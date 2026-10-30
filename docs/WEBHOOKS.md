# Webhooks

Webhook delivery is optional and configured in `TROA Admin Overseer Webhooks.cfg`. Enable the master and only the routes you use. Put each URL in its named `WebhookRoute`; XML query separators must use `&amp;`. Empty URLs remain disabled.

Routes include audit, moderation, joins, performance, rewards, limits, server, and critical as configured. Blank category mapping means muted. Use a Discord role ID for intended critical mentions. Protect URLs as credentials; never commit real endpoints.

Monitor+ command transport is separate from Overseer's webhook dispatch. Review Torch logs for delivery errors.
