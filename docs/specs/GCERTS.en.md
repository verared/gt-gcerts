# GCERTS Specification — Temporal Validity of Certificates (EXPERIMENTAL)

- **Status: EXPERIMENTAL** — separate from the normative core ·
  **Version:** 1.0.0 · **Baseline:** GUS v3.1.1
- **Consolidated edition:** [`../en/gus-3.0.0.md`](../en/gus-3.0.0.md) (§13.4)
- **License:** CC-BY-4.0 · Maintained by: verared contributors

> **This profile is NOT part of the calendar conformance guarantee nor of
> the canonical stamp.** There is no reference implementation in this
> repository; the specification declares the contract for future
> implementations.

## 1. Scope

Profiles for the **temporal validity of certificates** over GUS
coordinates: validity windows expressed in the TCJ/TAI scale (not in
civil UTC), verifiable offline and with the same determinism as the rest
of the standard.

## 2. Planned rules

1. Validity is expressed as the closed interval of GUS instants
   `[not_before, not_after]` (int64 seconds + nanos), never as ambiguous
   civil dates.
2. The validity check is a pure integer comparison, reproducible on any
   platform without network access.
3. Renewal and revocation are sealed events (GST domain) anchorable in
   the daily notary; a certificate's history is a verifiable chain.
4. Expiry is never extended by time zones or civil changes: the window
   is invariant even if the issuer jurisdiction changes its clock law.
5. An expired certificate is never "revalidated": a new one is issued;
   verification of historical signatures uses the material of the era.

## 3. Sources of truth

None yet: the specification is the source (Section 13.4 of the
consolidated edition).

## 4. Applicable vectors

None in this repository yet.

## 5. Maturity and limits

- **Experimental.** Not part of the conformance guarantee.
- GUS/GCERTS do not replace an operational PKI or operating-system
  security controls; they describe the temporal dimension that a PKI can
  consume in a verifiable way.

## 6. References

- Section 13.4 of the consolidated edition; `docs/en/threat-model.md`.
