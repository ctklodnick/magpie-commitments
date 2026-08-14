# Magpie commitments ledger

Append-only public record of cryptographic precommitments for the Magpie
trading-research project (a private, shadow-mode-only hobby system). Each
entry is a SHA-256 commitment published BEFORE the committed value is used,
so results derived later can prove the commitment predated them. The private
project repository records which commitment governs which study.

Format per line: ISO-date | label | sha256(secret) | context
