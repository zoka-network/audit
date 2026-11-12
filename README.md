# Zoka Quantic — Security Review

Internal security review (red-team) of the **Zoka Quantic Testnet v3** network.

We attacked our own network — consensus, block and transaction validation, the
two-of-three checkpoint authority and the public API surface — with live
adversarial requests and a line-by-line review of the code that must reject them.

**Result:** six controls tested, six passed. **No exploitable vulnerability was
found within the tested scope.**

## Reports

- **[Security Review — English](Zoka_Quantic_Security_Review_v3.pdf)** (PDF)
- **[Revisión de seguridad — Español](Zoka_Quantic_Revision_Seguridad_v3.pdf)** (PDF)

## Scope

**Tested:**

- Consensus integrity & double-spend prevention
- Transaction & block validation
- Emission & supply cap
- Checkpoint authority (2-of-3, hybrid Ed25519 + ML-DSA-65)
- Public API exposure & route separation
- Faucet abuse resistance (CAPTCHA + server-side caps)

**Not covered — pending external audit:**

- STARK proof-system soundness, including post-quantum soundness
- P2P resistance to DoS, eclipse & partition
- Memory-safety of `unsafe` code & side channels
- Tor transport & wallet-side key handling

## Honest framing

This is an **internal review, not a formal third-party audit**, and not a
guarantee of overall security. The independent external review of the protocol
and cryptography remains planned before mainnet.

**Basis:** live testing and source review of the Zoka node 5.0.1
(commit `afd0193a`) and the two public seeds, 12 November 2026. Internal
adversarial review with AI-assisted analysis.

---

### Español

Revisión de seguridad interna (red-team) de la red **Zoka Quantic Testnet v3**.
Atacamos nuestra propia red —consenso, validación de bloques y transacciones, la
autoridad de checkpoints de dos sobre tres y la superficie de la API pública— con
peticiones hostiles en vivo y una revisión del código línea por línea. Seis
controles probados, seis superados: no se encontró ninguna vulnerabilidad
explotable dentro del alcance probado. Es una revisión interna, **no una auditoría
formal de terceros**; la auditoría externa independiente sigue prevista antes de
la mainnet. El informe completo está en
[Revisión de seguridad — Español](Zoka_Quantic_Revision_Seguridad_v3.pdf).

---

[zoka.network](https://zoka.network) ·
[Wallet](https://wallet.zoka.network) ·
[Explorer](https://zokascan.cc) ·
[Faucet](https://faucet.zoka.network)
