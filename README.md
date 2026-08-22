# Zk--Cydonia-Foundry
# Quickstart demo CLI installation (Linux / macOS)
curl -fsSL https://cydonia.io/install-demo.sh | sh

# Run the local evaluation test
cydonia-attest-demo --node-id "CYDONIA_TEST_01" --simulate-proof
## ⚖️ Licensing & Commercial Use

This repository is licensed under the **Business Source License 1.1 (BSL 1.1)**.

* **Non-Commercial / Evaluation Use:** Free for testing, local development, and personal research.
* **Production & Commercial Use:** Requires an Enterprise License Key. 

To obtain a commercial license, access production binaries, or request custom TEE integration support, visit [cydonia.io/licensing](https://cydonia.io/licensing) or contact `licensing@cydonia.io`.
// Copyright (c) 2026 Cydonia Foundry. All rights reserved.
// Licensed under the Business Source License 1.1 (BSL-1.1).
// See LICENSE file in the project root for commercial licensing terms.
               CYDONIA ZK-TPM ATTESTATION SUITE (SDK v1.0)
                                    │
    ┌───────────────────────────────┼───────────────────────────────┐
    ▼                               ▼                               ▼
[MODULE 1: PROVER]            [MODULE 2: TPM DRIVER]        [MODULE 3: ANOMALY MATRIX]
Generates π = (A,B,C)         Binds Prover Output to        Real-Time Side-Channel &
ZK-SNARK Pairing Proofs       Hardware Root-of-Trust        Gradient Poisoning Detector
 Module 1: ZK-SNARK Prover Engine: Rust/C++ lightweight prover that compiles local execution traces into succinct Groth16 pairing proofs (\pi = (A, B, C)) without revealing local state or payload data.
 Module 2: Hardware Root-of-Trust Driver: Middleware connecting the ZK prover to local TPM 2.0 / Secure Enclaves, signing proofs with the node's endorsement key.
 Module 3: Multi-Modal Anomaly Detector: Active daemon monitoring clock drift (\Delta f), gradient poisoning (\Delta g > 0.042), and invalid curve point injections, auto-quarantining non-compliant nodes.
