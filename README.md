# CYFAI

<p align="center">
  <img src="public/cyfai-logo.png" alt="CYFAI logo" width="220" />
</p>

<p align="center"><strong>Clear approvals. Accountable payments. Verifiable records.</strong></p>

CYFAI is a financial transparency and payment coordination platform for small and medium-sized businesses. It helps a business turn a budget decision into a reviewable process: prepare a spending plan, collect approval from the people responsible, distribute funds through Paiflow, and check each payout against the Stellar network.

The goal is to make it easier for owners, finance teams, approvers, suppliers and other stakeholders to see what was authorized, where funds were sent, and what evidence supports the record. CYFAI combines practical business workflows with verifiable payment evidence, while keeping wallet signing in the user's Freighter wallet.

## What CYFAI does

- **Plan spending together.** Create a budget plan with recipients and allocations, then collect the required approvals before payment.
- **Distribute through Paiflow.** Submit an approved plan to its prepared Paiflow Split deployment. The business signs with Freighter; CYFAI does not hold wallet keys.
- **Verify payouts.** Check each recipient payout against Stellar transaction evidence and distinguish confirmed transactions from payouts that have not yet been verified.
- **Keep a reviewable record.** Preserve plan versions, approval history, documents and file-integrity checks so a reviewer can compare the current record with its evidence.
- **Understand budget performance.** Compare planned amounts with verified payouts, and export money-movement records for review.

CYFAI supports visibility and verification; it does not prove that a purchase was useful, compliant, or well spent. Stellar Testnet demonstrations use test assets and are not production financial services.

## How the flow works

```mermaid
flowchart LR
    A[Prepare budget plan] --> B[Collect approvals]
    B --> C[Owner signs with Freighter]
    C --> D[Paiflow Split on Stellar]
    D --> E[Verify each payout]
    E --> F[Review records and evidence]
```

## Demonstration status

The current prototype has completed an end-to-end Stellar Testnet payment demonstration: an owner signed in, bound a Testnet wallet, approved a budget plan, signed a 1 XLM Paiflow Split payment, and verified its three envelope payouts on-chain (0.5, 0.3 and 0.2 XLM). This demonstrates the payment and evidence flow in a test environment; it is not a production-readiness or security certification.

## Getting started

```bash
# Node 22.22.2 is the version supported by the Paiflow SDK (>=22.22.2 <23)
npm ci
cp .env.local.example .env.local   # add local values; never commit this file
npm run dev                        # http://localhost:3000
```

Available checks: `npm run lint`, `npm run typecheck`, `npm test`, `npm run build`, and `npm run check:bundle`. Database and local live-test instructions are in [TESTING.md](TESTING.md).

## Technology

| Area | Technology |
|---|---|
| Web application | Next.js App Router, TypeScript, Tailwind CSS |
| Server | Next.js route handlers |
| Data, files and sessions | Supabase PostgreSQL, Storage and cookie-based sessions |
| Payments | Paiflow SDK on Stellar Testnet; Freighter wallet signing |
| Integrity evidence | SHA-256 file and plan hashes with an application audit chain |

## Team

| Name | Program | University |
|---|---|---|
| Francis Gabriel P. Austria | BS Computer Science | West Visayas State University (WVSU) |
| Om Shanti Limpin | BS Computer Science | West Visayas State University (WVSU) |
| Carlos John Aristoki | BS Computer Science | West Visayas State University (WVSU) |

## License

Built for hackathon use. The source code is public as required by the competition rules.
