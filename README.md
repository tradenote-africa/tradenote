# TradeNote

Buyer-confirmed invoice finance for African suppliers, recorded on the XRP Ledger.

TradeNote is a proposed system that would let a supplier upload an invoice, require the named business buyer to confirm the amount and the obligation, allow an approved funder to offer an advance, and only then record the financing on the XRP Ledger. This repository currently holds concept documentation only. There is no application implementation, deployment, demo, partner integration, or ledger transaction history here.

## Status

Version 0.1 — concept and proposed architecture, 7 November 2026.

This is not a live product. No software, users, partners, licences, collections, or XRP Ledger transactions are claimed. Local payout rails mentioned in the design are proposed adapters, not live integrations.

The full design is in [WHITEPAPER.md](WHITEPAPER.md). These files are released under the [MIT License](LICENSE).

## Proposed workflow

1. A supplier creates an invoice record and uploads the document.
2. The named buyer confirms the amount and the obligation, or rejects the record. Unconfirmed invoices cannot be financed. Confirmation is not payment.
3. An approved funder, not the general public, may offer an advance below face value. An offer is not a promised return.
4. If the supplier accepts, the parties would execute financing or assignment documents off the ledger.
5. Only after that legal gate would the operator record a Multi-Purpose Token for that financed invoice, and the funder send a separate Payment of a test-issued settlement token. Those two ledger steps are sequential. They are not atomic delivery-versus-payment.
6. Collection would later use local fiat rails. The ledger can retire the invoice token after repayment; it cannot force the buyer to pay.

## Scope

The product language and architecture are pan-African. A first real launch, if it happens, would still start in one locally regulated corridor. No single licence, bank account, or payment rail is claimed to cover the continent.

The roles in the design are the supplier, the named buyer, an approved funder, and a licensed local partner (the operator) for corridor-specific compliance, token issuance, and collection.

## What a ledger record cannot do

A token does not create legal title by itself. If, and only if, valid legal documents say so, it can stand as an on-chain record of a contractual assignment or of a funder's participation in a receivable.

Buyer confirmation is not a guarantee that the buyer will pay, will not later dispute delivery, or will not default. An uploaded invoice is not proof that goods were delivered.

The application could refuse a second financing of the same invoice inside TradeNote, using a canonical key and a document hash. It cannot see or stop financing of the same invoice at a bank or on another platform.

If a local-currency invoice were funded in another currency, including a dollar stablecoin in a later phase, exchange-rate movement could leave the collected amount short of the advance and charges. The first demonstration described in the paper would use a test-issued settlement token created by the operator, not RLUSD. The XRP Ledger is a public network; Ripple is a separate company. Building on the ledger is not a Ripple partnership.

There is no TradeNote platform token and no guaranteed yield.

## Documents

- [WHITEPAPER.md](WHITEPAPER.md) — version 0.1 white paper
- [LICENSE](LICENSE) — MIT License
