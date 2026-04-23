import React from 'react';
import { Shield } from 'lucide-react';

export default function PrivacyTerms() {
  return (
    <div className="min-h-screen bg-background">
      {/* Header */}
      <header className="w-full border-b border-border/60 bg-card/80 backdrop-blur-md sticky top-0 z-50">
        <div className="max-w-2xl mx-auto px-6 py-4 flex items-center gap-3">
          <div className="p-2 rounded-lg bg-accent/10">
            <Shield className="w-5 h-5 text-accent" />
          </div>
          <div>
            <h1 className="text-base font-semibold text-foreground">SecureFox</h1>
            <p className="text-xs text-muted-foreground">Privacy & Terms</p>
          </div>
        </div>
      </header>

      {/* Content */}
      <main className="max-w-2xl mx-auto px-6 py-14 space-y-12">
        {/* Terms & Conditions */}
        <section>
          <h2 className="text-2xl font-serif font-bold text-foreground mb-4">Terms & Conditions</h2>
          <p className="text-muted-foreground leading-relaxed">
            By using this app, you agree to use the VPN service only for lawful and authorized activities. You must not use the service for fraud, abuse, harassment, unauthorized access, copyright infringement, spam, or any other illegal purpose. You are responsible for your own traffic and compliance with local laws. If you do not agree with these terms, please do not use the app.
          </p>
        </section>

        <div className="border-t border-border/50" />

        {/* Privacy Policy */}
        <section>
          <h2 className="text-2xl font-serif font-bold text-foreground mb-4">Privacy Policy</h2>
          <div className="text-muted-foreground leading-relaxed space-y-4">
            <p>
              We are committed to protecting your privacy. SecureFox does not log, monitor, or store any of your browsing activity, connection timestamps, IP addresses, or traffic data.
            </p>
            <p>
              The only data we collect is your account email (for authentication) and subscription status. Your data is never sold or shared with third parties. All connections are encrypted end-to-end. You may delete your account and all associated data at any time by contacting support.
            </p>
          </div>
        </section>

        <div className="pt-8 border-t border-border/50">
          <p className="text-sm text-muted-foreground text-center">© 2026 SecureFox. All rights reserved.</p>
        </div>
      </main>
    </div>
  );
}
