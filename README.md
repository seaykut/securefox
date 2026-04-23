import React from 'react';
import { motion } from 'framer-motion';
import { Shield, ArrowUp } from 'lucide-react';
import { Button } from '@/components/ui/button';
import PageHeader from '../components/privacy/PageHeader';
import SectionBlock from '../components/privacy/SectionBlock';
import TableOfContents from '../components/privacy/TableOfContents';

const fadeIn = {
  hidden: { opacity: 0, y: 16 },
  visible: (i) => ({
    opacity: 1,
    y: 0,
    transition: { delay: i * 0.04, duration: 0.5, ease: 'easeOut' },
  }),
};

export default function PrivacyTerms() {
  const scrollToTop = () => window.scrollTo({ top: 0, behavior: 'smooth' });

  return (
    <div className="min-h-screen bg-background">
      <PageHeader />

      {/* Hero */}
      <motion.div
        initial={{ opacity: 0, y: 20 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.6 }}
        className="max-w-4xl mx-auto px-6 pt-16 pb-10"
      >
        <div className="flex items-center gap-3 mb-4">
          <div className="p-2.5 rounded-xl bg-accent/10">
            <Shield className="w-5 h-5 text-accent" />
          </div>
          <span className="text-xs font-medium uppercase tracking-widest text-muted-foreground">
            Legal
          </span>
        </div>
        <h1 className="text-4xl md:text-5xl font-serif font-bold text-foreground tracking-tight leading-tight">
          Privacy Policy &<br />Terms of Service
        </h1>
        <p className="mt-4 text-muted-foreground text-lg max-w-2xl leading-relaxed">
          At Secure Fox, we are committed to protecting your privacy and ensuring transparency in how we handle your data. Please read this policy carefully.
        </p>
        <p className="mt-3 text-sm text-muted-foreground/70">
          Last updated: April 23, 2026 &nbsp;·&nbsp; Effective immediately
        </p>
      </motion.div>

      {/* Content */}
      <div className="max-w-4xl mx-auto px-6 pb-24">
        <motion.div
          initial="hidden"
          animate="visible"
          variants={fadeIn}
          custom={0}
          className="mb-12"
        >
          <TableOfContents />
        </motion.div>

        <div className="space-y-12">
          {sections.map((section, i) => (
            <motion.div
              key={section.id}
              id={section.id}
              initial="hidden"
              whileInView="visible"
              viewport={{ once: true, margin: '-40px' }}
              variants={fadeIn}
              custom={i}
            >
              <SectionBlock number={String(i + 1).padStart(2, '0')} title={section.title}>
                {section.content}
              </SectionBlock>
            </motion.div>
          ))}
        </div>

        {/* Divider */}
        <div className="mt-20 pt-10 border-t border-border/50 flex flex-col sm:flex-row items-center justify-between gap-4">
          <p className="text-sm text-muted-foreground">
            © 2026 Secure Fox. All rights reserved.
          </p>
          <Button
            variant="outline"
            size="sm"
            onClick={scrollToTop}
            className="gap-2"
          >
            <ArrowUp className="w-3.5 h-3.5" />
            Back to top
          </Button>
        </div>
      </div>
    </div>
  );
}

const sections = [
  {
    id: 'terms',
    title: 'Terms & Conditions',
    content: (
      <p>
        By using this app, you agree to use the VPN service only for lawful and authorized activities. You must not use the service for fraud, abuse, harassment, unauthorized access, copyright infringement, spam, or any other illegal purpose. You are responsible for your own traffic and compliance with local laws. If you do not agree with these terms, please do not use the app.
      </p>
    ),
  },
  {
    id: 'privacy',
    title: 'Privacy Policy',
    content: (
      <>
        <p>
          We are committed to protecting your privacy. SecureFox does not log, monitor, or store any of your browsing activity, connection timestamps, IP addresses, or traffic data.
        </p>
        <p>
          The only data we collect is your account email (for authentication) and subscription status. Your data is never sold or shared with third parties. All connections are encrypted end-to-end. You may delete your account and all associated data at any time by contacting support.
        </p>
      </>
    ),
  },
];
