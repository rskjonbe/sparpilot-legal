---
title: SparPilot Privacy Policy
---
# SparPilot — Privacy Policy

**Last updated: 24 October 2026**

## Scope and current operating status
SparPilot is a privately operated AI-assisted personal-finance project. Its live, read-only bank-information connections currently include Nordea and SAS EuroBonus Mastercard through Enable Banking. It supports viewing authorized account and card details, balances and transactions, and savings-oriented analysis. It does not initiate payments or transfers.

This notice describes the observed design and identifies controls that are **not yet fully verified**. It is not a GDPR compliance certification.

## Operator and contact
The project is operated by its individual owner. For questions about SparPilot, use the application contact details registered with Enable Banking. The project is intended for the owner's personal use; extending it to other users would require a new legal and security assessment.

## Information and purposes
Depending on the bank's authorized access, information may include account and card references, masked account identifiers, balances, transaction amounts and dates, counterparties, transaction descriptions and user-assigned account names. Descriptions may incidentally reveal sensitive personal details. The purpose is personal overview, expense analysis, reconciliation and identifying potential savings, not advertising, profiling other people or automated credit decisions.

## How data moves and where it may be processed
The user interacts with SparPilot through a private plugin in ChatGPT. The plugin connects to a SparPilot MCP backend hosted using Railway. Identity is mediated by Auth0; account-information access is provided via Enable Banking and the participating banks. The backend uses Neon PostgreSQL for bank-session, authorization, account-binding and display-name records. Banking results sent to ChatGPT become part of the interaction with OpenAI and are subject to the applicable ChatGPT privacy settings and terms. This is **not exclusively local processing**. The reviewed backend code does not intentionally persist a transaction-history table, but platform logs, conversation retention, backups and any provider-side retention have not been comprehensively verified.

A vendor's EU-region setting alone does not establish that all processing, support access and subprocessors remain within the EEA. Exact locations, contractual roles, international transfers and applicable provider retention policies still require confirmation before any broader use.

## Access, authorization and security
Bank authorization is completed separately with the relevant provider and is not equivalent to consent for every downstream processing purpose. The current backend is designed to bind sessions and account access to the authenticated operator, enforce short-lived one-time authorization state and encrypt temporary callback data, and use verified TLS for database client connections. These are implementation and test observations, not an independent end-to-end security certification.

The application's financial-data tools are intended to be read-only. It can nevertheless store personal display names and create or complete authorization records. No payment or transfer capability is exposed by the reviewed plugin. Never disclose bank credentials, signing keys, BankID codes or tokens in chats or public source repositories.

## Retention, withdrawal and deletion
Stored authorization records and display-name preferences, infrastructure logs, backup snapshots and ChatGPT conversation data have different lifecycles. **A complete end-to-end deletion and revocation procedure has not yet been verified.** Removing local data does not by itself revoke a bank's authorization; revoking bank access does not necessarily erase prior ChatGPT messages, backups or provider logs. For withdrawal of banking access, use the bank/provider's available authorization management process. For ChatGPT-held data, use the applicable ChatGPT controls.

The backend has a bounded cleanup utility for expired *temporary* authorization state; it is not a general-purpose user deletion or revocation mechanism. Exact operational retention periods and deletion controls are under review. No unsupported promise of instant or comprehensive deletion is made.

## Legal context
For strictly personal or household activity, the GDPR household exemption may be relevant to the individual operator; it does not automatically exempt independent service providers. Broader or commercial operation requires a separate assessment of controller/processor roles, legal basis, transparency, contracts, transfers, rights requests and security. Bank/PSD2 authorization must not be represented as a blanket GDPR legal basis.

## Updates
The notice will be reviewed when bank connectivity, providers, processing purposes, retention controls or available users change. Open items include infrastructure and edge logging, supplier terms and processing locations, verified end-to-end access revocation and deletion.
