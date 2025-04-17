# Awesome Consensus

The literature on consensus is vast. Here's a selection of papers exploring the research landscape, focusing on recent systems, tradeoff extrema, and features interesting for Hellas. The sections are not mutually exclusive: papers are listed multiply if they are relevant.

## I. Foundational Concepts and Theoretical Limits

This section covers papers exploring the fundamental principles, theoretical models, and inherent limitations of Byzantine agreement and related problems. It includes work on core consensus properties, formal modeling techniques, and analyses of different adversary models.

*   [Permissionless Consensus](#lewis-pyePermissionlessConsensus2024): Provides a framework for reasoning about consensus in permissionless settings with varying degrees of participant knowledge.
*   [Consensus Under Adversary Majority Done Right](#sridharConsensusAdversaryMajority2024): Systematizes consensus models based on client/validator behavior and network synchrony, characterizing resilience limits.
*   [All Byzantine Agreement Problems are Expensive](#civitAllByzantineAgreement2023): Proves a general quadratic message complexity lower bound for *any* non-trivial Byzantine agreement variant, closing a long-standing open problem.
*   [Communication Complexity of Byzantine Agreement, Revisited](#abrahamCommunicationComplexityByzantine2020): Explores the necessity of the "no after-the-fact removal" assumption for sub-quadratic BA and presents new constructions.
*   [Strong Byzantine Agreement with Adaptive Word Complexity](#civitStrongByzantineAgreement2023): Introduces the first SBA protocol with word complexity adaptive to the actual number of faults, focusing on efficient certification.
*   [The information structure of indulgent consensus](#guerraouiInformationStructureIndulgent2004): Analyzes the core information requirements for indulgent consensus protocols using the "Lambda" abstraction.
*   [In Search for an Optimal Authenticated Byzantine Agreement](#spiegelmanSearchOptimalAuthenticated2021): Proposes an optimistic BA protocol combining synchronous and asynchronous approaches, aiming for optimal complexity across network conditions.
*   [Simplicial Models for the Epistemic Logic of Faulty Agents](#goubaultSimplicialModelsEpistemic2023): Explores simplicial complex models for epistemic logic to reason about systems with varying numbers of (potentially crashed) agents.
*   [On Consensus Number 1 Objects](#khanchandaniConsensusNumber12021): Studies the properties and implementation of objects with consensus number 1, relevant for applications like asset transfer.
*   [Ouroboros Genesis: Composable Proof-of-Stake Blockchains with Dynamic Availability](#badertscherOuroborosGenesisComposable2018a): Presents a PoS protocol allowing secure bootstrapping from genesis in dynamic availability settings.
*   [Foundations of Dynamic BFT](#duanFoundationsDynamicBFT2022): Provides formal definitions and explores challenges for BFT protocols supporting dynamic membership changes.
*   [Towards Rational Consensus in Honest Majority](#srivastavaRationalConsensusHonest2024): Explores consensus in the presence of rational (incentive-driven) players alongside honest and Byzantine ones.
*   [Vivisecting the Dissection: On the Role of Trusted Components in BFT Protocols](#bessaniVivisectingDissectionRole2023): Critiques arguments against using TCs for replica reduction (to 2f+1) and defends their value for resilience.
*   [Reconfigurable Heterogeneous Quorum Systems](#liReconfigurableHeterogeneousQuorum2023): Models and provides reconfiguration protocols for quorum systems where participants define their own quorums and trust assumptions.
*   [Swiper: a new paradigm for efficient weighted distributed protocols](#tonkikhSwiperNewParadigm2024): Presents a general method to transform nominal-model protocols to the weighted model efficiently, preserving resilience for many important problems.

## II. Communication Complexity: Bounds and Optimality

These papers focus specifically on analyzing and optimizing the communication cost (bits or words exchanged) of Byzantine consensus protocols, a critical factor for scalability. They include lower bound proofs and protocols striving to match or improve upon these bounds.

*   [All Byzantine Agreement Problems are Expensive](#civitAllByzantineAgreement2023): Establishes the fundamental quadratic message complexity lower bound for all non-trivial BA problems.
*   [Communication Complexity of Byzantine Agreement, Revisited](#abrahamCommunicationComplexityByzantine2020): Investigates conditions for sub-quadratic BA and presents constructions achieving it under specific assumptions.
*   [Byzantine Consensus is Θ( n 2 ) The Dolev-Reischuk Bound is Tight even in Partial Synchrony! (Extended Version)](#civitByzantineConsensus22022): Presents SQuad, the first partially synchronous BA protocol proven to achieve optimal quadratic worst-case communication complexity.
*   [Quadratic worst-case message complexity for State Machine Replication in the partial synchrony model](#lewis-pyeQuadraticWorstcaseMessage2022): Describes a partially synchronous SMR protocol achieving the quadratic message complexity lower bound while maintaining optimistic responsiveness.
*   [Near-Optimal Communication Byzantine Reliable Broadcast Under a Message Adversary](#albouyNearOptimalCommunicationByzantine2025): Presents an MBRB algorithm with near-optimal bit complexity using coding techniques, threshold signatures, and vector commitments.
*   [Make Every Word Count: Adaptive Byzantine Agreement with Fewer Words](#cohenMakeEveryWord2023): Introduces BA/BB algorithms with communication complexity adaptive to the actual number of faults *f*, achieving O(n(f+1)).
*   [Strong Byzantine Agreement with Adaptive Word Complexity](#civitStrongByzantineAgreement2023): Introduces STRONG, a synchronous SBA protocol achieving adaptive word complexity.
*   [In Search for an Optimal Authenticated Byzantine Agreement](#spiegelmanSearchOptimalAuthenticated2021): Proves a lower bound for synchronous deterministic BA adaptive to failures and presents a matching optimistic protocol.
*   [Optimal Communication Complexity of Authenticated Byzantine Agreement](#momoseOptimalCommunicationComplexity2021): Presents two authenticated BA protocols achieving quadratic communication with different resilience/assumption trade-offs, nearing or matching the lower bound.
*   [Efficient Signature-Free Validated Agreement](#civitEfficientSignatureFreeValidated2024): Presents synchronous validated BA algorithms (HashExt, ErrorFreeExt) with near-optimal bit complexity without requiring signatures.
*   [Every Bit Counts in Consensus](#civitEveryBitCounts2023): Introduces DARE, improving the bit complexity for partially synchronous consensus for large messages (L > nκ) via a dispersal primitive.
*   [Asynchronous Data Dissemination and its Applications](#dasAsynchronousDataDissemination2021): Introduces an ADD primitive to improve communication cost for asynchronous RBC and related protocols.
*   [Byzantine Reliable Broadcast with Low Communication and Time Complexity](#locherByzantineReliableBroadcast2024): Introduces a mechanism to reduce the communication overhead factor in coding-based asynchronous BRB to 2 or 3/2.
*   [MiniCast: Minimizing the Communication Complexity of Reliable Broadcast](#locherMiniCastMinimizingCommunication2024): Presents an asynchronous RBC protocol achieving 1.5|m|n communication complexity for long messages, improving on the prior best of 2|m|n.
*   [Wahoo: A DAG-Based BFT Consensus With Low Latency and Low Communication Overhead](#daiWahooDAGBasedBFT2024): Achieves O(n^2) communication overhead in a DAG-based protocol using novel Provable Broadcast primitives.
*   [Fever: Optimal Responsive View Synchronisation](#lewis-pyeFeverOptimalResponsive2023): Achieves optimal quadratic worst-case communication for view sync while enabling linear cost between correct leaders.
*   [Lumiere: Making Optimal BFT for Partial Synchrony Practical](#lewis-pyeLumiereMakingOptimal2023): Achieves optimal worst-case O(n^2) communication while enabling communication adaptive to actual faults eventually.
*   [Expected Linear Round Synchronization: The Missing Link for Linear Byzantine SMR](#naorExpectedLinearSynchronization2020): Presents the first round synchronization algorithm with expected linear message complexity.
*   [Cogsworth: Byzantine View Synchronization.](#naorCogsworthByzantineView2019): Introduces Cogsworth, a view synchronization protocol with optimistically linear communication.
*   [Sing a Song of Simplex](#shoupSingSongSimplex2024): Modifies Simplex for more communication-efficient block dispersal while retaining optimal latency.

## III. Network Models and Protocol Adaptivity

This section categorizes protocols based on the network timing assumptions they make (synchronous, partially synchronous, asynchronous) and explores protocols designed to adapt their performance or behavior based on network conditions (hybrid/adaptive).

### Partially Synchronous Protocols
These protocols assume the network eventually becomes synchronous (after some Global Stabilization Time, GST) and remain so for long enough to make progress. They often optimize for behavior during synchronous periods.

*   [Byzantine Consensus is Θ( n 2 ) The Dolev-Reischuk Bound is Tight even in Partial Synchrony! (Extended Version)](#civitByzantineConsensus22022): Presents SQuad, achieving optimal quadratic communication in partial synchrony.
*   [Quadratic worst-case message complexity for State Machine Replication in the partial synchrony model](#lewis-pyeQuadraticWorstcaseMessage2022): Achieves optimal quadratic communication for SMR in partial synchrony.
*   [Every Bit Counts in Consensus](#civitEveryBitCounts2023): Presents DARE/DARE-Stark with improved bit complexity for partially synchronous consensus.
*   [Fever: Optimal Responsive View Synchronisation](#lewis-pyeFeverOptimalResponsive2023): A view synchronization protocol for partial synchrony with optimal worst-case and responsive linear communication.
*   [Lumiere: Making Optimal BFT for Partial Synchrony Practical](#lewis-pyeLumiereMakingOptimal2023): Enables BFT SMR in partial synchrony with optimal worst-case communication and adaptive communication/latency based on actual faults.
*   [The latest gossip on BFT consensus](#buchmanLatestGossipBFT2019): Describes Tendermint, a BFT consensus protocol often deployed in partially synchronous settings.
*   [Snowman for partial synchrony](#buchwaldSnowmanPartialSynchrony2025): Modifies the Snowman (Avalanche) protocol for consistency in partial synchrony.
*   [Autobahn: Seamless high speed BFT](#giridharanAutobahnSeamlessHigh2025): Combines asynchronous dissemination with partially synchronous consensus for low latency and seamless recovery.
*   [Proofs of non-Supermajority: the missing link for two-phase BFT with responsive view-change and linear complexity](#levratProofsNonSupermajorityMissing2023): Enables two-phase, responsive, linear-complexity BFT in partial synchrony using a new PnS primitive.
*   [Rondo: Scalable and Reconfiguration-Friendly Randomness Beacon](#mengRondoScalableReconfigurationFriendly2024): Presents a DRB protocol built using a novel partially synchronous BFT protocol (Rondo-BFT).
*   [Fast Leaderless Byzantine Total Order Broadcast](#montiFastLeaderlessByzantine2024): Presents Flutter/Blink, leaderless total-order broadcast/binary consensus protocols for partial synchrony with fast paths.

### Asynchronous Protocols
These protocols make no assumptions about network delay bounds, guaranteeing safety and liveness regardless of message timing (though performance may degrade under high latency).

*   [Near-Optimal Communication Byzantine Reliable Broadcast Under a Message Adversary](#albouyNearOptimalCommunicationByzantine2025): Presents an asynchronous MBRB algorithm with near-optimal bit complexity.
*   [Asynchronous Data Dissemination and its Applications](#dasAsynchronousDataDissemination2021): Introduces an ADD primitive and uses it to improve communication for asynchronous RBC and other primitives.
*   [Byzantine Reliable Broadcast with Low Communication and Time Complexity](#locherByzantineReliableBroadcast2024): Presents asynchronous BRB algorithms with reduced communication overhead factor (2 or 3/2).
*   [MiniCast: Minimizing the Communication Complexity of Reliable Broadcast](#locherMiniCastMinimizingCommunication2024): Achieves 1.5|m|n communication complexity for asynchronous RBC with long messages.
*   [Asynchronous BFT Asset Transfer: Quasi-Anonymous, Light, and Consensus-Free](#albouyAsynchronousBFTAsset2025): An asynchronous, consensus-free asset transfer system.
*   [Making Hash-based MVBA Great Again](#fengMakingHashbasedMVBA2024): Introduces a hash-based asynchronous MVBA with nearly optimal communication, outperforming prior hash-based and signature-based schemes.
*   [Mahi-Mahi: Low-Latency Asynchronous BFT DAG-Based Consensus](#jovanovicMahiMahiLowLatencyAsynchronous2024): An asynchronous DAG-based consensus protocol achieving sub-second latency using uncertified DAGs.

### Hybrid and Adaptive Protocols
These protocols attempt to get the best of both worlds: high performance (low latency/high throughput) when the network behaves well (like partial synchrony) but maintaining guaranteed progress (liveness) even under asynchronous conditions.

*   [Jolteon and Ditto: Network-Adaptive Efficient Consensus with Asynchronous Fallback](#gelashviliJolteonDittoNetworkAdaptive2022): Presents Ditto, combining a linear partially synchronous protocol (Jolteon) with an asynchronous fallback for optimal communication and robustness.
*   [Bolt-Dumbo Transformer: Asynchronous Consensus As Fast As the Pipelined BFT](#luBoltDumboTransformerAsynchronous2022): Presents BDT, a framework for optimistic asynchronous atomic broadcast with efficient pace-synchronization for fallback.
*   [Abraxas: Throughput-Efficient Hybrid Asynchronous Consensus](#blumAbraxasThroughputEfficientHybrid2023): Constructs a hybrid protocol from fast (Πfast) and asynchronous (Πslow) components, maintaining Πslow's performance in bad conditions and Πfast's in good conditions.
*   [ParBFT: Faster Asynchronous BFT Consensus with a Parallel Optimistic Path](#daiParBFTFasterAsynchronous2023): Runs optimistic and pessimistic paths in parallel to ensure low latency without accurate network delay estimation.
*   [Ipotane: Achieving the Best of All Worlds in Asynchronous BFT](#daiIpotaneAchievingBest2024): Aims for partially synchronous performance in good conditions and purely asynchronous performance (throughput & latency) in bad conditions using parallel paths and a novel DBA primitive.
*   [Remora: A Low-Latency DAG-Based BFT Through Optimistic Paths](#daiRemoraLowLatencyDAGBased2025): A DAG-based BFT protocol using optimistic paths for low latency (3 rounds) in favorable conditions, falling back to a pessimistic path otherwise.
*   [Autobahn: Seamless high speed BFT](#giridharanAutobahnSeamlessHigh2025): Combines asynchronous dissemination with partially synchronous consensus for low latency and seamless recovery from transient asynchrony ("blips").
*   [Bullshark: DAG BFT Protocols Made Practical](#spiegelmanBullsharkDAGBFT2022): A DAG-based protocol optimized for the common synchronous case ("fast-path") while retaining asynchronous liveness.
*   [In Search for an Optimal Authenticated Byzantine Agreement](#spiegelmanSearchOptimalAuthenticated2021): Proposes an optimistic protocol using a synchronous algorithm first, falling back to a randomized asynchronous one if needed.
*   [Slipstream: Ebb-and-Flow Consensus on a DAG with Fast Confirmation for UTXO Transactions](#polyanskiiSlipstreamEbbandFlowConsensus2024): Offers both an optimistic ordering (live in sleepy model) and a final ordering (live in eventual lock-step synchronous model).

### Synchronous Protocols
These protocols assume known, fixed upper bounds on message delivery times (Δ). They often offer simplicity or different resilience characteristics but can fail if the bounds are violated.

*   [How Robust Are Synchronous Consensus Protocols?](#milosevicHowRobustAre2025): Introduces BoundBFT and analyzes the robustness and performance trade-offs of synchronous protocols concerning the synchrony bound Δ.
*   [Efficient Signature-Free Validated Agreement](#civitEfficientSignatureFreeValidated2024): Presents HashExt and ErrorFreeExt, synchronous validated BA algorithms with near-optimal bit complexity without signatures.
*   [Strong Byzantine Agreement with Adaptive Word Complexity](#civitStrongByzantineAgreement2023): Introduces STRONG, a synchronous SBA protocol achieving adaptive word complexity.

## IV. DAG-based Consensus Architectures

This section focuses on protocols that structure communication and dependencies as a Directed Acyclic Graph (DAG), often aiming for higher throughput by decoupling dissemination from ordering or allowing parallel processing. Includes mempool designs based on DAGs.

*   [SoK: DAG-based Consensus Protocols](#raikwarSoKDAGbasedConsensus2024): A Systematization of Knowledge paper reviewing and categorizing DAG-based consensus protocols.
*   [Narwhal and Tusk: A DAG-based Mempool and Efficient BFT Consensus](#danezisNarwhalTuskDAGbased2022): Separates dissemination (Narwhal mempool) from ordering (Tusk consensus) using a DAG structure for high throughput.
*   [All You Need is DAG](#keidarAllYouNeed2021): Presents DAG-Rider, an asynchronous Byzantine Atomic Broadcast protocol built on a DAG, achieving optimal resilience, amortized communication, and time.
*   [Bullshark: DAG BFT Protocols Made Practical](#spiegelmanBullsharkDAGBFT2022): Optimizes DAG-based consensus for low latency in synchronous periods via a fast path, while retaining asynchronous liveness.
*   [Mysticeti: Reaching the Limits of Latency with Uncertified DAGs](#babelMysticetiReachingLimits2024): Achieves 3-round latency lower bound using uncertified DAGs and a novel commit rule, plus a fast path extension (Mysticeti-FPC).
*   [LightDAG: A Low-latency DAG-based BFT Consensus through Lightweight Broadcast](#daiLightDAGLowlatencyDAGbased2024): Reduces DAG latency by replacing RBC with lighter broadcast primitives (CBC, PBC) and handling potential issues like missing totality or equivocation.
*   [Remora: A Low-Latency DAG-Based BFT Through Optimistic Paths](#daiRemoraLowLatencyDAGBased2025): Uses optimistic paths on a DAG to achieve 3-round latency in good cases.
*   [Wahoo: A DAG-Based BFT Consensus With Low Latency and Low Communication Overhead](#daiWahooDAGBasedBFT2024): Reduces DAG communication to O(n^2) using novel Provable Broadcast primitives (PBC, EPBC) while maintaining low latency.
*   [Mahi-Mahi: Low-Latency Asynchronous BFT DAG-Based Consensus](#jovanovicMahiMahiLowLatencyAsynchronous2024): Achieves sub-second asynchronous latency by using uncertified DAGs and committing multiple blocks per round.
*   [Sailfish: Towards Improving the Latency of DAG-based BFT](#shresthaSailfishImprovingLatency): Aims to reduce DAG latency by supporting a leader vertex in *each* round.
*   [BBCA-CHAIN: Low Latency, High Throughput BFT Consensus on a DAG](#malkhiBBCACHAINLowLatency2023): Uses a modified BCB primitive (BBCA) for direct commits on a DAG backbone, reducing voting latency.
*   [Tangle 2.0 Leaderless Nakamoto Consensus on the Heaviest DAG](#mullerTangle20Leaderless2022): Describes the Tangle 2.0 protocol using a stake-weighted DAG for leaderless consensus.
*   [Slipstream: Ebb-and-Flow Consensus on a DAG with Fast Confirmation for UTXO Transactions](#polyanskiiSlipstreamEbbandFlowConsensus2024): A DAG-based BFT protocol with optimistic and final ordering layers, plus fast UTXO confirmation.
*   [Autobahn: Seamless high speed BFT](#giridharanAutobahnSeamlessHigh2025): Leverages a highly parallel asynchronous DAG-like data dissemination layer combined with partially synchronous consensus.
*   [The Blocklace: A Byzantine-repelling and Universal Conflict-free Replicated Data Type](#almeidaBlocklaceByzantinerepellingUniversal2024): Proposes the blocklace, a partially-ordered DAG structure, as a universal BFT CRDT implementation.

## V. Broadcast Primitives and Data Dissemination

Focuses on the fundamental building blocks for disseminating information reliably and consistently in the presence of Byzantine faults. Covers variants like Reliable Broadcast (RBC), Consistent Broadcast (CBC), Atomic Broadcast (ABC), and techniques for optimizing them.

*   [Near-Optimal Communication Byzantine Reliable Broadcast Under a Message Adversary](#albouyNearOptimalCommunicationByzantine2025): Near-optimal communication MBRB using coding, threshold signatures, and vector commitments.
*   [Asynchronous Data Dissemination and its Applications](#dasAsynchronousDataDissemination2021): Introduces Asynchronous Data Dissemination (ADD) to improve asynchronous RBC communication cost.
*   [Byzantine Reliable Broadcast with Low Communication and Time Complexity](#locherByzantineReliableBroadcast2024): Reduces communication overhead factor in asynchronous BRB using a novel mechanism.
*   [MiniCast: Minimizing the Communication Complexity of Reliable Broadcast](#locherMiniCastMinimizingCommunication2024): Achieves 1.5|m|n communication for asynchronous RBC, improving on the state-of-the-art factor of 2.
*   [A New Broadcast Primitive for BFT Protocols](#drijversNewBroadcastPrimitive2024): Defines and implements "abortable broadcast," a practical primitive providing strong guarantees while bounding resources.
*   [Generic Multicast](#bolinaGenericMulticast2024): Proposes a generic multicast primitive combining atomic broadcast, atomic multicast, and generic broadcast properties efficiently.
*   [LightDAG: A Low-latency DAG-based BFT Consensus through Lightweight Broadcast](#daiLightDAGLowlatencyDAGbased2024): Uses Consistent Broadcast (CBC) and Plain Broadcast (PBC) instead of RBC for lower latency in DAGs.
*   [Wahoo: A DAG-Based BFT Consensus With Low Latency and Low Communication Overhead](#daiWahooDAGBasedBFT2024): Introduces Provable Broadcast (PBC) and Enhanced Provable Broadcast (EPBC) with linear communication overhead for DAGs.
*   [BBCA-CHAIN: Low Latency, High Throughput BFT Consensus on a DAG](#malkhiBBCACHAINLowLatency2023): Uses a modified Byzantine Consistent Broadcast (BBCA) with a "Complete-Adopt" semantic for efficient DAG consensus.
*   [Chop Chop: Byzantine Atomic Broadcast to the Network Limit](#camaioniChopChopByzantine2024): Achieves extremely high throughput Atomic Broadcast using an authenticated memory pool and "distillation" batching.
*   [Dynamic Probabilistic Reliable Broadcast](#anikinaDynamicProbabilisticReliable2023): Explores probabilistic validation with dynamic witnesses to overcome quadratic RBC communication costs.
*   [Make Every Word Count: Adaptive Byzantine Agreement with Fewer Words](#cohenMakeEveryWord2023): Presents an adaptive Byzantine Broadcast algorithm with O(n(f+1)) communication.

## VI. Leaderless and Alternative Consensus Models

This section explores consensus paradigms that deviate from the traditional leader-based, total-order consensus model. It includes leaderless protocols and approaches that avoid consensus altogether, like CRDTs or specialized asset transfer systems.

### Leaderless Protocols
These protocols avoid electing a single leader to drive consensus, potentially improving fault tolerance or censorship resistance, though sometimes at the cost of complexity or latency.

*   [Leaderless Consensus](#antoniadisLeaderlessConsensus2021): Provides a definition of leaderless algorithms and presents leaderless consensus solutions for various models (shared memory, message passing).
*   [Tangle 2.0 Leaderless Nakamoto Consensus on the Heaviest DAG](#mullerTangle20Leaderless2022): Describes a leaderless consensus protocol based on a weighted DAG structure.
*   [Fast Leaderless Byzantine Total Order Broadcast](#montiFastLeaderlessByzantine2024): Presents Flutter, a fast leaderless total order broadcast protocol for partial synchrony.

### Consensus-less & CRDT Approaches
These approaches aim to achieve specific application goals (like asset transfer or state replication) without requiring full BFT consensus on a total order, often leveraging techniques like CRDTs or reliable broadcast variants.

*   [Asynchronous BFT Asset Transfer: Quasi-Anonymous, Light, and Consensus-Free](#albouyAsynchronousBFTAsset2025): An asynchronous asset transfer system that avoids total order consensus.
*   [FastPay: High-Performance Byzantine Fault Tolerant Settlement](#baudetFastPayHighPerformanceByzantine2020): A high-performance settlement system based on Byzantine Consistent Broadcast, avoiding atomic commit (consensus).
*   [Stingray: Fast Concurrent Transactions Without Consensus](#sridharStingrayFastConcurrent2025): Processes concurrent (commutative) transactions using replicated counters and fallback consensus only for contention.
*   [CryptoConcurrency: (Almost) Consensusless Asset Transfer with Shared Accounts](#tonkikhCryptoConcurrencyAlmostConsensusless2023): Allows parallel processing of non-conflicting asset transfers, resorting to consensus only for conflicts on shared accounts.
*   [Process-Commutative Distributed Objects: From Cryptocurrencies to Byzantine-Fault-Tolerant CRDTs](#freyProcessCommutativeDistributedObjects2023): Characterizes and implements distributed objects requiring only per-process FIFO ordering, bridging BFT CRDTs and ledgers.
*   [Making CRDTs Byzantine fault tolerant](#kleppmannMakingCRDTsByzantine2022): Proposes a scheme to adapt existing non-Byzantine CRDTs for Byzantine fault tolerance.
*   [The Blocklace: A Byzantine-repelling and Universal Conflict-free Replicated Data Type](#almeidaBlocklaceByzantinerepellingUniversal2024): Presents the blocklace DAG as a universal Byzantine fault-tolerant CRDT implementation capable of repelling equivocators.
*   [GOC-Ledger: State-based Conflict-Free Replicated Ledger from Grow-Only Counters](#lavoieGOCLedgerStatebasedConflictFree2023): Implements a replicated ledger as a state-based CRDT using grow-only counters, avoiding operation history reasoning.
*   [On Consensus Number 1 Objects](#khanchandaniConsensusNumber12021): Explores consensus number 1 objects, sufficient for tasks like asset transfer without needing stronger consensus primitives.

## VII. Cryptography in Consensus Systems

This section highlights papers where the choice, design, or application of cryptographic primitives (like threshold signatures, hashing, VSS, accumulators) plays a central role in the consensus protocol's efficiency, security, or features.

*   [Near-Optimal Communication Byzantine Reliable Broadcast Under a Message Adversary](#albouyNearOptimalCommunicationByzantine2025): Uses threshold signatures and vector commitments for near-optimal MBRB communication.
*   [Efficient Signature-Free Validated Agreement](#civitEfficientSignatureFreeValidated2024): Presents validated BA algorithms using only hashing (HashExt) or no cryptography (ErrorFreeExt), avoiding signatures.
*   [Making Hash-based MVBA Great Again](#fengMakingHashbasedMVBA2024): Develops an asynchronous MVBA using only hash functions, comparing performance against threshold signature-based approaches.
*   [Thresh-Hold: Assessment of Threshold Cryptography in Leader-Based Consensus](#vonseckThreshHoldAssessmentThreshold2024): Analyzes and benchmarks the impact of different threshold signature schemes (BLS, ECDSA, Schnorr) on HotStuff performance.
*   [Proofs of non-Supermajority: the missing link for two-phase BFT with responsive view-change and linear complexity](#levratProofsNonSupermajorityMissing2023): Introduces the Proofs of non-Supermajority (PnS) primitive, implementable with threshold signatures, to achieve linear complexity.
*   [Linear View Change in Optimistically Fast BFT](#rambaudLinearViewChange2022): Introduces Proofs of Exclusivity (PoE), built using threshold signatures, for linear view changes in fast-track BFT.
*   [Practical Non-interactive Multi-signatures, and a Multi-to-Aggregate Signatures Compiler](#rambaudPracticalNoninteractiveMultisignatures2024): Develops practical non-interactive multi-signatures (fNIM) and aggregate signatures (fNIA) relevant for consensus certificate aggregation and verification.

## VIII. System Design, Security, and Dynamics

This section covers practical aspects of building, verifying, securing, and evolving BFT consensus systems. It includes implementation details, formal verification efforts, analyses of attacks and defenses, support for dynamic participation, and considerations for weighted systems and sharding.

### Implementation, Verification, Attacks, Forensics, and Trusted Components
Papers focusing on the practical challenges of building secure systems, including implementation pitfalls, verification techniques, specific attacks, forensic capabilities, and the role of trusted hardware.

*   [Beyond the Whitepaper: Where BFT Consensus Protocols Meet Reality](#wongWhitepaperWhereBFT2024): Discusses lessons learned and common vulnerabilities found when implementing theoretical BFT protocols in real-world systems.
*   [Formal Verification of Blockchain Byzantine Fault Tolerance](#tholoniatFormalVerificationBlockchain2019): Illustrates vulnerabilities in blockchain consensus and formally verifies components of Red Belly Blockchain using ByMC.
*   [Liveness Attacks On HotStuff: The Vulnerability Of Timer Doubling Mechanism](#guoLivenessAttacksHotStuff2024): Identifies and demonstrates liveness attacks against HotStuff's timer doubling mechanism and proposes a fix.
*   [How Robust Are Synchronous Consensus Protocols?](#milosevicHowRobustAre2025): Analyzes attack strategies against synchronous protocols based on violating timing assumptions.
*   [BFT Protocol Forensics](#shengBFTProtocolForensics2021): Formalizes and analyzes the forensic support (ability to identify faulty replicas) of various BFT protocols like PBFT, HotStuff, Algorand, and LibraBFT.
*   [uBFT: Microsecond-Scale BFT using Disaggregated Memory](#aguileraUBFTMicrosecondScaleBFT2023): Uses disaggregated memory as a small trusted computing base to achieve low-latency BFT with 2f+1 replicas.
*   [Vivisecting the Dissection: On the Role of Trusted Components in BFT Protocols](#bessaniVivisectingDissectionRole2023): Argues for the value of trusted components (TCs) primarily for reducing replica requirements in BFT protocols.
*   [A New Broadcast Primitive for BFT Protocols](#drijversNewBroadcastPrimitive2024): Describes a practical implementation of "abortable broadcast" used in the IC, focusing on bounded resources and DoS prevention.
*   [Making CRDTs Byzantine fault tolerant](#kleppmannMakingCRDTsByzantine2022): Addresses securing CRDTs against Byzantine participants.
*   [Towards Rational Consensus in Honest Majority](#srivastavaRationalConsensusHonest2024): Considers security implications when some participants are rational (self-interested) rather than purely honest or Byzantine.

### Dynamic Membership, Reconfiguration, and Availability
Papers addressing the challenges of systems where participants can join, leave, or become temporarily unavailable, a key requirement for permissionless or long-lived systems.

*   [Foundations of Dynamic BFT](#duanFoundationsDynamicBFT2022): Provides formal definitions for dynamic BFT and presents Dyno, an efficient dynamic BFT protocol.
*   [Rondo: Scalable and Reconfiguration-Friendly Randomness Beacon](#mengRondoScalableReconfigurationFriendly2024): Presents Rondo-BFT, a dynamic BFT protocol designed to support reconfiguration for DRB applications.
*   [Reconfigurable Heterogeneous Quorum Systems](#liReconfigurableHeterogeneousQuorum2023): Provides reconfiguration protocols (join, leave, add/remove quorum) for heterogeneous quorum systems.
*   [Ouroboros Genesis: Composable Proof-of-Stake Blockchains with Dynamic Availability](#badertscherOuroborosGenesisComposable2018a): Enables nodes to join securely using only genesis information, supporting dynamic availability in PoS.
*   [Permissionless Consensus](#lewis-pyePermissionlessConsensus2024): Analyzes consensus capabilities in settings with dynamic availability and varying degrees of participant knowledge.

### Weighted Consensus, Decentralization, and Sharding
Papers exploring systems where participants have varying influence (weights, stake), analyzing the impact on decentralization, and techniques like sharding to improve overall system scale.

*   [How Does Stake Distribution Influence Consensus? Analyzing Blockchain Decentralization](#motepalliHowDoesStake2024): Analyzes stake concentration in PoS blockchains and proposes Square Root Stake Weight (SRSW) to improve decentralization metrics.
*   [Swiper: a new paradigm for efficient weighted distributed protocols](#tonkikhSwiperNewParadigm2024): Provides a general transformation from nominal (equal weight) protocols to weighted protocols efficiently using weight reduction techniques.
*   [Optimal Sharding for Scalable Blockchains with Deconstructed SMR](#zhangOptimalShardingScalable2024): Proposes Arete, a sharding protocol that deconstructs SMR to allow smaller, more resilient shards and improve scalability.

## Bibliography

### Communication Complexity of Byzantine Agreement, Revisited
<a name="abrahamCommunicationComplexityByzantine2020"></a>

**Authors:** Abraham, Ittai; Chan, T.-H. Hubert; Dolev, Danny; Nayak, Kartik; Pass, Rafael; Ren, Ling; Shi, Elaine

**Type:** Preprint
**Date:** 2020-02-15
**DOI:** [10.48550/arXiv.1805.03391](https://doi.org/10.48550/arXiv.1805.03391)
**URL:** [http://arxiv.org/abs/1805.03391](http://arxiv.org/abs/1805.03391)

**Abstract:**
> As Byzantine Agreement (BA) protocols find application in large-scale decentralized cryptocurrencies, an increasingly important problem is to design BA protocols with improved communication complexity. A few existing works have shown how to achieve subquadratic BA under an {\it adaptive} adversary. Intriguingly, they all make a common relaxation about the adaptivity of the attacker, that is, if an honest node sends a message and then gets corrupted in some round, the adversary {\it cannot erase the message that was already sent} --- henceforth we say that such an adversary cannot perform "after-the-fact removal". By contrast, many (super-)quadratic BA protocols in the literature can tolerate after-the-fact removal. In this paper, we first prove that disallowing after-the-fact removal is necessary for achieving subquadratic-communication BA. Next, we show new subquadratic binary BA constructions (of course, assuming no after-the-fact removal) that achieves near-optimal resilience and expected constant rounds under standard cryptographic assumptions and a public-key infrastructure (PKI) in both synchronous and partially synchronous settings. In comparison, all known subquadratic protocols make additional strong assumptions such as random oracles or the ability of honest nodes to erase secrets from memory, and even with these strong assumptions, no prior work can achieve the above properties. Lastly, we show that some setup assumption is necessary for achieving subquadratic multicast-based BA.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`, `foundational`

---

### uBFT: Microsecond-Scale BFT using Disaggregated Memory
<a name="aguileraUBFTMicrosecondScaleBFT2023"></a>

**Authors:** Aguilera, Marcos K.; Ben-David, Naama; Guerraoui, Rachid; Murat, Antoine; Xygkis, Athanasios; Zablotchi, Igor

**Type:** Journal Article
**Date:** 2023-01-27
**Publication:** Proceedings of the 28th ACM International Conference on Architectural Support for Programming Languages and Operating Systems, Volume 2
**Pages:** 862-877
**DOI:** [10.1145/3575693.3575732](https://doi.org/10.1145/3575693.3575732)
**URL:** [https://dl.acm.org/doi/10.1145/3575693.3575732](https://dl.acm.org/doi/10.1145/3575693.3575732)

**Abstract:**
> We propose uBFT, the first State Machine Replication (SMR) system to achieve microsecond-scale latency in data centers, while using only 2f+1 replicas to tolerate f Byzantine failures. The Byzantine Fault Tolerance (BFT) provided by uBFT is essential as pure crashes appear to be a mere illusion with real-life systems reportedly failing in many unexpected ways. uBFT relies on a small non-tailored trusted computing base—disaggregated memory—and consumes a practically bounded amount of memory. uBFT is based on a novel abstraction called Consistent Tail Broadcast, which we use to prevent equivocation while bounding memory. We implement uBFT using RDMA-based disaggregated memory and obtain an end-to-end latency of as little as 10 us. This is at least 50× faster than MinBFT, a state-of-the-art 2f+1 BFT SMR based on Intel’s SGX. We use uBFT to replicate two KV-stores (Memcached and Redis), as well as a financial order matching engine (Liquibook). These applications have low latency (up to 20 us) and become Byzantine tolerant with as little as 10 us more. The price for uBFT is a small amount of reliable disaggregated memory (less than 1 MiB), which in our prototype consists of a small number of memory servers connected through RDMA and replicated for fault tolerance.

---

### Asynchronous BFT Asset Transfer: Quasi-Anonymous, Light, and Consensus-Free
<a name="albouyAsynchronousBFTAsset2025"></a>

**Authors:** Albouy, Timothé; Anceaume, Emmanuelle; Frey, Davide; Gestin, Mathieu; Rauch, Arthur; Raynal, Michel; Taïani, François

**Type:** Preprint
**Date:** 2025-02-19
**DOI:** [10.48550/arXiv.2405.18072](https://doi.org/10.48550/arXiv.2405.18072)
**URL:** [http://arxiv.org/abs/2405.18072](http://arxiv.org/abs/2405.18072)

**Abstract:**
> This paper introduces a new asynchronous Byzantine-tolerant asset transfer system (cryptocurrency) with three noteworthy properties: quasi-anonymity, lightness, and consensus-freedom. Quasi-anonymity means no information is leaked regarding the receivers and amounts of the asset transfers. Lightness means that the underlying cryptographic schemes are \textit{succinct} (\textit{i.e.}, they produce short-sized and quickly verifiable proofs) and each process only stores its own transfers while keeping communication cost as low as possible. Consensus-freedom means the system does not rely on a total order of asset transfers. The proposed algorithm is the first asset transfer system that simultaneously fulfills all these properties in the presence of asynchrony and Byzantine processes. To obtain them, the paper adopts a modular approach combining a new distributed object called ``agreement proof'' and well-known techniques such as commitments, universal accumulators, and zero-knowledge proofs.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`, `consensusless`

---

### Near-Optimal Communication Byzantine Reliable Broadcast Under a Message Adversary
<a name="albouyNearOptimalCommunicationByzantine2025"></a>

**Authors:** Albouy, Timothé; Frey, Davide; Gelles, Ran; Hazay, Carmit; Raynal, Michel; Schiller, Elad Michael; Taïani, François; Zikas, Vassilis; Bonomi, Silvia; Galletta, Letterio; Rivière, Etienne; Schiavoni, Valerio

**Type:** Conference Paper
**Date:** 2025
**Publication:** LIPIcs, Volume 324, OPODIS 2024
**Volume:** 324
**Pages:** 14:1-14:29
**DOI:** [10.4230/LIPICS.OPODIS.2024.14](https://doi.org/10.4230/LIPICS.OPODIS.2024.14)
**URL:** [https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.OPODIS.2024.14](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.OPODIS.2024.14)

**Abstract:**
> We address the problem of Reliable Broadcast in asynchronous message-passing systems with n nodes, of which up to t are malicious (faulty), in addition to a message adversary that can drop some of the messages sent by correct (non-faulty) nodes. We present a Message-Adversary-Tolerant Byzantine Reliable Broadcast (MBRB) algorithm that communicates O(|m|+nκ) bits per node, where |m| represents the length of the application message and κ = Ω(log n) is a security parameter. This communication complexity is optimal up to the parameter κ. This significantly improves upon the state-of-the-art MBRB solution (Albouy, Frey, Raynal, and Taïani, TCS 2023), which incurs communication of O(n|m|+n²κ) bits per node. Our solution sends at most 4n² messages overall, which is asymptotically optimal. Reduced communication is achieved by employing coding techniques that replace the need for all nodes to (re-)broadcast the entire application message m. Instead, nodes forward authenticated fragments of the encoding of m using an erasure-correcting code. Under the cryptographic assumptions of threshold signatures and vector commitments, and assuming n > 3t+2d, where the adversary drops at most d messages per broadcast, our algorithm allows at least 𝓁 = n - t - (1 + ε)d (for any arbitrarily low ε > 0) correct nodes to reconstruct m, despite missing fragments caused by the malicious nodes and the message adversary.

**Tags:** `Theory of computation → Distributed algorithms`, `{Threshold} signatures`, `{Vector commitments}`, `Asynchronous message-passing`, `Byzantine fault-tolerance`, `Erasure-correction codes`, `Message adversary`, `Reliable broadcast`

---

### The Blocklace: A Byzantine-repelling and Universal Conflict-free Replicated Data Type
<a name="almeidaBlocklaceByzantinerepellingUniversal2024"></a>

**Authors:** Almeida, Paulo Sérgio; Shapiro, Ehud

**Type:** Journal Article
**Date:** 2024
**DOI:** [10.48550/ARXIV.2402.08068](https://doi.org/10.48550/ARXIV.2402.08068)
**URL:** [https://arxiv.org/abs/2402.08068](https://arxiv.org/abs/2402.08068)

**Abstract:**
> Conflict-free Replicated Data Types (CRDTs) are designed for replica convergence without global coordination or consensus. Recent work has achieved the same in a Byzantine environment, through DAG-like structures based on cryptographic hashes of content. The blocklace is a partially-ordered generalization of the blockchain in which each block has any finite number of signed hash pointers to preceding blocks. We show that the blocklace datatype, with the sole operation of adding a single block, is a CRDT: it is both a pure operation-based CRDT, with self-tagging; and a delta-state CRDT, under a slight generalization of the delta framework. Allowing arbitrary values as payload, the blocklace can also be seen as a universal Byzantine fault-tolerant implementation for arbitrary CRDTs, under the operation-based approach. Current approaches only care about CRDT convergence, being equivocation-tolerant (they do not detect or prevent equivocations), allowing a Byzantine node to cause an arbitrary amount of harm by polluting the CRDT state with an unbounded number of equivocations. We show that the blocklace can be used not only in an equivocation-tolerant way, but also so as to detect and eventually exclude Byzantine nodes, including equivocators, even under the presence of undetectable colluders. The blocklace CRDT protocol ensures that a Byzantine node may harm only a finite prefix of the computation.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`, `Data Structures and Algorithms (cs.DS)`

---

### Dynamic Probabilistic Reliable Broadcast
<a name="anikinaDynamicProbabilisticReliable2023"></a>

**Authors:** Anikina, Veronika; Bezerra, João Paulo; Kuznetsov, Petr; Schiff, Liron; Schmid, Stefan

**Type:** Conference Paper
**Date:** 2023
**DOI:** [10.48550/ARXIV.2306.04221](https://doi.org/10.48550/ARXIV.2306.04221)
**URL:** [https://arxiv.org/abs/2306.04221](https://arxiv.org/abs/2306.04221)

**Abstract:**
> Byzantine reliable broadcast is a fundamental primitive in distributed systems that allows a set of processes to agree on a message broadcast by a dedicated process, even when some of them are malicious (Byzantine). It guarantees that no two correct processes deliver different messages, and if a message is delivered by a correct process, every correct process eventually delivers one. Byzantine reliable broadcast protocols are known to scale poorly, as they require $Ω(n^2)$ message exchanges, where $n$ is the number of system members. The quadratic cost can be explained by the inherent need for every process to relay a message to every other process. In this paper, we explore ways to overcome this limitation, by casting the problem to the probabilistic setting. We propose a solution in which every broadcast message is validated by a small set of witnesses, which allows us to maintain low latency and small communication complexity. In order to tolerate the slow adaptive adversary, we dynamically select the witnesses through a novel stream-local hash function: given a stream of inputs, it generates a stream of output hashed values that adapts to small deviations of the inputs. Our performance analysis shows that the proposed solution exhibits significant scalability gains over state-of-the-art protocols.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`

---

### Leaderless Consensus
<a name="antoniadisLeaderlessConsensus2021"></a>

**Authors:** Antoniadis, Karolos; Desjardins, Antoine; Gramoli, Vincent; Guerraoui, Rachid; Zablotchi, Igor

**Type:** Journal Article
**Date:** 2021-07
**Publication:** 2021 IEEE 41st International Conference on Distributed Computing Systems (ICDCS)
**Pages:** 392-402
**DOI:** [10.1109/ICDCS51616.2021.00045](https://doi.org/10.1109/ICDCS51616.2021.00045)
**URL:** [https://ieeexplore.ieee.org/document/9546485/](https://ieeexplore.ieee.org/document/9546485/)

**Abstract:**
> Classical synchronous consensus algorithms are leaderless: processes exchange their proposals, retain the maximum value and decide when they see the same choice across a couple of rounds. Indulgent consensus algorithms are more robust in that they only require eventual synchrony, but are however typically leader-based. Intuitively, this is a weakness for a slow leader can delay any decision. This paper asks whether, under eventual synchrony, it is possible to deterministically solve consensus without a leader. The fact that the weakest failure detector to solve consensus is one that also eventually elects a leader seems to indicate that the answer to the question is negative. We prove in this paper that the answer is actually positive. We first give a precise definition of the very notion of a leaderless algorithm. Then we present three indulgent leaderless consensus algorithms, each we believe interesting in its own right: (i) for shared memory, (ii) for message passing with omission failures and (iii) for message passing with Byzantine failures (with and without authentication).

**Tags:** `foundational`

---

### Mysticeti: Reaching the Limits of Latency with Uncertified DAGs
<a name="babelMysticetiReachingLimits2024"></a>

**Authors:** Babel, Kushal; Chursin, Andrey; Danezis, George; Kichidis, Anastasios; Kokoris-Kogias, Lefteris; Koshy, Arun; Sonnino, Alberto; Tian, Mingwei

**Type:** Preprint
**Date:** 2024-07-13
**DOI:** [10.48550/arXiv.2310.14821](https://doi.org/10.48550/arXiv.2310.14821)
**URL:** [http://arxiv.org/abs/2310.14821](http://arxiv.org/abs/2310.14821)

**Abstract:**
> We introduce Mysticeti-C, the first DAG-based Byzantine consensus protocol to achieve the lower bounds of latency of 3 message rounds. Since Mysticeti-C is built over DAGs it also achieves high resource efficiency and censorship resistance. Mysticeti-C achieves this latency improvement by avoiding explicit certification of the DAG blocks and by proposing a novel commit rule such that every block can be committed without delays, resulting in optimal latency in the steady state and under crash failures. We further extend Mysticeti-C to Mysticeti-FPC, which incorporates a fast commit path that achieves even lower latency for transferring assets. Unlike prior fast commit path protocols, Mysticeti-FPC minimizes the number of signatures and messages by weaving the fast path transactions into the DAG. This frees up resources, which subsequently result in better performance. We prove the safety and liveness in a Byzantine context. We evaluate both Mysticeti protocols and compare them with state-of-the-art consensus and fast path protocols to demonstrate their low latency and resource efficiency, as well as their more graceful degradation under crash failures. Mysticeti-C is the first Byzantine consensus protocol to achieve WAN latency of 0.5s for consensus commit while simultaneously maintaining state-of-the-art throughput of over 200k TPS. Finally, we report on integrating Mysticeti-C as the consensus protocol into the Sui blockchain, resulting in over 4x latency reduction.

**Tags:** `Computer Science - Cryptography and Security`, `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### Ouroboros Genesis: Composable Proof-of-Stake Blockchains with Dynamic Availability
<a name="badertscherOuroborosGenesisComposable2018a"></a>

**Authors:** Badertscher, Christian; Gaži, Peter; Kiayias, Aggelos; Russell, Alexander; Zikas, Vassilis

**Type:** Journal Article
**Date:** 2018-10-15
**Publication:** Proceedings of the 2018 ACM SIGSAC Conference on Computer and Communications Security
**Pages:** 913-930
**DOI:** [10.1145/3243734.3243848](https://doi.org/10.1145/3243734.3243848)
**URL:** [https://dl.acm.org/doi/10.1145/3243734.3243848](https://dl.acm.org/doi/10.1145/3243734.3243848)

**Abstract:**
> We present a novel Proof-of-Stake (PoS) protocol, Ouroboros Genesis, that enables parties to safely join (or rejoin) the protocol execution using only the genesis block information. Prior to our work, PoS protocols either required parties to obtain a trusted "checkpoint" block upon joining and, furthermore, to be frequently online or required an accurate estimate of the number of online parties to be hardcoded into the protocol logic. This ability of new parties to "bootstrap from genesis" was a hallmark property of the Bitcoin blockchain and was considered an important advantage of PoW-based blockchains over PoS-based blockchains since it facilitates robust operation in a setting with dynamic availability, i.e., the natural setting---without external trusted objects such as checkpoint blocks---where parties come and go arbitrarily, may join at any moment, or remain offline for prolonged periods of time. We prove the security of Ouroboros Genesis against a fully adaptive adversary controlling less than half of the total stake in a partially synchronous network with unknown message delay and unknown, varying levels of party availability. Our security proof is in the Universally Composable setting assuming the most natural abstraction of a hash function, known as the strict Global Random Oracle (ACM-CCS 2014); this highlights an important advantage of PoS blockchains over their PoW counterparts in terms of composability with respect to the hash function formalisation: rather than a strict GRO, PoW-based protocol security requires a "local" random oracle. Finally, proving the security of our construction against an adaptive adversary requires a novel martingale technique that may be of independent interest in the analysis of blockchain protocols.

---

### FastPay: High-Performance Byzantine Fault Tolerant Settlement
<a name="baudetFastPayHighPerformanceByzantine2020"></a>

**Authors:** Baudet, Mathieu; Danezis, George; Sonnino, Alberto

**Type:** Preprint
**Date:** 2020-11-03
**DOI:** [10.48550/arXiv.2003.11506](https://doi.org/10.48550/arXiv.2003.11506)
**URL:** [http://arxiv.org/abs/2003.11506](http://arxiv.org/abs/2003.11506)

**Abstract:**
> FastPay allows a set of distributed authorities, some of which are Byzantine, to maintain a high-integrity and availability settlement system for pre-funded payments. It can be used to settle payments in a native unit of value (crypto-currency), or as a financial side-infrastructure to support retail payments in fiat currencies. FastPay is based on Byzantine Consistent Broadcast as its core primitive, foregoing the expenses of full atomic commit channels (consensus). The resulting system has low-latency for both confirmation and payment finality. Remarkably, each authority can be sharded across many machines to allow unbounded horizontal scalability. Our experiments demonstrate intra-continental confirmation latency of less than 100ms, making FastPay applicable to point of sale payments. In laboratory environments, we achieve over 80,000 transactions per second with 20 authorities---surpassing the requirements of current retail card payment networks, while significantly increasing their robustness.

**Tags:** `Computer Science - Cryptography and Security`, `consensusless`

---

### BBCA-LEDGER: High Throughput Consensus meets Low Latency | Semantic Scholar
<a name="BBCALEDGERHighThroughput"></a>

**Authors:** N/A

**Type:** Web Page
**Date:** N/A
**URL:** [https://www.semanticscholar.org/paper/BBCA-LEDGER%3A-High-Throughput-Consensus-meets-Low-Stathakopoulou-Wei/8e24ece6bf9cde87ad6e78f4217a853428f53c04](https://www.semanticscholar.org/paper/BBCA-LEDGER%3A-High-Throughput-Consensus-meets-Low-Stathakopoulou-Wei/8e24ece6bf9cde87ad6e78f4217a853428f53c04)

---

### Vivisecting the Dissection: On the Role of Trusted Components in BFT Protocols
<a name="bessaniVivisectingDissectionRole2023"></a>

**Authors:** Bessani, Alysson; Correia, Miguel; Distler, Tobias; Kapitza, Rüdiger; Esteves-Verissimo, Paulo; Yu, Jiangshan

**Type:** Journal Article
**Date:** 2023
**DOI:** [10.48550/ARXIV.2312.05714](https://doi.org/10.48550/ARXIV.2312.05714)
**URL:** [https://arxiv.org/abs/2312.05714](https://arxiv.org/abs/2312.05714)

**Abstract:**
> A recent paper by Gupta et al. (EuroSys'23) challenged the usefulness of trusted component (TC) based Byzantine fault-tolerant (BFT) protocols to lower the replica group size from $3f+1$ to $2f+1$, identifying three limitations of such protocols and proposing that TCs should be used instead to improve the performance of BFT protocols. Here, we point out flaws in both arguments and advocate that the most worthwhile use of TCs in BFT protocols is indeed to make them as resilient as crash fault-tolerant (CFT) protocols, which can tolerate up to $f$ faulty replicas using $2f+1$ replicas.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`, `Cryptography and Security (cs.CR)`

---

### Abraxas: Throughput-Efficient Hybrid Asynchronous Consensus
<a name="blumAbraxasThroughputEfficientHybrid2023"></a>

**Authors:** Blum, Erica; Katz, Jonathan; Loss, Julian; Nayak, Kartik; Ochsenreither, Simon

**Type:** Journal Article
**Date:** 2023-11-15
**Publication:** Proceedings of the 2023 ACM SIGSAC Conference on Computer and Communications Security
**Pages:** 519-533
**DOI:** [10.1145/3576915.3623191](https://doi.org/10.1145/3576915.3623191)
**URL:** [https://dl.acm.org/doi/10.1145/3576915.3623191](https://dl.acm.org/doi/10.1145/3576915.3623191)

**Abstract:**
> Protocols for state-machine replication (SMR) often trade off performance for resilience to network delay. In particular, protocols for asynchronous SMR tolerate arbitrary network delay but sacrifice throughput/latency when the network is fast, while partially synchronous protocols have good performance in a fast network but fail to make progress if the network experiences high delay. Existing hybrid protocols are resilient to arbitrary network delay and have good performance when the network is fast, but suffer from high overhead (''thrashing'') if the network repeatedly switches between being fast and slow, e.g., in a network that is typically fast but has intermittent message delays. We propose Abraxas, a generic approach for constructing a hybrid protocol from any ''fast'' protocol Πfast and asynchronous protocolΠslow to achieve (1) security and performance equivalent to Πslow under arbitrary network behavior, and (2) performance equivalent to Πfast when conditions are favorable. We instantiate Abraxas with the best existing protocols for Πfast (Jolteon) and Πslow (\mbox2-chain VABA), and show experimentally that the resulting protocol significantly outperforms Ditto, the previous state-of-the-art hybrid protocol.

---

### Generic Multicast
<a name="bolinaGenericMulticast2024"></a>

**Authors:** Bolina, Jose; Sutra, Pierre; Antunes, Douglas; Camargos, Lasaro

**Type:** Journal Article
**Date:** 2024-11-26
**Publication:** Proceedings of the 13th Latin-American Symposium on Dependable and Secure Computing
**Pages:** 81-90
**DOI:** [10.1145/3697090.3697095](https://doi.org/10.1145/3697090.3697095)
**URL:** [https://dl.acm.org/doi/10.1145/3697090.3697095](https://dl.acm.org/doi/10.1145/3697090.3697095)

**Abstract:**
> Communication primitives play a central role in modern computing. They offer a panel of reliability and ordering guarantees for messages, enabling the implementation of complex distributed interactions. In particular, atomic broadcast is a pivotal abstraction for implementing fault-tolerant distributed services. This primitive allows disseminating messages across the system in a total order. There are two group communication primitives closely related to atomic broadcast. Atomic multicast permits targeting a subset of participants, possibly stricter than the whole system. Generic broadcast leverages the semantics of messages to order them only where necessary (that is when they conflict). In this paper, we propose to combine all these primitives into a single, more general one, called generic multicast. We formally specify the guarantees offered by generic multicast and present efficient algorithms. Compared to prior works, our solutions offer appealing properties in terms of time and space complexity. In particular, when a run is conflict-free, that is no two messages conflict, a message is delivered after at most three message delays.

---

### The latest gossip on BFT consensus
<a name="buchmanLatestGossipBFT2019"></a>

**Authors:** Buchman, Ethan; Kwon, Jae; Milosevic, Zarko

**Type:** Preprint
**Date:** 2019-11-22
**DOI:** [10.48550/arXiv.1807.04938](https://doi.org/10.48550/arXiv.1807.04938)
**URL:** [http://arxiv.org/abs/1807.04938](http://arxiv.org/abs/1807.04938)

**Abstract:**
> The paper presents Tendermint, a new protocol for ordering events in a distributed network under adversarial conditions. More commonly known as Byzantine Fault Tolerant (BFT) consensus or atomic broadcast, the problem has attracted significant attention in recent years due to the widespread success of blockchain-based digital currencies, such as Bitcoin and Ethereum, which successfully solved the problem in a public setting without a central authority. Tendermint modernizes classic academic work on the subject and simplifies the design of the BFT algorithm by relying on a peer-to-peer gossip protocol among nodes.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### Snowman for partial synchrony
<a name="buchwaldSnowmanPartialSynchrony2025"></a>

**Authors:** Buchwald, Aaron; Buttolph, Stephen; Lewis-Pye, Andrew; Sekniqi, Kevin

**Type:** Conference Paper
**Date:** 2025-01-27
**URL:** [https://www.semanticscholar.org/paper/Snowman-for-partial-synchrony-Buchwald-Buttolph/16454e47ede5e3fa3814563018973892a9819822](https://www.semanticscholar.org/paper/Snowman-for-partial-synchrony-Buchwald-Buttolph/16454e47ede5e3fa3814563018973892a9819822)

**Abstract:**
> Snowman is the consensus protocol run by blockchains on Avalanche. Recent work established a rigorous proof of probabilistic consistency for Snowman in the \emph{synchronous} setting, under the simplifying assumption that correct processes execute sampling rounds in `lockstep'. In this paper, we describe a modification of the protocol that ensures consistency in the \emph{partially synchronous} setting, and when correct processes carry out successive sampling rounds at their own speed, with the time between sampling rounds determined by local message delays.

---

### Chop Chop: Byzantine Atomic Broadcast to the Network Limit
<a name="camaioniChopChopByzantine2024"></a>

**Authors:** Camaioni, Martina; Guerraoui, Rachid; Monti, Matteo; Roman, Pierre-Louis; Vidigueira, Manuel; Voron, Gauthier

**Type:** Preprint
**Date:** 2024-08-28
**DOI:** [10.48550/arXiv.2304.07081](https://doi.org/10.48550/arXiv.2304.07081)
**URL:** [http://arxiv.org/abs/2304.07081](http://arxiv.org/abs/2304.07081)

**Abstract:**
> At the heart of state machine replication, the celebrated technique enabling decentralized and secure universal computation, lies Atomic Broadcast, a fundamental communication primitive that orders, authenticates, and deduplicates messages. This paper presents Chop Chop, a Byzantine Atomic Broadcast system that uses a novel authenticated memory pool to amortize the cost of ordering, authenticating and deduplicating messages, achieving "line rate" (i.e., closely matching the complexity of a protocol that does not ensure any ordering, authentication or Byzantine resilience) even when processing messages as small as 8 bytes. Chop Chop attains this performance by means of a new form of batching we call distillation. A distilled batch is a set of messages that are fast to authenticate, deduplicate, and order. Batches are distilled using a novel interactive protocol involving brokers, an untrusted layer of facilitating processes between clients and servers. In a geo-distributed deployment of 64 medium-sized servers, Chop Chop processes 43,600,000 messages per second with an average latency of 3.6 seconds. Under the same conditions, state-of-the-art alternatives offer two orders of magnitude less throughput for the same latency. We showcase three simple Chop Chop applications: a Payment system, an Auction house and a "Pixel war" game, respectively achieving 32, 2.3 and 35 million operations per second.

**Tags:** `Computer Science - Cryptography and Security`, `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### All Byzantine Agreement Problems are Expensive
<a name="civitAllByzantineAgreement2023"></a>

**Authors:** Civit, Pierre; Gilbert, Seth; Guerraoui, Rachid; Komatovic, Jovan; Paramonov, Anton; Vidigueira, Manuel

**Type:** Journal Article
**Date:** 2023
**DOI:** [10.48550/ARXIV.2311.08060](https://doi.org/10.48550/ARXIV.2311.08060)
**URL:** [https://arxiv.org/abs/2311.08060](https://arxiv.org/abs/2311.08060)

**Abstract:**
> Byzantine agreement, arguably the most fundamental problem in distributed computing, operates among n processes, out of which t &lt; n can exhibit arbitrary failures. The problem states that all correct (non-faulty) processes must eventually decide (termination) the same value (agreement) from a set of admissible values defined by the proposals of the processes (validity). Depending on the exact version of the validity property, Byzantine agreement comes in different forms, from Byzantine broadcast to strong and weak consensus, to modern variants of the problem introduced in today's blockchain systems. Regardless of the specific flavor of the agreement problem, its communication cost is a fundamental metric whose improvement has been the focus of decades of research. The Dolev-Reischuk bound, one of the most celebrated results in distributed computing, proved 40 years ago that, at least for Byzantine broadcast, no deterministic solution can do better than Omega(t^2) exchanged messages in the worst case. Since then, it remained unknown whether the quadratic lower bound extends to seemingly weaker variants of Byzantine agreement. This paper answers the question in the affirmative, closing this long-standing open problem. Namely, we prove that any non-trivial agreement problem requires Omega(t^2) messages to be exchanged in the worst case. To prove the general lower bound, we determine the weakest Byzantine agreement problem and show, via a novel indistinguishability argument, that it incurs Omega(t^2) exchanged messages.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`, `foundational`

---

### Byzantine Consensus is Θ( n 2 ) The Dolev-Reischuk Bound is Tight even in Partial Synchrony! (Extended Version)
<a name="civitByzantineConsensus22022"></a>

**Authors:** Civit, P.; Dzulfikar, M. A.; Gilbert, S.; Gramoli, V.; Guerraoui, R.; Komatovic, J.; Vidigueira, M.

**Type:** Conference Paper
**Date:** 2022
**URL:** [https://www.semanticscholar.org/paper/Byzantine-Consensus-is-%CE%98(-n-2-)-The-Dolev-Reischuk-Civit-Dzulfikar/3f97b1c634caf4fb344bd0a134543c427f484117#extracted](https://www.semanticscholar.org/paper/Byzantine-Consensus-is-%CE%98(-n-2-)-The-Dolev-Reischuk-Civit-Dzulfikar/3f97b1c634caf4fb344bd0a134543c427f484117#extracted)

**Abstract:**
> The Dolev-Reischuk bound says that any deterministic Byzantine consensus protocol has (at least) quadratic communication complexity in the worst case. While it has been shown that the bound is tight in synchronous environments, it is still unknown whether a consensus protocol with quadratic communication complexity can be obtained in partial synchrony. Until now, the most efficient known solutions for Byzantine consensus in partially synchronous settings had cubic communication complexity (e.g., HotStuff, binary DBFT). This paper closes the existing gap by introducing SQuad, a partially synchronous Byzantine consensus protocol with quadratic worst-case communication complexity. In addition, SQuad is optimally-resilient and achieves linear worst-case latency complexity. The key technical contribution underlying SQuad lies in the way we solve view synchronization , the problem of bringing all correct processes to the same view with a correct leader for sufficiently long. Concretely, we present RareSync, a view synchronization protocol with quadratic communication complexity and linear latency complexity, which we utilize in order to obtain SQuad.

---

### Efficient Signature-Free Validated Agreement
<a name="civitEfficientSignatureFreeValidated2024"></a>

**Authors:** Civit, Pierre; Dzulfikar, Muhammad Ayaz; Gilbert, Seth; Guerraoui, Rachid; Komatovic, Jovan; Vidigueira, Manuel; Zablotchi, Igor

**Type:** Preprint
**Date:** 2024-08-20
**DOI:** [10.48550/arXiv.2403.08374](https://doi.org/10.48550/arXiv.2403.08374)
**URL:** [http://arxiv.org/abs/2403.08374](http://arxiv.org/abs/2403.08374)

**Abstract:**
> Byzantine agreement enables n processes to agree on a common L-bit value, despite up to t > 0 arbitrary failures. A long line of work has been dedicated to improving the bit complexity of Byzantine agreement in synchrony. This has culminated in COOL, an error-free (deterministically secure against a computationally unbounded adversary) solution that achieves O(nL + n^2 logn) worst-case bit complexity (which is optimal for L >= n logn according to the Dolev-Reischuk lower bound). COOL satisfies strong unanimity: if all correct processes propose the same value, only that value can be decided. Strong unanimity is, however, not sufficient for today's state machine replication (SMR) and blockchain protocols. These systems value progress and require a decided value to always be valid, excluding default decisions (such as EMPTY) even in cases where there is no unanimity a priori. Validated Byzantine agreement satisfies this property (called external validity). Yet, the best error-free (or even signature-free) validated agreement solutions achieve only O(n^2L) bit complexity, a far cry from the Omega(nL + n^2) Dolev-Reishcuk lower bound. In this paper, we present two new synchronous algorithms for validated Byzantine agreement, HashExt and ErrorFreeExt, with different trade-offs. Both algorithms are (1) signature-free, (2) optimally resilient (tolerate up to t < n / 3 failures), and (3) early-stopping (terminate in O(f+1) rounds, where f = n^2 kappa (where kappa is the size of a hash). On the other hand, ErrorFreeExt is error-free, using no cryptography whatsoever, and achieves O( (nL + n^2) logn ) bit complexity, which is near-optimal for any L.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### Every Bit Counts in Consensus
<a name="civitEveryBitCounts2023"></a>

**Authors:** Civit, Pierre; Gilbert, Seth; Guerraoui, Rachid; Komatovic, Jovan; Monti, Matteo; Vidigueira, Manuel

**Type:** Journal Article
**Date:** 2023
**DOI:** [10.48550/ARXIV.2306.00431](https://doi.org/10.48550/ARXIV.2306.00431)
**URL:** [https://arxiv.org/abs/2306.00431](https://arxiv.org/abs/2306.00431)

**Abstract:**
> Consensus enables n processes to agree on a common valid L-bit value, despite t &lt; n/3 processes being faulty and acting arbitrarily. A long line of work has been dedicated to improving the worst-case communication complexity of consensus in partial synchrony. This has recently culminated in the worst-case word complexity of O(n^2). However, the worst-case bit complexity of the best solution is still O(n^2 L + n^2 kappa) (where kappa is the security parameter), far from the Ω(n L + n^2) lower bound. The gap is significant given the practical use of consensus primitives, where values typically consist of batches of large size (L &gt; n). This paper shows how to narrow the aforementioned gap while achieving optimal linear latency. Namely, we present a new algorithm, DARE (Disperse, Agree, REtrieve), that improves upon the O(n^2 L) term via a novel dispersal primitive. DARE achieves O(n^{1.5} L + n^{2.5} kappa) bit complexity, an effective sqrt{n}-factor improvement over the state-of-the-art (when L &gt; n kappa). Moreover, we show that employing heavier cryptographic primitives, namely STARK proofs, allows us to devise DARE-Stark, a version of DARE which achieves the near-optimal bit complexity of O(n L + n^2 poly(kappa)). Both DARE and DARE-Stark achieve optimal O(n) latency.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`

---

### Strong Byzantine Agreement with Adaptive Word Complexity
<a name="civitStrongByzantineAgreement2023"></a>

**Authors:** Civit, Pierre; Gilbert, Seth; Guerraoui, Rachid; Komatovic, Jovan; Vidigueira, Manuel

**Type:** Journal Article
**Date:** 2023
**DOI:** [10.48550/ARXIV.2308.03524](https://doi.org/10.48550/ARXIV.2308.03524)
**URL:** [https://arxiv.org/abs/2308.03524](https://arxiv.org/abs/2308.03524)

**Abstract:**
> The strong Byzantine agreement (SBA) problem is defined among n processes, out of which t &lt; n can be faulty and behave arbitrarily. SBA allows correct (non-faulty) processes to agree on a common value. Moreover, if all correct processes have proposed the same value, only that value can be agreed upon. It has been known for a long time that any solution to the SBA problem incurs quadratic worst-case word complexity; additionally, the bound was known to be tight. However, no existing protocol achieves adaptive word complexity, where the number of exchanged words depends on the actual number of faults, and not on the upper bound. Therefore, it is still unknown whether SBA with adaptive word complexity exists. This paper answers the question in the affirmative. Namely, we introduce STRONG, a synchronous protocol that solves SBA among n = (2 + Omega(1))t + 1 processes and achieves adaptive word complexity. We show that the fundamental challenge of adaptive SBA lies in efficiently solving certification, the problem of obtaining a constant-sized, locally-verifiable proof that a value can safely be decided.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`

---

### Make Every Word Count: Adaptive Byzantine Agreement with Fewer Words
<a name="cohenMakeEveryWord2023"></a>

**Authors:** Cohen, Shir; Keidar, Idit; Spiegelman, Alexander; Hillel, Eshcar; Palmieri, Roberto; Rivière, Etienne

**Type:** Conference Paper
**Date:** 2023
**Publication:** LIPIcs, Volume 253, OPODIS 2022
**Volume:** 253
**Pages:** 18:1-18:21
**DOI:** [10.4230/LIPICS.OPODIS.2022.18](https://doi.org/10.4230/LIPICS.OPODIS.2022.18)
**URL:** [https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.OPODIS.2022.18](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.OPODIS.2022.18)

**Abstract:**
> Byzantine Agreement (BA) is a key component in many distributed systems. While Dolev and Reischuk have proven a long time ago that quadratic communication complexity is necessary for worst-case runs, the question of what can be done in practically common runs with fewer failures remained open. In this paper we present the first Byzantine Broadcast algorithm with O(n(f+1)) communication complexity in a model with resilience of n = 2t+1, where 0 ≤ f ≤ t is the actual number of process failures in a run. And for BA with strong unanimity, we present the first optimal-resilience algorithm that has linear communication complexity in the failure-free case and a quadratic cost otherwise.

**Tags:** `Theory of computation → Distributed algorithms`, `Adaptive communication`, `Byzantine Agreement`, `Byzantine Broadcast`

---

### Ipotane: Achieving the Best of All Worlds in Asynchronous BFT
<a name="daiIpotaneAchievingBest2024"></a>

**Authors:** Dai, Xiaohai; Ding, Chaozheng; Jin, Hai; Loss, Julian; Ren, Ling

**Type:** Journal Article
**Date:** 2024
**Publication:** IACR Cryptol. ePrint Arch.
**URL:** [https://www.semanticscholar.org/paper/Ipotane%3A-Achieving-the-Best-of-All-Worlds-in-BFT-Dai-Ding/9baa25d3f703f1c89b2c768f344029c91648365a](https://www.semanticscholar.org/paper/Ipotane%3A-Achieving-the-Best-of-All-Worlds-in-BFT-Dai-Ding/9baa25d3f703f1c89b2c768f344029c91648365a)

**Abstract:**
> —State-of-the-art asynchronous Byzantine Fault Tolerance (BFT) protocols integrate a partially-synchronous optimistic path. The holy grail in this paradigm is to match the performance of a partially-synchronous protocol in favorable situations and match the performance of a purely asynchronous protocol in unfavorable situations. Several prior works have made progress toward this goal by matching the efficiency of a partially-synchronous protocol in favorable conditions. However, their performance compared to purely asynchronous protocols is reduced when network conditions are unfavorable. To address these shortcomings, a recent work, Abraxas (CCS '23), presents the first optimistic asynchronous BFT protocol that retains stable throughput in all situations. However, Abraxas still incurs very high worst-case latency in unfavorable situations because it is slow at detecting the failure of its optimistic path. Another recent work, ParBFT (CCS '23) guarantees good latency in all situations, but suffers from reduced throughput in unfavorable situations due to its use of extra Asynchronous Binary Agreement (ABA) instances. To approach our holy grail, we propose Ipotane, which delivers performance comparable to partially-synchronous protocols in favorable situations, and attains performance on par with purely asynchronous protocols in unfavorable situations— in both throughput and latency. Ipotane also runs the two paths simultaneously. It adopts two-chain HotStuff as the optimistic path, thus achieving high performance in favorable situations. As for the pessimistic path, we introduce a new primitive Dual-functional Byzantine Agreement (DBA), which packs the functionalities of biased ABA and Validated Asynchronous Byzantine Agreement (VABA). Ipotane runs DBA instances continuously as the pessimistic path. DBA’s ABA functionality quickly detects the optimistic path’s failure, ensuring Ipotane’s low latency in unfavorable situations. Meanwhile, the VABA functionality continuously produces blocks, maintaining Ipotane’s high throughput. Additionally, the biased property ensures that blocks committed via the optimistic path are respected by DBA instances, guaranteeing consistency across two paths. We conduct extensive experiments to demonstrate that Ipotane achieves high through-put and low latency in all situations.

---

### LightDAG: A Low-latency DAG-based BFT Consensus through Lightweight Broadcast
<a name="daiLightDAGLowlatencyDAGbased2024"></a>

**Authors:** Dai, Xiaohai; Wang, Guanxiong; Xiao, Jiang; Guo, Zhengxuan; Hao, Rui; Xie, Xia; Jin, Hai

**Type:** Journal Article
**Date:** 2024-5-27
**Publication:** 2024 IEEE International Parallel and Distributed Processing Symposium (IPDPS)
**Pages:** 998-1008
**DOI:** [10.1109/IPDPS57955.2024.00093](https://doi.org/10.1109/IPDPS57955.2024.00093)
**URL:** [https://ieeexplore.ieee.org/document/10579243/](https://ieeexplore.ieee.org/document/10579243/)

**Abstract:**
> To improve the throughput of Byzantine Fault Tolerance (BFT) consensus protocols, the Directed Acyclic Graph (DAG) topology has been introduced to parallel data processing, leading to the development of DAG-based BFT consensus. However, existing DAG-based works heavily rely on Reliable Broadcast (RBC) protocols for block broadcasting, which introduces significant latency due to the three communication steps involved in each RBC. For instance, DAGRider, a representative DAG-based protocol, exhibits the best latency of 12 steps, considerably higher than non-DAG protocols like PBFT, which only requires 3 steps. To tackle this issue, we propose LightDAG, which replaces RBC with lightweight broadcasting protocols such as Consistent Broadcast (CBC) and Plain Broadcast (PBC). Since CBC and PBC can be implemented in two and one communication steps, respectively, LightDAG achieves low latency.In our proposal, we present two variants of LightDAG, namely LightDAG1 and LightDAG2, each providing a trade-off between the best latency and the expected worst latency. In LightDAG1, every block is broadcast using CBC, which exhibits a best latency of 5 steps and an expected worst latency of 14 steps. Since CBC cannot guarantee the totality property, we design a block retrieval mechanism in LightDAG1 to assist replicas in retrieving missing blocks. LightDAG2 utilizes a combination of PBC and CBC for block broadcasting, resulting in the best latency of 4 steps and an expected worst latency of 12(t+1) steps, where t represents the number of actual Byzantine replicas. Since a Byzantine replica may equivocate through PBC, LightDAG2 prohibits blocks from directly referencing contradictory blocks. To ensure liveness, we propose a mechanism to identify and exclude Byzantine replicas if they engage in equivocation attacks. Extensive experiments have been conducted to evaluate LightDAG, and the results demonstrate its feasibility and efficiency.

---

### ParBFT: Faster Asynchronous BFT Consensus with a Parallel Optimistic Path
<a name="daiParBFTFasterAsynchronous2023"></a>

**Authors:** Dai, Xiaohai; Zhang, Bolin; Jin, Hai; Ren, Ling

**Type:** Journal Article
**Date:** 2023-11-15
**Publication:** Proceedings of the 2023 ACM SIGSAC Conference on Computer and Communications Security
**Pages:** 504-518
**DOI:** [10.1145/3576915.3623101](https://doi.org/10.1145/3576915.3623101)
**URL:** [https://dl.acm.org/doi/10.1145/3576915.3623101](https://dl.acm.org/doi/10.1145/3576915.3623101)

**Abstract:**
> To reduce latency and communication overhead of asynchronous Byzantine Fault Tolerance (BFT) consensus, an optimistic path is often added, with Ditto and BDT as state-of-the-art representatives. These protocols first attempt to run an optimistic path that is typically adapted from partially-synchronous BFT and promises good performance in good situations. If the optimistic path fails to make progress, these protocols switch to a pessimistic path after a timeout, to guarantee liveness in an asynchronous network. This design crucially relies on an accurate estimation of the network delay Δ to set the timeout parameter correctly. A wrong estimation of Δ can lead to either premature or delayed switching to the pessimistic path, hurting the protocol's efficiency in both cases. To address the above issue, we propose ParBFT, which employs a parallel optimistic path. As long as the leader of the optimistic path is non-faulty, ParBFT ensures low latency without requiring an accurate estimation of the network delay. We propose two variants of ParBFT, namely ParBFT1 and ParBFT2, with a trade-off between latency and communication. ParBFT1 simultaneously launches the two paths, achieves lower latency under a faulty leader, but has a quadratic message complexity even in good situations. ParBFT2 reduces the message complexity in good situations by delaying the pessimistic path, at the cost of a higher latency under a faulty leader. Experimental results demonstrate that ParBFT outperforms Ditto or BDT. In particular, when the network condition is bad, ParBFT can reach consensus through the optimistic path, while Ditto and BDT suffer from path switching and have to make progress using the pessimistic path.

---

### Remora: A Low-Latency DAG-Based BFT Through Optimistic Paths
<a name="daiRemoraLowLatencyDAGBased2025"></a>

**Authors:** Dai, Xiaohai; Li, Wei; Wang, Guanxiong; Xiao, Jiang; Chen, Haoyang; Li, Shufei; Zomaya, Albert Y.; Jin, Hai

**Type:** Journal Article
**Date:** 2025-01
**Publication:** IEEE Transactions on Computers
**Volume:** 74
**Issue:** 1
**Pages:** 57-70
**DOI:** [10.1109/TC.2024.3461309](https://doi.org/10.1109/TC.2024.3461309)
**URL:** [https://ieeexplore.ieee.org/document/10680428/](https://ieeexplore.ieee.org/document/10680428/)

**Abstract:**
> Standing as a foundational element within blockchain systems, the Byzantine Fault Tolerant (BFT) consensus has garnered significant attention over the past decade. The introduction of a Directed Acyclic Directed (DAG) structure into BFT consensus design, termed DAG-based BFT, has emerged to bolster throughput. However, prevalent DAG-based protocols grapple with substantial latency issues, suffering from a latency gap compared to non-DAG protocols. For instance, leading-edge DAG-based protocols named GradedDAG and BullShark exhibit a good-case latency of $4$4 and $6$6 communication rounds, respectively. In contrast, the non-DAG protocol, exemplified by PBFT, attains a latency of $3$3 rounds in favorable conditions. To bridge this latency gap, we propose Remora, a novel DAG-based BFT protocol. Remora achieves a reduced latency of $3$3 rounds by incorporating optimistic paths. At its core, Remora endeavors to commit blocks through the optimistic path initially, facilitating low latency in favorable situations. Conversely, in unfavorable scenarios, Remora seamlessly transitions to a pessimistic path to ensure liveness. Various experiments validate Remora's feasibility and efficiency, highlighting its potential as a robust solution in the realm of BFT consensus protocols.

---

### Wahoo: A DAG-Based BFT Consensus With Low Latency and Low Communication Overhead
<a name="daiWahooDAGBasedBFT2024"></a>

**Authors:** Dai, Xiaohai; Zhang, Zhaonan; Guo, Zhengxuan; Ding, Chaozheng; Xiao, Jiang; Xie, Xia; Hao, Rui; Jin, Hai

**Type:** Journal Article
**Date:** 2024
**Publication:** IEEE Transactions on Information Forensics and Security
**Volume:** 19
**Pages:** 7508-7522
**DOI:** [10.1109/TIFS.2024.3409082](https://doi.org/10.1109/TIFS.2024.3409082)
**URL:** [https://ieeexplore.ieee.org/document/10547048/](https://ieeexplore.ieee.org/document/10547048/)

**Abstract:**
> To parallelize data processing within BFT consensus protocols, Directed Acyclic Graph (DAG) structures have been integrated into consensus design, shaping the realm of DAG-based BFT protocols. Existing DAG-based protocols rely on the Reliable Broadcast (RBC) protocol or its variants for block dissemination, which ensures consistency and totality properties of the data delivery. However, the inherent communication overhead of  $O(n^{2})$  in RBC (where n is the total replica count) results in an unwieldy  $O(n^{3})$  overhead in current DAG-based solutions, as each replica disseminates blocks through RBC in parallel. In response to this issue, we propose two new broadcast protocols: Provable Broadcast (PBC) and Enhanced Provable Broadcast (EPBC). Both PBC and EPBC maintain the consistency property of data delivery, similar to RBC, while offering linear communication overhead without totality. Leveraging these broadcast protocols, we devise Wahoo, a novel DAG-based BFT protocol that significantly reduces communication overhead to  $O(n^{2})$ . To address the absence of the totality property, we introduce a block retrieval mechanism to assist replicas in acquiring missing blocks. Additionally, under favorable conditions, Wahoo achieves a low latency of  $4\delta $  (where  $\delta $  symbolizes the actual network delay), rivaling the best performance of existing DAG-based protocols. Various experiments showcase Wahoo’s high performance, owing to its substantially reduced communication overhead.

---

### Narwhal and Tusk: A DAG-based Mempool and Efficient BFT Consensus
<a name="danezisNarwhalTuskDAGbased2022"></a>

**Authors:** Danezis, George; Kogias, Eleftherios Kokoris; Sonnino, Alberto; Spiegelman, Alexander

**Type:** Preprint
**Date:** 2022-03-16
**DOI:** [10.48550/arXiv.2105.11827](https://doi.org/10.48550/arXiv.2105.11827)
**URL:** [http://arxiv.org/abs/2105.11827](http://arxiv.org/abs/2105.11827)

**Abstract:**
> We propose separating the task of reliable transaction dissemination from transaction ordering, to enable high-performance Byzantine fault-tolerant quorum-based consensus. We design and evaluate a mempool protocol, Narwhal, specializing in high-throughput reliable dissemination and storage of causal histories of transactions. Narwhal tolerates an asynchronous network and maintains high performance despite failures. Narwhal is designed to easily scale-out using multiple workers at each validator, and we demonstrate that there is no foreseeable limit to the throughput we can achieve. Composing Narwhal with a partially synchronous consensus protocol (Narwhal-HotStuff) yields significantly better throughput even in the presence of faults or intermittent loss of liveness due to asynchrony. However, loss of liveness can result in higher latency. To achieve overall good performance when faults occur we design Tusk, a zero-message overhead asynchronous consensus protocol, to work with Narwhal. We demonstrate its high performance under a variety of configurations and faults. As a summary of results, on a WAN, Narwhal-Hotstuff achieves over 130,000 tx/sec at less than 2-sec latency compared with 1,800 tx/sec at 1-sec latency for Hotstuff. Additional workers increase throughput linearly to 600,000 tx/sec without any latency increase. Tusk achieves 160,000 tx/sec with about 3 seconds latency. Under faults, both protocols maintain high throughput, but Narwhal-HotStuff suffers from increased latency.

**Tags:** `Computer Science - Cryptography and Security`, `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### Asynchronous Data Dissemination and its Applications
<a name="dasAsynchronousDataDissemination2021"></a>

**Authors:** Das, Sourav; Xiang, Zhuolun; Ren, Ling

**Type:** Conference Paper
**Date:** 2021-11-13
**Publication:** Proceedings of the 2021 ACM SIGSAC Conference on Computer and Communications Security
**Pages:** 2705–2721
**DOI:** [10.1145/3460120.3484808](https://doi.org/10.1145/3460120.3484808)
**URL:** [https://doi.org/10.1145/3460120.3484808](https://doi.org/10.1145/3460120.3484808)

**Abstract:**
> In this paper, we introduce the problem of Asynchronous Data Dissemination (ADD). Intuitively, an ADD protocol disseminates a message to all honest nodes in an asynchronous network, given that at least t+1 honest nodes initially hold the message where t is the maximum number of malicious nodes. We design a simple and efficient ADD protocol for n parties that is information-theoretically secure, tolerates up to one-third malicious nodes, and has a communication cost of O(n|M|+n2) for disseminating a message M. We then use our ADD protocol to improve many important primitives in cryptography and distributed computing. For asynchronous reliable broadcast (RBC), assuming collision-resistant hash functions, we give a RBC protocol with communication cost O(n|M| + κ n2) where κ is the size of the hash function output. This improves over the prior best scheme with communication cost O(n|M| + κ n2 łog n) under the same setting. Our improved RBC protocol immediately improves the communication cost of asynchronous atomic broadcast and Asynchronous Distributed Key Generation (ADKG) protocols. We also use our improved RBC protocol along with additional new techniques to improve the communication cost of Asynchronous Verifiable Secret Sharing (AVSS), Asynchronous Complete Secret Sharing (ACSS), and dual-threshold ACSS from O(κ n2 łog n) to O(κ n2) without using any trusted setup.

---

### A New Broadcast Primitive for BFT Protocols
<a name="drijversNewBroadcastPrimitive2024"></a>

**Authors:** Drijvers, Manu; Gretler, Tim; Harchol, Yotam; Klenze, Tobias; Maric, Ognjen; Neamtu, Stefan; Pignolet, Yvonne-Anne; Rumenov, Rostislav; Sharifi, Daniel; Shoup, Victor

**Type:** Preprint
**Date:** 2024-10-30
**DOI:** [10.48550/arXiv.2410.22080](https://doi.org/10.48550/arXiv.2410.22080)
**URL:** [http://arxiv.org/abs/2410.22080](http://arxiv.org/abs/2410.22080)

**Abstract:**
> Byzantine fault tolerant (BFT) protocol descriptions often assume application-layer networking primitives, such as best-effort and reliable broadcast, which are impossible to implement in practice in a Byzantine environment as they require either unbounded buffering of messages or giving up liveness, under certain circumstances. However, many of these protocols do not (or can be modified to not) need such strong networking primitives. In this paper, we define a new, slightly weaker networking primitive that we call abortable broadcast. We describe an implementation of this new primitive and show that it (1) still provides strong delivery guarantees, even in the case of network congestion, link or peer failure, and backpressure, (2) preserves bandwidth, and (3) enforces all data structures to be bounded even in the presence of malicious peers. The latter prevents out-of-memory DoS attacks by malicious peers, an issue often overlooked in the literature. The new primitive and its implementation are not just theoretical. We use them to implement the BFT protocols in the IC (Internet Computer), a publicly available blockchain network that enables replicated execution of general-purpose computation, serving hundreds of thousands of applications and their users.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`, `Computer Science - Networking and Internet Architecture`

---

### Foundations of Dynamic BFT
<a name="duanFoundationsDynamicBFT2022"></a>

**Authors:** Duan, Sisi; Zhang, Haibin

**Type:** Preprint
**Date:** 2022
**URL:** [https://eprint.iacr.org/2022/597](https://eprint.iacr.org/2022/597)

**Abstract:**
> This paper studies dynamic BFT, where replicas can join and leave the system dynamically, a primitive that is nowadays increasingly needed. We provide a formal treatment for dynamic BFT protocols, endowing them with a flexible syntax and various security definitions.

We demonstrate the challenges of extending static BFT to dynamic BFT. Then we design and implement Dyno, a highly efficient dynamic BFT protocol under the partial synchrony model. We show that Dyno can seamlessly handle membership changes without incurring performance degradation.

**Tags:** `atomic broadcast`, `BFT`, `Byzantine fault tolerance`, `consortium blockchains`, `definitions`, `dynamic BFT`, `dynamic membership`, `failures`, `fault tolerance`, `foundations`, `hybrid blockchains`, `reconfiguration`

---

### Dynamically available consensus on a DAG with fast confirmation for UTXO transactions | Semantic Scholar
<a name="DynamicallyAvailableConsensus"></a>

**Authors:** N/A

**Type:** Web Page
**Date:** N/A
**URL:** [https://www.semanticscholar.org/paper/Dynamically-available-consensus-on-a-DAG-with-fast-Polyanskii/c59e9f034766f72bf11d40a33c503a21fb5e89ab](https://www.semanticscholar.org/paper/Dynamically-available-consensus-on-a-DAG-with-fast-Polyanskii/c59e9f034766f72bf11d40a33c503a21fb5e89ab)

---

### Faster Asynchronous Blockchain Consensus and MVBA
<a name="FasterAsynchronousBlockchain"></a>

**Authors:** N/A

**Type:** Web Page
**Date:** N/A
**URL:** [https://www.semanticscholar.org/paper/Faster-Asynchronous-Blockchain-Consensus-and-MVBA-Rambaud/8472e1632b1f372296b8cd3f64f7ebb71641576b](https://www.semanticscholar.org/paper/Faster-Asynchronous-Blockchain-Consensus-and-MVBA-Rambaud/8472e1632b1f372296b8cd3f64f7ebb71641576b)

**Abstract:**
> Blockchain consensus, a.k.a. BFT SMR, are protocols enabling n processes to decide on an ever-growing chain. The fastest known asynchronous one is called 2-chain VABA (PODC’21 and FC’22), and is used as fallback chain in Abraxas* (CCS’23). It has a claimed 9 . 5 δ expected latency when used for a single shot instance, a.k.a. an MVBA. We exhibit attacks breaking it. Hence, the title of the fastest asynchronous MVBA with quadratic messages complexity goes to sMVBA (CCS’22), with 10 δ expected latency. Our positive contributions are two new and complementary designs.

---

### Making Hash-based MVBA Great Again
<a name="fengMakingHashbasedMVBA2024"></a>

**Authors:** Feng, Hanwen; Lu, Zhenliang; Mai, Tiancheng; Tang, Qiang

**Type:** Journal Article
**Date:** 2024
**Publication:** IACR Cryptol. ePrint Arch.
**URL:** [https://www.semanticscholar.org/paper/Making-Hash-based-MVBA-Great-Again-Feng-Lu/a45a06dc78f2b755926e1b4261ba6dc594f088a0](https://www.semanticscholar.org/paper/Making-Hash-based-MVBA-Great-Again-Feng-Lu/a45a06dc78f2b755926e1b4261ba6dc594f088a0)

**Abstract:**
> Multi-valuedValidatedAsynchronousByzantineAgreement( MVBA ) is one essential primitive for many distributed protocols, such as asynchronous Byzantine fault-tolerant scenarios like atomic broadcast ( ABC ), asynchronous distributed key generation, and many others. Recent efforts (Lu et al, PODC’ 20) have pushed the communication complexity of MVBA to optimal O( ℓ𝑛 + 𝜆𝑛 2 ) , which, however, heavily rely on “heavyweight” cryptographic tools, such as non-interactive threshold signatures. The computational cost of algebraic operations, the susceptibility to quantum attacks, and the necessity of a trusted setup associated with threshold signatures present significant remaining challenges. There is a growing interest in information-theoretic or hash-based constructions (historically called signature-free constructions). Unfortunately, the state-of-the-art hash-based MVBA (Duan et al., CCS’23) incurs a large O( ℓ𝑛 2 + 𝜆𝑛 3 ) -bits communication, which in turn makes the hash-based MVBA inferior performance-wise comparing with the “classical” ones. Indeed, this was clearly demonstrated in our experimental evaluations. To make hash-based MVBA actually realize its full potential, in this paper, we introduce an MVBA with adaptive security, and (cid:101) O( ℓ𝑛 + 𝜆𝑛 2 ) communication, exclusively leveraging conventional hash functions. Our new MVBA achieves nearly optimal communication, devoid of heavy operations, surpassing both threshold signature-based schemes and the hash-based scheme in many practical settings, as demonstrated in our experiments. For example, in scenarios with a network size of 𝑛 = 201 and an input size of 1 . 75 MB, our MVBA exhibits a latency that is 81% lower than that of the existing hash-based MVBA and 47% lower than the threshold signature-based MVBA . Our new construction also achieves optimal parameters in other metrics such as O( 1 ) rounds and O( 𝑛 2 ) message complexity, except with a sub-optimal resilience, tolerating up to 20% Byzantine corruptions (instead of 33%). Given its practical performance advantages, our new hash-based MVBA naturally leads to better asynchronous distributed protocols, by simply plugging it into existing frameworks.

---

### Process-Commutative Distributed Objects: From Cryptocurrencies to Byzantine-Fault-Tolerant CRDTs
<a name="freyProcessCommutativeDistributedObjects2023"></a>

**Authors:** Frey, Davide; Guillou, Lucie; Raynal, Michel; Taïani, François

**Type:** Journal Article
**Date:** 2023
**DOI:** [10.48550/ARXIV.2311.13936](https://doi.org/10.48550/ARXIV.2311.13936)
**URL:** [https://arxiv.org/abs/2311.13936](https://arxiv.org/abs/2311.13936)

**Abstract:**
> This paper explores the territory that lies between best-effort Byzantine-Fault-Tolerant Conflict-free Replicated Data Types (BFT CRDTs) and totally ordered distributed ledgers, such as those implemented by Blockchains. It formally characterizes a novel class of distributed objects that only requires a First In First Out (FIFO) order on the object operations from each process (taken individually). The formalization leverages Mazurkiewicz traces to define legal sequences of operations and ensure both Strong Eventual Consistency (SEC) and Pipleline Consistency (PC). The paper presents a generic algorithm that implements this novel class of distributed objects both in a crash- and Byzantine setting. It also illustrates the practical interest of the proposed approach using four instances of this class of objects, namely money transfer, Petri nets, multi-sets, and concurrent work stealing dequeues.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`

---

### Jolteon and Ditto: Network-Adaptive Efficient Consensus with Asynchronous Fallback
<a name="gelashviliJolteonDittoNetworkAdaptive2022"></a>

**Authors:** Eyal, Ittay; Garay, Juan; Gelashvili, Rati; Kokoris-Kogias, Lefteris; Sonnino, Alberto; Spiegelman, Alexander; Xiang, Zhuolun

**Type:** Journal Article
**Date:** 2022
**Volume:** 13411
**Pages:** 296-315
**DOI:** [10.1007/978-3-031-18283-9_14](https://doi.org/10.1007/978-3-031-18283-9_14)
**URL:** [https://link.springer.com/10.1007/978-3-031-18283-9_14](https://link.springer.com/10.1007/978-3-031-18283-9_14)

**Abstract:**
> Existing committee-based Byzantine state machine replication (SMR) protocols, typically deployed in production blockchains, face a clear trade-off: (1) they either achieve linear communication cost in the happy path, but sacrifice liveness during periods of asynchrony, or (2) they are robust (progress with probability one) but pay quadratic communication cost. We believe this trade-off is unwarranted since existing linear protocols still have asymptotic quadratic cost in the worst case. We design Ditto, a Byzantine SMR protocol that enjoys the best of both worlds: optimal communication on and off the happy path (linear and quadratic, respectively) and progress guarantee under asynchrony and DDoS attacks. We achieve this by replacing the view-synchronization of partially synchronous protocols with an asynchronous fallback mechanism at no extra asymptotic cost. Specifically, we start from HotStuff, a state-of-the-art linear protocol, and gradually build Ditto. As a separate contribution and an intermediate step, we design a 2-chain version of HotStuff, Jolteon, which leverages a quadratic view-change mechanism to reduce the latency of the standard 3-chain HotStuff. We implement and experimentally evaluate all our systems. Notably, Jolteon's commit latency outperforms HotStuff by 200-300ms with varying system size. Additionally, Ditto adapts to the network and provides better performance than Jolteon under faulty conditions and better performance than VABA (a state-of-the-art asynchronous protocol) under faultless conditions. This proves our case that breaking the robustness-efficiency trade-off is in the realm of practicality.

---

### Autobahn: Seamless high speed BFT
<a name="giridharanAutobahnSeamlessHigh2025"></a>

**Authors:** Giridharan, Neil; Suri-Payer, Florian; Abraham, Ittai; Alvisi, Lorenzo; Crooks, Natacha

**Type:** Preprint
**Date:** 2025-01-20
**DOI:** [10.48550/arXiv.2401.10369](https://doi.org/10.48550/arXiv.2401.10369)
**URL:** [http://arxiv.org/abs/2401.10369](http://arxiv.org/abs/2401.10369)

**Abstract:**
> Today's practical, high performance Byzantine Fault Tolerant (BFT) consensus protocols operate in the partial synchrony model. However, existing protocols are inefficient when deployments are indeed partially synchronous. They deliver either low latency during fault-free, synchronous periods (good intervals) or robust recovery from events that interrupt progress (blips). At one end, traditional, view-based BFT protocols optimize for latency during good intervals, but, when blips occur, can suffer from performance degradation (hangovers) that can last beyond the return of a good interval. At the other end, modern DAG-based BFT protocols recover more gracefully from blips, but exhibit lackluster latency during good intervals. To close the gap, this work presents Autobahn, a novel high-throughput BFT protocol that offers both low latency and seamless recovery from blips. By combining a highly parallel asynchronous data dissemination layer with a low-latency, partially synchronous consensus mechanism, Autobahn (i) avoids the hangovers incurred by traditional BFT protocols and (ii) matches the throughput of state of the art DAG-based BFT protocols while cutting their latency in half, matching the latency of traditional BFT protocols.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### Simplicial Models for the Epistemic Logic of Faulty Agents
<a name="goubaultSimplicialModelsEpistemic2023"></a>

**Authors:** Goubault, Eric; Kniazev, Roman; Ledent, Jeremy; Rajsbaum, Sergio

**Type:** Preprint
**Date:** 2023-11-14
**DOI:** [10.48550/arXiv.2311.01351](https://doi.org/10.48550/arXiv.2311.01351)
**URL:** [http://arxiv.org/abs/2311.01351](http://arxiv.org/abs/2311.01351)

**Abstract:**
> In recent years, several authors have been investigating simplicial models, a model of epistemic logic based on higher-dimensional structures called simplicial complexes. In the original formulation, simplicial models were always assumed to be pure, meaning that all worlds have the same dimension. This is equivalent to the standard S5n semantics of epistemic logic, based on Kripke models. By removing the assumption that models must be pure, we can go beyond the usual Kripke semantics and study epistemic logics where the number of agents participating in a world can vary. This approach has been developed in a number of papers, with applications in fault-tolerant distributed computing where processes may crash during the execution of a system. A difficulty that arises is that subtle design choices in the definition of impure simplicial models can result in different axioms of the resulting logic. In this paper, we classify those design choices systematically, and axiomatize the corresponding logics. We illustrate them via distributed computing examples of synchronous systems where processes may crash.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`, `Computer Science - Artificial Intelligence`, `Computer Science - Logic in Computer Science`, `Mathematics - Algebraic Topology`

---

### The information structure of indulgent consensus
<a name="guerraouiInformationStructureIndulgent2004"></a>

**Authors:** Guerraoui, R.; Raynal, M.

**Type:** Journal Article
**Date:** 2004-04
**Publication:** IEEE Transactions on Computers
**Volume:** 53
**Issue:** 4
**Pages:** 453-466
**DOI:** [10.1109/TC.2004.1268403](https://doi.org/10.1109/TC.2004.1268403)
**URL:** [http://ieeexplore.ieee.org/document/1268403/](http://ieeexplore.ieee.org/document/1268403/)

**Abstract:**
> To solve consensus, distributed systems have to be equipped with oracles such as a failure detector, a leader capability, or a random number generator. For each oracle, various consensus algorithms have been devised. Some of these algorithms are indulgent toward their oracle in the sense that they never violate consensus safety, no matter how the underlying oracle behaves. We present a simple and generic indulgent consensus algorithm that can be instantiated with any specific oracle and be as efficient as any ad hoc consensus algorithm initially devised with that oracle in mind. The key to combining genericity and efficiency is to factor out the information structure of indulgent consensus executions within a new distributed abstraction, which we call "Lambda". Interestingly, identifying this information structure also promotes a fine-grained study of the inherent complexity of indulgent consensus. We show that instantiations of our generic algorithm with specific oracles, or combinations of them, match lower bounds on oracle-efficiency, zero-degradation, and one-step-decision. We show, however, that no leader or failure detector-based consensus algorithm can be, at the same time, zero-degrading and configuration-efficient. Moreover, we show that leader-based consensus algorithms that are oracle-efficient are inherently zero-degrading, but some failure detector-based consensus algorithms can be both oracle-efficient and configuration-efficient. These results highlight some of the fundamental trade offs underlying each oracle.

---

### Liveness Attacks On HotStuff: The Vulnerability Of Timer Doubling Mechanism
<a name="guoLivenessAttacksHotStuff2024"></a>

**Authors:** Guo, Kaiwen; Hu, Kexin; Zhang, Zhenfeng

**Type:** Journal Article
**Date:** 2024-08-11
**Publication:** The Computer Journal
**Volume:** 67
**Issue:** 8
**Pages:** 2586-2600
**DOI:** [10.1093/comjnl/bxae027](https://doi.org/10.1093/comjnl/bxae027)
**URL:** [https://academic.oup.com/comjnl/article/67/8/2586/7634133](https://academic.oup.com/comjnl/article/67/8/2586/7634133)

**Abstract:**
> Abstract
            Byzantine fault-tolerant (BFT) consensus protocols are essential in distributed computing. Most partially synchronous BFT protocols proceed in views and rely on a view synchronizer module to guarantee liveness by synchronizing honest replicas to the same view. HotStuff is a leading BFT consensus protocol known for achieving linear view change and optimistic responsiveness. To achieve these desirable properties, HotStuff relies on a candidate solution for the view synchronizer based on a recomposed timer doubling mechanism. However, a formal analysis of this mechanism is currently lacking. This paper delves into HotStuff with the recomposed timer doubling mechanism. To facilitate accurate analysis, we introduce a new specification for the view synchronizer, incorporating two paths for view switching as in HotStuff’s setting. Surprisingly, we observe that the adversary can disrupt the view synchronization and launch a liveness attack, stalling the confirmation process. Besides, the adversary can further recover or control the confirmation process at will. A repairment that retains the desirable feature of HotStuff is also presented. We simulate the liveness attack and the repairment, demonstrating their effectiveness. Specifically, the liveness attack can cause HotStuff’s throughput to drop and remain at 0. When equipped with our repairment, HotStuff can resist the attack and retain the throughput performance.

---

### A Review of Asynchronous Byzantine Consensus Protocols
<a name="jiReviewAsynchronousByzantine2024"></a>

**Authors:** Ji, Zhenyan; Zhang, Xiao; Hu, Jianghao; Lu, Yuan; Liu, Jiqiang

**Type:** Journal Article
**Date:** 2024-12-11
**Publication:** Sensors
**Volume:** 24
**Issue:** 24
**Pages:** 7927
**DOI:** [10.3390/s24247927](https://doi.org/10.3390/s24247927)
**URL:** [https://www.mdpi.com/1424-8220/24/24/7927](https://www.mdpi.com/1424-8220/24/24/7927)

**Abstract:**
> Blockchain technology can be used in the IoT to ensure the data privacy collected by sensors. In blockchain systems, consensus mechanisms are a key technology for maintaining data consistency and correctness. Among the various consensus protocols, asynchronous Byzantine consensus protocols offer strong robustness as they do not rely on any network timing assumptions during design. As a result, these protocols have become a research hotspot in the field of blockchain. Based on different structural design approaches, asynchronous Byzantine consensus protocols can be divided into two categories: protocols based on the DAG structure and protocols based on the ACS structure. The paper describes their principles and summarizes the related research works. The advantages and disadvantages of the protocols are also compared and analyzed. At the end of the paper, future research directions are identified.

---

### Mahi-Mahi: Low-Latency Asynchronous BFT DAG-Based Consensus
<a name="jovanovicMahiMahiLowLatencyAsynchronous2024"></a>

**Authors:** Jovanovic, Philipp; Kogias, Lefteris Kokoris; Kumara, Bryan; Sonnino, Alberto; Tennage, Pasindu; Zablotchi, Igor

**Type:** Journal Article
**Date:** 2024
**DOI:** [10.48550/ARXIV.2410.08670](https://doi.org/10.48550/ARXIV.2410.08670)
**URL:** [https://arxiv.org/abs/2410.08670](https://arxiv.org/abs/2410.08670)

**Abstract:**
> We present Mahi-Mahi, the first asynchronous BFT consensus protocol that achieves sub-second latency in the WAN while processing over 100,000 transactions per second. We accomplish this remarkable performance by building Mahi-Mahi on an uncertified structured Directed Acyclic Graph (DAG). By forgoing explicit certification, we significantly reduce the number of messages required to commit and minimize CPU overhead associated with certificate verification. Mahi-Mahi introduces a novel commit rule that allows committing multiple blocks in each DAG round, while ensuring liveness in the presence of an asynchronous adversary. Mahi-Mahi can be parametrized to either attempt to commit within 5 message delays, maximizing the probability of commitment under a continuously active asynchronous adversary, or within 4 message delays, which reduces latency under a more moderate and realistic asynchronous adversary. We demonstrate the safety and liveness of Mahi-Mahi in a Byzantine context. Subsequently, we evaluate Mahi-Mahi in a geo-replicated setting and compare its performance against state-of-the-art asynchronous consensus protocols, showcasing Mahi-Mahi's significantly lower latency.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`, `Cryptography and Security (cs.CR)`

---

### HotStuff-1: Linear Consensus with One-Phase Speculation
<a name="kangHotStuff1LinearConsensus2024"></a>

**Authors:** Kang, Dakai; Gupta, Suyash; Malkhi, Dahlia; Sadoghi, Mohammad

**Type:** Journal Article
**Date:** 2024
**DOI:** [10.48550/ARXIV.2408.04728](https://doi.org/10.48550/ARXIV.2408.04728)
**URL:** [https://arxiv.org/abs/2408.04728](https://arxiv.org/abs/2408.04728)

**Abstract:**
> This paper introduces HotStuff-1, a BFT consensus protocol that improves the latency of HotStuff-2 by two network-hops while maintaining linear communication complexity against faults. Additionally, HotStuff-1 incorporates an incentive-compatible leader rotation regime that motivates leaders to commit consensus decisions promptly.
 HotStuff-1 achieves a reduction by two network hops by sending clients early finality confirmations speculatively, after one phase of the protocol. Unlike previous speculation regimes, the early finality confirmation path of HotStuff-1 is fault-tolerant and the latency improvement does not rely on optimism. An important consideration for speculation regimes in general, which is referred to as the prefix speculation dilemma, is exposed and resolved.
 HotStuff-1 embodies an additional mechanism, slotting, that thwarts real-world delays caused by rationally-incentivized leaders. Leaders may also be inclined to sabotage each other's progress. The slotting mechanism allows leaders to drive multiple decisions, thus mitigating both threats, while dynamically adapting the number of allowed decisions per leader to network transmission delays.

**Tags:** `FOS: Computer and information sciences`, `Databases (cs.DB)`

---

### All You Need is DAG
<a name="keidarAllYouNeed2021"></a>

**Authors:** Keidar, Idit; Kokoris-Kogias, Eleftherios; Naor, Oded; Spiegelman, Alexander

**Type:** Journal Article
**Date:** 2021-07-21
**Publication:** Proceedings of the 2021 ACM Symposium on Principles of Distributed Computing
**Pages:** 165-175
**DOI:** [10.1145/3465084.3467905](https://doi.org/10.1145/3465084.3467905)
**URL:** [https://dl.acm.org/doi/10.1145/3465084.3467905](https://dl.acm.org/doi/10.1145/3465084.3467905)

**Abstract:**
> We present DAG-Rider, the first asynchronous Byzantine Atomic Broadcast protocol that achieves optimal resilience, optimal amortized communication complexity, and optimal time complexity. DAG-Rider is post-quantum safe and ensures that all values proposed by correct processes eventually get delivered. We construct DAG-Rider in two layers: In the first layer, processes reliably broadcast their proposals and build a structured Directed Acyclic Graph (DAG) of the communication among them. In the second layer, processes locally observe their DAGs and totally order all proposals with no extra communication.

---

### On Consensus Number 1 Objects
<a name="khanchandaniConsensusNumber12021"></a>

**Authors:** Khanchandani, Pankaj; Schappi, Jan; Wang, Ye; Wattenhofer, Roger

**Type:** Journal Article
**Date:** 2021-12
**Publication:** 2021 IEEE 27th International Conference on Parallel and Distributed Systems (ICPADS)
**Pages:** 875-882
**DOI:** [10.1109/ICPADS53394.2021.00115](https://doi.org/10.1109/ICPADS53394.2021.00115)
**URL:** [https://ieeexplore.ieee.org/document/9763737/](https://ieeexplore.ieee.org/document/9763737/)

**Abstract:**
> The consensus number concept is used to determine the power of synchronization primitives in distributed systems. Recent work in the blockchain domain motivates shifting the attention to consensus number 1 objects, as it has been shown that transaction-based blockchains just need consensus number 1. In this paper we want to get a better understanding of such consensus number 1 objects. In particular, we study the necessary and sufficient conditions for determining the consensus number 1 objects. If an object has consensus number 1, then its operations must be either commutative or associative (necessary condition). On the other hand, if the operations are consistently commutative or overwriting, i.e., independent of the current state of the object, then the consensus number of the object is 1 (sufficient condition). We give an algorithm to implement such generic consensus number 1 objects using only read/write registers. This implies that read/write registers are universal enough to solve tasks, such as asset transfer of a cryptocurrency, among many others, in wait-free distributed systems for any number of processes.

---

### Making CRDTs Byzantine fault tolerant
<a name="kleppmannMakingCRDTsByzantine2022"></a>

**Authors:** Kleppmann, Martin

**Type:** Journal Article
**Date:** 2022-04-05
**Publication:** Proceedings of the 9th Workshop on Principles and Practice of Consistency for Distributed Data
**Pages:** 8-15
**DOI:** [10.1145/3517209.3524042](https://doi.org/10.1145/3517209.3524042)
**URL:** [https://dl.acm.org/doi/10.1145/3517209.3524042](https://dl.acm.org/doi/10.1145/3517209.3524042)

**Abstract:**
> It is often claimed that Conflict-free Replicated Data Types (CRDTs) ensure consistency of replicated data in peer-to-peer systems. However, peer-to-peer systems usually consist of untrusted nodes that may deviate from the specified protocol (i.e. exhibit Byzantine faults), and most existing CRDT algorithms cannot guarantee consistency in the presence of such faults. This paper shows how to adapt existing non-Byzantine CRDT algorithms and make them Byzantine fault-tolerant. The proposed scheme can tolerate any number of Byzantine nodes (making it immune to Sybil attacks), guarantees Strong Eventual Consistency, and requires only modest changes to existing CRDT algorithms.

---

### GOC-Ledger: State-based Conflict-Free Replicated Ledger from Grow-Only Counters
<a name="lavoieGOCLedgerStatebasedConflictFree2023"></a>

**Authors:** Lavoie, Erick

**Type:** Preprint
**Date:** 2023-05-26
**DOI:** [10.48550/arXiv.2305.16976](https://doi.org/10.48550/arXiv.2305.16976)
**URL:** [http://arxiv.org/abs/2305.16976](http://arxiv.org/abs/2305.16976)

**Abstract:**
> Conventional blockchains use consensus algorithms that totally order updates across all accounts, which is stronger than necessary to implement a replicated ledger. This makes updates slower and more expensive than necessary. More recent consensus-free replicated ledgers forego consensus algorithms, with significant increase in performance and decrease in infrastructure costs. However, current designs are based around reliable broadcast of update operations to all replicas which require reliable message delivery and reasoning over operation histories to establish convergence and safety. In this paper, we present a replicated ledger as a state-based conflict-free replicated data type (CRDT) based on grow-only counters. This design provides two major benefits: 1) it requires a weaker eventual transitive delivery of the latest state rather than reliable broadcast of all update operations to all replicas; 2) eventual convergence and safety properties can be proven easily without having to reason over operation histories: convergence comes from the composition of grow-only counters, themselves CRDTs, and safety properties can be expressed over the state of counters, locally and globally. In addition, applications that tolerate temporary negative balances require no additional mechanisms and applications that require strictly non-negative balances can be supported by enforcing sequential updates to the same account across replicas. Our design is sufficient when executing on replicas that might crash and recover, as common in deployments in which all replicas are managed by trusted entities. It may also provide a good foundation to explore new mechanisms for tolerating adversarial replicas.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### Proofs of non-Supermajority: the missing link for two-phase BFT with responsive view-change and linear complexity
<a name="levratProofsNonSupermajorityMissing2023"></a>

**Authors:** Levrat, Christophe; Rambaud, Matthieu

**Type:** Conference Paper
**Date:** 2023
**URL:** [https://www.semanticscholar.org/paper/Proofs-of-non-Supermajority%3A-the-missing-link-for-Levrat-Rambaud/52b8101be0032db298ff73335f14a174baecd55c](https://www.semanticscholar.org/paper/Proofs-of-non-Supermajority%3A-the-missing-link-for-Levrat-Rambaud/52b8101be0032db298ff73335f14a174baecd55c)

**Abstract:**
> . We consider leader-based Byzantine state machine replication, a.k.a. “BFT”, under partial synchrony. We provide a generic solution enabling to match simultaneously, for the first time, three arguably gold standards of BFT: in two phases, with a responsive view change and a linear complexity per view. It is based on a new threshold primitive, which we call Proofs of non-Supermajority (or PnS for short). A PnS system enables players, each with an input number, to report their input to a leader, with extra hints enabling their efficient aggregation. Out of a threshold number k ( = 2 t + 1 ) of such reports, calling v max the highest reported value, the leader can efficiently build a short proof that a threshold number of k − t honest players have their inputs lower than this v max . As highlighted in the state of the art BFT [Abraham et al. Podc’23], any of our lightweight implementations of PnS can be plugged in their BFT, or the one of [Gelashvili et al FC’22], to bring down their complexities from quadratic to linear. Previous BFTs implicitely implemented PnS by either (i) having the leader multicasting the k signed reports, so this had quadratic communication complexity, or (ii) multicasting an aggregate signature on the reports, with verification complexity of k + 1 pairings, so this had a total quadratic computation complexity. To match our linear complexity claim, we introduce a very simple constant-sized and constant-verification implementation of PnS, built from any threshold (or multi-) signature scheme. We then bring further optimizations by introducing the following tools of possible independent interest:

---

### Fever: Optimal Responsive View Synchronisation
<a name="lewis-pyeFeverOptimalResponsive2023"></a>

**Authors:** Lewis-Pye, Andrew; Abraham, Ittai

**Type:** Conference Paper
**Date:** 2023
**DOI:** [10.48550/ARXIV.2301.09881](https://doi.org/10.48550/ARXIV.2301.09881)
**URL:** [https://arxiv.org/abs/2301.09881](https://arxiv.org/abs/2301.09881)

**Abstract:**
> View synchronisation is an important component of many modern Byzantine Fault Tolerant State Machine Replication (SMR) systems in the partial synchrony model. Roughly, the efficiency of view synchronisation is measured as the word complexity and latency required for moving from being synchronised in a view of one correct leader to being synchronised in the view of the next correct leader. The efficiency of view synchronisation has emerged as a major bottleneck in the efficiency of SMR systems as a whole. A key question remained open: Do there exist view synchronisation protocols with asymptotically optimal quadratic worst-case word complexity that also obtain linear message complexity and responsiveness when moving between consecutive correct leaders? We answer this question affirmatively with a new view synchronisation protocol for partial synchrony assuming minimal clock synchronisation, called \emph{Fever}. If $n$ is the number of processors and $t$ is the largest integer $

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`

---

### Lumiere: Making Optimal BFT for Partial Synchrony Practical
<a name="lewis-pyeLumiereMakingOptimal2023"></a>

**Authors:** Lewis-Pye, Andrew; Malkhi, Dahlia; Naor, Oded; Nayak, Kartik

**Type:** Journal Article
**Date:** 2023
**DOI:** [10.48550/ARXIV.2311.08091](https://doi.org/10.48550/ARXIV.2311.08091)
**URL:** [https://arxiv.org/abs/2311.08091](https://arxiv.org/abs/2311.08091)

**Abstract:**
> The view synchronization problem lies at the heart of many Byzantine Fault Tolerant (BFT) State Machine Replication (SMR) protocols in the partial synchrony model, since these protocols are usually based on views. Liveness is guaranteed if honest processors spend a sufficiently long time in the same view during periods of synchrony, and if the leader of the view is honest. Ensuring that these conditions occur, known as Byzantine View Synchronization (BVS), has turned out to be the performance bottleneck of many BFT SMR protocols.
 A recent line of work has shown that, by using an appropriate view synchronization protocol, BFT SMR protocols can achieve $O(n^2)$ communication complexity in the worst case after GST, thereby finally matching the lower bound established by Dolev and Reischuk in 1985. However, these protocols suffer from two major issues:
 (1) When implemented so as to be optimistically responsive, even a single Byzantine processor may infinitely often cause $Ω(nΔ)$ latency between consecutive consensus decisions.
 (2) Even in the absence of Byzantine action, infinitely many views require honest processors to send $Ω(n^2)$ messages.
 Here, we present Lumiere, an optimistically responsive BVS protocol which maintains optimal worst-case communication complexity while simultaneously addressing the two issues above: for the first time, Lumiere enables BFT consensus solutions in the partial synchrony setting that have $O(n^2)$ worst-case communication complexity, and that eventually always (i.e., except for a small constant number of "warmup" decisions) have communication complexity and latency which is linear in the number of actual faults in the execution.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`

---

### Permissionless Consensus
<a name="lewis-pyePermissionlessConsensus2024"></a>

**Authors:** Lewis-Pye, Andrew; Roughgarden, Tim

**Type:** Preprint
**Date:** 2024-03-03
**DOI:** [10.48550/arXiv.2304.14701](https://doi.org/10.48550/arXiv.2304.14701)
**URL:** [http://arxiv.org/abs/2304.14701](http://arxiv.org/abs/2304.14701)

**Abstract:**
> Blockchain protocols typically aspire to run in the permissionless setting, in which nodes are owned and operated by a large number of diverse and unknown entities, with each node free to start or stop running the protocol at any time. This setting is more challenging than the traditional permissioned setting, in which the set of nodes that will be running the protocol is fixed and known at the time of protocol deployment. The goal of this paper is to provide a framework for reasoning about the rich design space of blockchain protocols and their capabilities and limitations in the permissionless setting. We propose a hierarchy of settings with different "degrees of permissionlessness", specified by the amount of knowledge that a protocol has about the current participants: These are the fully permissionless, dynamically available and quasi-permissionless settings. The paper also proves several results illustrating the utility of our analysis framework for reasoning about blockchain protocols in these settings. For example: (1) In the fully permissionless setting, even with synchronous communication and with severe restrictions on the total size of the Byzantine players, every deterministic protocol for Byzantine agreement has a non-terminating execution. (2) In the dynamically available and partially synchronous setting, no protocol can solve the Byzantine agreement problem with high probability, even if there are no Byzantine players at all. (3) In the quasi-permissionless and partially synchronous setting, by contrast, assuming a bound on the total size of the Byzantine players, there is a deterministic protocol solving state machine replication. (4) In the quasi-permissionless and synchronous setting, every proof-of-stake state machine replication protocol that uses only time-malleable cryptographic primitives is vulnerable to long-range attacks.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`, `foundational`

---

### Quadratic worst-case message complexity for State Machine Replication in the partial synchrony model
<a name="lewis-pyeQuadraticWorstcaseMessage2022"></a>

**Authors:** Lewis-Pye, Andrew

**Type:** Journal Article
**Date:** 2022-01-04
**Publication:** ArXiv
**URL:** [https://www.semanticscholar.org/paper/Quadratic-worst-case-message-complexity-for-State-Lewis-Pye/35c45abc5aed75f0ef27bb1e1c55a4df5134695c](https://www.semanticscholar.org/paper/Quadratic-worst-case-message-complexity-for-State-Lewis-Pye/35c45abc5aed75f0ef27bb1e1c55a4df5134695c)

**Abstract:**
> We consider the message complexity of State Machine Replication protocols dealing with Byzantine failures in the partial synchrony model. A result of Dolev and Reischuk gives a quadratic lower bound for the message complexity, but it was unknown whether this lower bound is tight, with the most efficient known protocols giving worst-case message complexity $O(n^3)$. We describe a protocol which meets Dolev and Reischuk's quadratic lower bound, while also satisfying other desirable properties. To specify these properties, suppose that we have $n$ replicas, $f$ of which display Byzantine faults (with $n\geq 3f+1$). Suppose that $\Delta$ is an upper bound on message delay, i.e. if a message is sent at time $t$, then it is received by time $ \text{max} \{ t, GST \} +\Delta $. We describe a deterministic protocol that simultaneously achieves $O(n^2)$ worst-case message complexity, optimistic responsiveness, $O(f\Delta )$ time to first confirmation after $GST$ and $O(n)$ mean message complexity.

---

### Reconfigurable Heterogeneous Quorum Systems
<a name="liReconfigurableHeterogeneousQuorum2023"></a>

**Authors:** Li, Xiao; Lesani, M.

**Type:** Conference Paper
**Date:** 2023-04-04
**URL:** [https://www.semanticscholar.org/paper/Reconfigurable-Heterogeneous-Quorum-Systems-Li-Lesani/abf7788272cf6d8e8b7ab8554587ee40c20a5b1f](https://www.semanticscholar.org/paper/Reconfigurable-Heterogeneous-Quorum-Systems-Li-Lesani/abf7788272cf6d8e8b7ab8554587ee40c20a5b1f)

**Abstract:**
> In contrast to proof-of-work replication, Byzantine quorum systems maintain consistency across replicas with higher throughput modest energy consumption, and deterministic liveness guarantees. If complemented with heterogeneous trust and open membership, they have the potential to serve as blockchains backbone. This paper presents a general model of heterogeneous quorum systems where each participant can declare its own quorums, and captures the consistency, availability and inclusion properties of these systems. In order to support open membership, it then presents reconfiguration protocols for heterogeneous quorum systems including joining and leaving of a process, and adding and removing of a quorum, and further, proves their correctness in the face of Byzantine attacks. The design of the protocols is informed by the trade-offs that the paper proves for the properties that reconfigurations can preserve. The paper further presents a graph characterization of heterogeneous quorum systems, and its application for reconfiguration optimization.

---

### Byzantine Reliable Broadcast with Low Communication and Time Complexity
<a name="locherByzantineReliableBroadcast2024"></a>

**Authors:** Locher, Thomas

**Type:** Conference Paper
**Date:** 2024
**DOI:** [10.48550/ARXIV.2404.08070](https://doi.org/10.48550/ARXIV.2404.08070)
**URL:** [https://arxiv.org/abs/2404.08070](https://arxiv.org/abs/2404.08070)

**Abstract:**
> Byzantine reliable broadcast is a fundamental problem in distributed computing, which has been studied extensively over the past decades. State-of-the-art algorithms are predominantly based on the approach to share encoded fragments of the broadcast message, yielding an asymptotically optimal communication complexity when the message size exceeds the network size, a condition frequently encountered in practice. However, algorithms following the standard coding approach incur an overhead factor of at least 3, which can already be a burden for bandwidth-constrained applications. Minimizing this overhead is an important objective with immediate benefits to protocols that use a reliable broadcast routine as a building block.
 This paper introduces a novel mechanism to lower the communication and computational complexity. Two algorithms are presented that employ this mechanism to reliably broadcast messages in an asynchronous network where less than a third of all nodes are Byzantine. The first algorithm reduces the overhead factor to 2 and has a time complexity of 3 if the sender is honest, whereas the second algorithm attains an optimal time complexity of 2 with the same overhead factor in the absence of equivocation. Moreover, an optimization for real-world implementations is proposed, reducing the overhead factor to 3/2 under normal operation. Lastly, a lower bound is proved that an overhead factor lower than 3/2 cannot be achieved for a relevant class of reliable broadcast algorithms.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`

---

### MiniCast: Minimizing the Communication Complexity of Reliable Broadcast
<a name="locherMiniCastMinimizingCommunication2024"></a>

**Authors:** Locher, Thomas; Shoup, Victor

**Type:** Preprint
**Date:** 2024
**URL:** [https://eprint.iacr.org/2024/571](https://eprint.iacr.org/2024/571)

**Abstract:**
> We give a new protocol for reliable broadcast with improved communication complexity for long messages. Namely, to reliably broadcast a message a message m over an asynchronous network to a set of n parties, of which fewer than n/3 may be corrupt, our protocol achieves a communication complexity of 1.5|m|n+O(κn2log⁡(n)), where κ is the output length of a collision-resistant hash function. This result improves on the previously best known bound for long messages of 2|m|n+O(κn2log⁡(n)).

**Tags:** `asynchronous network`, `communication complexity`, `reliable broadcast`

---

### Bolt-Dumbo Transformer: Asynchronous Consensus As Fast As the Pipelined BFT
<a name="luBoltDumboTransformerAsynchronous2022"></a>

**Authors:** Lu, Yuan; Lu, Zhenliang; Tang, Qiang

**Type:** Preprint
**Date:** 2022-08-31
**DOI:** [10.48550/arXiv.2103.09425](https://doi.org/10.48550/arXiv.2103.09425)
**URL:** [http://arxiv.org/abs/2103.09425](http://arxiv.org/abs/2103.09425)

**Abstract:**
> An urgent demand of deploying BFT consensus over the Internet is raised for implementing blockchain services. The deterministic (partial) synchronous protocols can be simple and fast in good network conditions, but are subject to denial-of-service when synchrony assumption fails. Asynchronous protocols, on the contrary, are robust against the adversarial network, but are substantially more complicated and slower for the inherent use of randomness. Facing the issues, optimistic asynchronous atomic broadcast ( Kursawe-Shoup, 2002; Ramasamy-Cachin, 2005) was proposed to improve the normal-case performance of the slow asynchronous consensus. They run a deterministic fastlane if the network condition remains good, and can fall back to a fully asynchronous protocol via a pace-synchronization mechanism if the fastlane fails. Unfortunately, existing pace-synchronization directly uses a heavy tool of asynchronous multi-valued validated Byzantine agreement (MVBA). We present Bolt-Dumbo Transformer (BDT), a generic framework for practical optimistic asynchronous atomic broadcast. At the core of BDT, we set forth a new fastlane abstraction that is simple and fast, while preparing honest parties to gracefully face potential fastlane failures caused by malicious leader or bad network. This enables a highly efficient pace-synchronization to handle fallback. The resulting design reduces a cumbersome MVBA to a variant of the conceptually simplest binary agreement only. Besides detailed security analyses, we also give concrete instantiations of our framework and implement them. Extensive experiments demonstrate that BDT can enjoy both the low latency of deterministic protocols (e.g. 2-chain version of HotStuff) and the robustness of state-of-the-art asynchronous protocols in practice.

**Tags:** `Computer Science - Cryptography and Security`, `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### BBCA-CHAIN: Low Latency, High Throughput BFT Consensus on a DAG
<a name="malkhiBBCACHAINLowLatency2023"></a>

**Authors:** Malkhi, Dahlia; Stathakopoulou, C.; Yin, Maofan

**Type:** Conference Paper
**Date:** 2023-10-10
**URL:** [https://www.semanticscholar.org/paper/BBCA-CHAIN%3A-Low-Latency%2C-High-Throughput-BFT-on-a-Malkhi-Stathakopoulou/58001c78128e4889d060c997ebb2bb2768dae96b](https://www.semanticscholar.org/paper/BBCA-CHAIN%3A-Low-Latency%2C-High-Throughput-BFT-on-a-Malkhi-Stathakopoulou/58001c78128e4889d060c997ebb2bb2768dae96b)

**Abstract:**
> This paper presents a partially synchronous BFT consensus protocol powered by BBCA, a lightly modified Byzantine Consistent Broadcast (BCB) primitive. BBCA provides a Complete-Adopt semantic through an added probing interface to allow either aborting the broadcast by correct nodes or exclusively, adopting the message consistently in case of a potential delivery. It does not introduce any extra types of messages or additional communication costs to BCB. BBCA is harnessed into BBCA-CHAIN to make direct commits on a chained backbone of a causally ordered graph of blocks, without any additional voting blocks or artificial layering. With the help of Complete-Adopt, the additional knowledge gained from the underlying BCB completely removes the voting latency in popular DAG-based protocols. At the same time, causal ordering allows nodes to propose blocks in parallel and achieve high throughput. BBCA-CHAIN thus closes up the gap between protocols built by consistent broadcasts (e.g., Bullshark) to those without such an abstraction (e.g., PBFT/HotStuff), emphasizing their shared fundamental principles. Using a Bracha-style BCB as an example, we fully specify BBCA-CHAIN with simplicity, serving as a solid basis for high-performance replication systems (and blockchains).

---

### Rondo: Scalable and Reconfiguration-Friendly Randomness Beacon
<a name="mengRondoScalableReconfigurationFriendly2024"></a>

**Authors:** Meng, Xuanji; Sui, Xiao; Yang, Zhaoxin; Rong, Kang; Xu, Wenbo; Chen, Shenglong; Yan, Ying; Duan, Sisi

**Type:** Journal Article
**Date:** 2024
**Publication:** IACR Cryptol. ePrint Arch.
**URL:** [https://www.semanticscholar.org/paper/Rondo%3A-Scalable-and-Reconfiguration-Friendly-Beacon-Meng-Sui/c6d62edc77ffec6362993460b99939699b3fb521](https://www.semanticscholar.org/paper/Rondo%3A-Scalable-and-Reconfiguration-Friendly-Beacon-Meng-Sui/c6d62edc77ffec6362993460b99939699b3fb521)

**Abstract:**
> —We present Rondo, a scalable and reconfiguration-friendly distributed randomness beacon (DRB) protocol in the partially synchronous model. Rondo is the first DRB protocol that is built from batched asynchronous verifiable secret sharing (bAVSS) and meanwhile avoids the high O ( n 3 ) message cost, where n is the number of nodes. Our key contribution lies in the introduction of a new variant of bAVSS called batched asynchronous verifiable secret sharing with partial output (bAVSS-PO). bAVSS-PO is a weaker primitive than bAVSS but allows us to build a secure and more scalable DRB protocol. We propose a bAVSS-PO protocol Breeze. Breeze achieves the optimal O ( n ) messages for the sharing stage and allows Rondo to offer better scalability than prior DRB protocols. Additionally, to support the reconfiguration, we introduce Rondo-BFT, a dynamic and partially synchronous Byzantine fault-tolerant protocol inspired by Dyno (S&P 2022). Unlike Dyno, Rondo-BFT provides a communication pattern that generates randomness beacon output periodically, making it well-suited for DRB applications. We implement our protocols and evaluate the performance on Amazon EC2 using up to 91 instances. Our evaluation results show that Rondo achieves higher throughput than existing works and meanwhile offers better scalability, where the performance does not degrade

---

### How Robust Are Synchronous Consensus Protocols?
<a name="milosevicHowRobustAre2025"></a>

**Authors:** Milošević, Nenad; Cason, Daniel; Milošević, Zarko; Pedone, Fernando; Bonomi, Silvia; Galletta, Letterio; Rivière, Etienne; Schiavoni, Valerio

**Type:** Conference Paper
**Date:** 2025
**Publication:** LIPIcs, Volume 324, OPODIS 2024
**Volume:** 324
**Pages:** 20:1-20:25
**DOI:** [10.4230/LIPICS.OPODIS.2024.20](https://doi.org/10.4230/LIPICS.OPODIS.2024.20)
**URL:** [https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.OPODIS.2024.20](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.OPODIS.2024.20)

**Abstract:**
> Synchronous Byzantine fault-tolerant (BFT) protocols have long been a reality in an academic setting, yet their practicality remains debated. The main concern of skeptics of synchronous systems is that the correctness of these protocols depends on the timely delivery of all messages within a predefined synchronous bound, Δ. This dependency creates a challenging tradeoff between protocol correctness and performance, as Δ directly impacts both. In this paper, we examine this tradeoff in detail. Specifically, we introduce BoundBFT, a new synchronous BFT consensus protocol. We analyze how BoundBFT’s correctness can be compromised and use this analysis to design and implement the most effective attack strategies that malicious processes could employ. Furthermore, we experimentally determine the synchronous bound Δ that provides sufficient confidence in maintaining protocol correctness even in the presence of malicious replicas. Finally, we apply this discovered bound to BoundBFT, evaluate its performance, and compare it to state-of-the-art synchronous and partially synchronous protocols.

**Tags:** `Computing methodologies → Distributed algorithms`, `Blockchain`, `Byzantine Failures`, `Computer systems organization → Availability`, `Computer systems organization → Redundancy`, `Computer systems organization → Reliability`, `Synchronous Consensus`

---

### Optimal Communication Complexity of Authenticated Byzantine Agreement
<a name="momoseOptimalCommunicationComplexity2021"></a>

**Authors:** Momose, Atsuki; Ren, Ling; Gilbert, Seth

**Type:** Conference Paper
**Date:** 2021
**Publication:** LIPIcs, Volume 209, DISC 2021
**Volume:** 209
**Pages:** 32:1-32:16
**DOI:** [10.4230/LIPICS.DISC.2021.32](https://doi.org/10.4230/LIPICS.DISC.2021.32)
**URL:** [https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.DISC.2021.32](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.DISC.2021.32)

**Abstract:**
> Byzantine Agreement (BA) is one of the most fundamental problems in distributed computing, and its communication complexity is an important efficiency metric. It is well known that quadratic communication is necessary for BA in the worst case due to a lower bound by Dolev and Reischuk. This lower bound has been shown to be tight for the unauthenticated setting with f < n/3 by Berman et al. but a considerable gap remains for the authenticated setting with n/3 ≤ f < n/2. 
This paper provides two results towards closing this gap. Both protocols have a quadratic communication complexity and have different trade-offs in resilience and assumptions. The first protocol achieves the optimal resilience of f < n/2 but requires a trusted setup for threshold signature. The second protocol achieves near optimal resilience f ≤ (1/2 - ε)n in the standard PKI model.

**Tags:** `Security and privacy → Distributed systems security`, `Byzantine Agreement`, `Communication Complexity`, `Lower Bound`

---

### Fast Leaderless Byzantine Total Order Broadcast
<a name="montiFastLeaderlessByzantine2024"></a>

**Authors:** Monti, Matteo; Camaioni, Martina; Roman, Pierre-Louis

**Type:** Journal Article
**Date:** 2024
**DOI:** [10.48550/ARXIV.2412.14061](https://doi.org/10.48550/ARXIV.2412.14061)
**URL:** [https://arxiv.org/abs/2412.14061](https://arxiv.org/abs/2412.14061)

**Abstract:**
> This paper presents the Byzantine fault-tolerant agreement protocols Flutter and Blink. Both algorithms are deterministic, leaderless and signature-free; both assume partial synchrony and at least $(5f + 1)$ servers, where $f$ bounds the number of faults. The main contribution, Flutter, is a Total-Order Broadcast implementation that achieves faster broadcast-to-delivery latency by removing the extra message delay associated with serializing messages through a leader. In the "good case" where all processes are correct, the network is synchronous, and local clocks are well-synchronized, Flutter delivers client requests in $(2Δ+ ε)$ time units, $Δ$ being the message delay and $ε$ an arbitrarily small constant. Under the same conditions, state-of-the-art protocols require $3Δ$ time units. Flutter's good-case latency is quasi-optimal, meaning it cannot be improved upon by any finite amount. Under the hood, Flutter builds upon Blink, a (Representative) Binary Consensus implementation whose fast path enables decisions in $Δ$ time units when all correct servers propose the same value. Blink generalizes the existing Binary Consensus solution Bosco from the $(7f + 1)$ to the $(5f + 1)$ setting.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`

---

### How Does Stake Distribution Influence Consensus? Analyzing Blockchain Decentralization
<a name="motepalliHowDoesStake2024"></a>

**Authors:** Motepalli, Shashank; Jacobsen, Hans-Arno

**Type:** Journal Article
**Date:** 2024-5-27
**Publication:** 2024 IEEE International Conference on Blockchain and Cryptocurrency (ICBC)
**Pages:** 343-352
**DOI:** [10.1109/ICBC59979.2024.10634400](https://doi.org/10.1109/ICBC59979.2024.10634400)
**URL:** [https://ieeexplore.ieee.org/document/10634400/](https://ieeexplore.ieee.org/document/10634400/)

**Abstract:**
> In the PoS blockchain landscape, the challenge of achieving full decentralization is often hindered by a disproportionate concentration of staked tokens among a few validators. This study analyses this challenge by first formalizing decentralization metrics for weighted consensus mechanisms. An empirical analysis across ten permissionless blockchains uncovers significant weight concentration among validators, underscoring the need for an equitable approach. To counter this, we introduce the Square Root Stake Weight (SRSW) model, which effectively recalibrates staking weight distribution. Our examination of the SRSW model demonstrates notable improvements in the decentralization metrics: the Gini index improves by $37.16 \%$ on average, while Nakamoto coefficients for liveness and safety see mean enhancements of $101.04 \%$ and $80.09 \%$, respectively. This research is a pivotal step toward a more fair and equitable distribution of staking weight, advancing the decentralization in blockchain consensus mechanisms.

---

### Tangle 2.0 Leaderless Nakamoto Consensus on the Heaviest DAG
<a name="mullerTangle20Leaderless2022"></a>

**Authors:** Muller, Sebastian; Penzkofer, Andreas; Polyanskii, Nikita; Theis, Jonas; Sanders, William; Moog, Hans

**Type:** Journal Article
**Date:** 2022
**Publication:** IEEE Access
**Volume:** 10
**Pages:** 105807-105842
**DOI:** [10.1109/ACCESS.2022.3211422](https://doi.org/10.1109/ACCESS.2022.3211422)
**URL:** [https://ieeexplore.ieee.org/document/9907014/](https://ieeexplore.ieee.org/document/9907014/)

**Abstract:**
> We introduce the theoretical foundations of the Tangle 2.0, a probabilistic leaderless consensus protocol based on a directed acyclic graph (DAG) called the Tangle. The Tangle naturally succeeds the blockchain as its next evolutionary step as it offers features suited to establish more efficient and scalable distributed ledger solutions. Consensus is no longer found in the longest chain but on the heaviest DAG, where PoW is replaced by a stake- or reputation-based weight function. The DAG structure and the underlying Reality-based UTXO Ledger allow parallel validation of transactions without the need for total ordering. Moreover, it enables the removal of the intermediary of miners and validators, allowing a pure two-step process that follows the propose-vote paradigm at the node level and not at the validator level. We propose a framework to analyse liveness and safety under different communication and adversary models. This allows providing impossibility results in some edge cases and in the asynchronous communication model. We provide formal proof of the security of the protocol assuming a common random coin.

---

### Cogsworth: Byzantine View Synchronization.
<a name="naorCogsworthByzantineView2019"></a>

**Authors:** Naor, O.; Baudet, M.; Malkhi, D.; Spiegelman, A.

**Type:** Journal Article
**Date:** 2019-09-11
**Publication:** arXiv: Distributed, Parallel, and Cluster Computing
**URL:** [https://www.semanticscholar.org/paper/Cogsworth%3A-Byzantine-View-Synchronization.-Naor-Baudet/51f763df4ee3a8d3b56756a4a6f5004fd0cda7ee](https://www.semanticscholar.org/paper/Cogsworth%3A-Byzantine-View-Synchronization.-Naor-Baudet/51f763df4ee3a8d3b56756a4a6f5004fd0cda7ee)

**Abstract:**
> Many distributed protocols in the partial synchrony setting with Byzantine nodes divide the local state of the nodes into views, and the transition from one view to the next dictates a leader change. In order to provide liveness, all honest nodes need to stay in the same view for a sufficiently long time. This requires intricate mechanisms that are typically intertwined with the rest of the protocol, making it hard to understand and to reason about. Furthermore, state-machine replication, which is consisted of multiple instances of single-shot consensus, can use the same view synchronization protocol. 
We define the Byzantine View Synchronization problem, which is responsible for eventually bringing all nodes to the same view for a sufficiently long time. 
Two approaches for implementing a protocol that achieves view synchronization exhibit the following tradeoffs: a view doubling solution has zero communication costs but unbounded latency, while a broadcastbased solution has quadratic communication costs but constant latency. We describe both protocols, prove their correctness, and also introduce a third protocol, named Cogsworth, that has optimistically linear communication complexity and constant latency, and faced with benign failures, has expected linear communication and constant latency. Cogsworth is particularly useful for a family of consensus protocols that exhibit linear communication under various circumstances.

---

### Expected Linear Round Synchronization: The Missing Link for Linear Byzantine SMR
<a name="naorExpectedLinearSynchronization2020"></a>

**Authors:** Naor, Oded; Keidar, Idit; Attiya, Hagit

**Type:** Conference Paper
**Date:** 2020
**Publication:** LIPIcs, Volume 179, DISC 2020
**Volume:** 179
**Pages:** 26:1-26:17
**DOI:** [10.4230/LIPICS.DISC.2020.26](https://doi.org/10.4230/LIPICS.DISC.2020.26)
**URL:** [https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.DISC.2020.26](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.DISC.2020.26)

**Abstract:**
> State Machine Replication (SMR) solutions often divide time into rounds, with a designated leader driving decisions in each round. Progress is guaranteed once all correct processes synchronize to the same round, and the leader of that round is correct. Recently suggested Byzantine SMR solutions such as HotStuff, Tendermint, and LibraBFT achieve progress with a linear message complexity and a constant time complexity once such round synchronization occurs. But round synchronization itself incurs an additional cost. By Dolev and Reischuk’s lower bound, any deterministic solution must have Ω(n²) communication complexity. Yet the question of randomized round synchronization with an expected linear message complexity remained open. 
We present an algorithm that, for the first time, achieves round synchronization with expected linear message complexity and expected constant latency. Existing protocols can use our round synchronization algorithm to solve Byzantine SMR with the same asymptotic performance.

**Tags:** `Computing methodologies → Distributed algorithms`, `Distributed Systems`, `State Machine Replication`

---

### Slipstream: Ebb-and-Flow Consensus on a DAG with Fast Confirmation for UTXO Transactions
<a name="polyanskiiSlipstreamEbbandFlowConsensus2024"></a>

**Authors:** Polyanskii, Nikita; Muller, Sebastian; Raikwar, Mayank

**Type:** Journal Article
**Date:** 2024
**DOI:** [10.48550/ARXIV.2410.14876](https://doi.org/10.48550/ARXIV.2410.14876)
**URL:** [https://arxiv.org/abs/2410.14876](https://arxiv.org/abs/2410.14876)

**Abstract:**
> This paper introduces Slipstream, a Byzantine Fault Tolerance (BFT) protocol where nodes concurrently propose blocks to be added to a Directed Acyclic Graph (DAG) and aim to agree on block ordering. Slipstream offers two types of block orderings: an optimistic ordering, which is live and secure in a sleepy model under up to 50% Byzantine nodes, and a final ordering, which is a prefix of the optimistic ordering and ensures safety and liveness in an eventual lock-step synchronous model under up to 33% Byzantine nodes. Additionally, Slipstream integrates a payment system that allows for fast UTXO transaction confirmation independently of block ordering. Transactions are confirmed in three rounds during synchrony, and unconfirmed double spends are resolved in a novel way using the DAG structure.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`, `Data Structures and Algorithms (cs.DS)`

---

### SoK: DAG-based Consensus Protocols
<a name="raikwarSoKDAGbasedConsensus2024"></a>

**Authors:** Raikwar, Mayank; Polyanskii, Nikita; Müller, Sebastian

**Type:** Journal Article
**Date:** 2024-5-27
**Publication:** 2024 IEEE International Conference on Blockchain and Cryptocurrency (ICBC)
**Pages:** 1-18
**DOI:** [10.1109/ICBC59979.2024.10634358](https://doi.org/10.1109/ICBC59979.2024.10634358)
**URL:** [https://ieeexplore.ieee.org/document/10634358/](https://ieeexplore.ieee.org/document/10634358/)

**Abstract:**
> This paper is a Systematization of Knowledge (SoK) that focuses on Directed Acyclic Graph (DAG)-based consensus protocols in Distributed Ledger Technologies (DLTs). Our study evaluates their impact on performance and their tradeoffs concerning consistency, availability, and partition tolerance, as postulated by the CAP theorem. We delineate the key functionalities and tradeoffs of DAGbased consensus protocols, highlighting iterative improvements and deviations from foundational models. Additionally, we identify research gaps and suggest directions for future work to refine DAG-based consensus mechanisms.

---

### Linear View Change in Optimistically Fast BFT
<a name="rambaudLinearViewChange2022"></a>

**Authors:** Rambaud, Matthieu; Tonkikh, Andrei; Abspoel, Mark

**Type:** Journal Article
**Date:** 2022-11-07
**Publication:** Proceedings of the 2022 ACM Workshop on Developments in Consensus
**Pages:** 67-78
**DOI:** [10.1145/3560829.3563562](https://doi.org/10.1145/3560829.3563562)
**URL:** [https://dl.acm.org/doi/10.1145/3560829.3563562](https://dl.acm.org/doi/10.1145/3560829.3563562)

**Abstract:**
> To be competitive with centralized applications, consensus protocols in blockchains must provide minimal latency while being able to scale to thousands of participants in order to preserve a high level of decentralization. A common way to minimize latency is to augment a consensus protocol with a fast track, which ensures that a decision is reached in just a couple of message delays in favorable conditions. However, it is a challenging task to preserve safety and good performance when these favorable conditions do not hold. To the best of our knowledge, all existing Byzantine fault-tolerant consensus protocols with fast tracks require view change protocols with quadratic authenticator complexity. In this paper, we provide the first solution to Byzantine consensus with fast track with a linear view change. The protocol incurs no asymptotic overhead over the baseline while reducing the latency in favorable conditions by a factor of 2. Our construction is based on a novel type of cryptographic proofs, which we call Proofs of Exclusivity (or PoE for short), which may be of independent interest. While our protocol for constructing a PoE comes at no extra costs in latency or asymptotic complexities, it does require some extra computation. To make sure that it does not impair the overall performance, we also show how to apply accountability and proofs of misbehavior in order to reduce to zero the overhead incurred by the computation of a PoE. More precisely, our mechanism guarantees that whenever this overhead is not zero, then automatically honest participants obtain a publicly verifiable proof that a well-identified malicious participant openly misbehaved. In this case, the overhead of computing a few extra threshold signatures for the Proof of Exclusivity can be seen as a relatively small price to get rid of a malicious participant.

---

### Practical Non-interactive Multi-signatures, and a Multi-to-Aggregate Signatures Compiler
<a name="rambaudPracticalNoninteractiveMultisignatures2024"></a>

**Authors:** Rambaud, Matthieu; Levrat, Christophe

**Type:** Journal Article
**Date:** 2024
**Publication:** IACR Cryptol. ePrint Arch.
**URL:** [https://www.semanticscholar.org/paper/Practical-Non-interactive-Multi-signatures%2C-and-a-Rambaud-Levrat/4050c50ba2ab9b946927aabafd1351f52249ff70](https://www.semanticscholar.org/paper/Practical-Non-interactive-Multi-signatures%2C-and-a-Rambaud-Levrat/4050c50ba2ab9b946927aabafd1351f52249ff70)

**Abstract:**
> —In a fully non-interactive multi-signature, resp. aggregate-signature scheme (fNIM, resp. fNIA), signatures issued by many signers on the same message, resp. on different messages, can be succinctly “combined”, resp. “aggregated”. fNIMs are used in the Ethereum consensus protocol, to produce the certiﬁcates of validity of blocks which are to be veriﬁed by billions of clients. fNIAs are used in some PBFT-like consensus protocols, such as the production version of Diem by Aptos, to replace the forwarding of many signatures by a new leader. In this work we address three complexity bottlenecks. (i) fNIAs are costlier than fNIMs, e.g., we observe that veriﬁcation time of a 3000-wise aggregate signature of BGLS (Eurocrypt’03), takes 300x longer veriﬁcation time than veriﬁcation of a 3000-wise pairing-based multisignature. (ii) fNIMs impose that each veriﬁer processes the setup published by the group of potential signers. This processing consists either in verifying proofs of possession (PoPs), such as in Pixel (Usenix’20) and in the IETF’22 draft inherited from Ristenpart-Yilek (Eurocrypt’07), which costs a product of pairings over all published keys. Or, it consists in re-randomizing the keys, such as in SMSKR (FC’24). (iii) Existing proven security bounds on efﬁcient fNIMs do not give any guarantee in practical curves with 256bits-large groups, such as BLS12-381 (used in Ethereum) or BLS12-377 (used in Zexe). Thus, computing in much larger curves is required to have provable guarantees. Our ﬁrst contribution is a new fNIM called dms , it addresses both (ii) and (iii). It is as simple as adding Schnorr PoPs to the schoolbook pairing-based

---

### BFT Protocol Forensics
<a name="shengBFTProtocolForensics2021"></a>

**Authors:** Sheng, Peiyao; Wang, Gerui; Nayak, Kartik; Kannan, Sreeram; Viswanath, Pramod

**Type:** Conference Paper
**Date:** 2021-11-12
**Publication:** Proceedings of the 2021 ACM SIGSAC Conference on Computer and Communications Security
**Pages:** 1722-1743
**DOI:** [10.1145/3460120.3484566](https://doi.org/10.1145/3460120.3484566)
**URL:** [http://arxiv.org/abs/2010.06785](http://arxiv.org/abs/2010.06785)

**Abstract:**
> Byzantine fault-tolerant (BFT) protocols allow a group of replicas to come to a consensus even when some of the replicas are Byzantine faulty. There exist multiple BFT protocols to securely tolerate an optimal number of faults $t$ under different network settings. However, if the number of faults $f$ exceeds $t$ then security could be violated. In this paper we mathematically formalize the study of forensic support of BFT protocols: we aim to identify (with cryptographic integrity) as many of the malicious replicas as possible and in as a distributed manner as possible. Our main result is that forensic support of BFT protocols depends heavily on minor implementation details that do not affect the protocol's security or complexity. Focusing on popular BFT protocols (PBFT, HotStuff, Algorand) we exactly characterize their forensic support, showing that there exist minor variants of each protocol for which the forensic supports vary widely. We show strong forensic support capability of LibraBFT, the consensus protocol of Diem cryptocurrency; our lightweight forensic module implemented on a Diem client is open-sourced and is under active consideration for deployment in Diem. Finally, we show that all secure BFT protocols designed for $2t+1$ replicas communicating over a synchronous network forensic support are inherently nonexistent; this impossibility result holds for all BFT protocols and even if one has access to the states of all replicas (including Byzantine ones).

**Tags:** `Computer Science - Cryptography and Security`

---

### Sing a Song of Simplex
<a name="shoupSingSongSimplex2024"></a>

**Authors:** Shoup, Victor; Alistarh, Dan

**Type:** Conference Paper
**Date:** 2024
**Publication:** LIPIcs, Volume 319, DISC 2024
**Volume:** 319
**Pages:** 37:1-37:22
**DOI:** [10.4230/LIPICS.DISC.2024.37](https://doi.org/10.4230/LIPICS.DISC.2024.37)
**URL:** [https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.DISC.2024.37](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.DISC.2024.37)

**Abstract:**
> We flesh out some details of the recently proposed Simplex atomic broadcast protocol, and modify it so that leaders disperse blocks in a more communication-efficient fashion. The resulting protocol, called DispersedSimplex, maintains the simplicity and excellent - indeed, optimal - latency characteristics of the original Simplex protocol. We also present a variant that supports "stable leaders". We also suggest a number of practical optimizations and provide concrete performance estimates that take into account not just network latency but also network bandwidth limitations and computational costs.

**Tags:** `Atomic broadcast`, `Blockchain`, `Consensus`, `Theory of computation → Cryptographic protocols`

---

### Sailfish: Towards Improving the Latency of DAG-based BFT
<a name="shresthaSailfishImprovingLatency"></a>

**Authors:** Shrestha, Nibesh; Shrothrium, Rohan; Nayak, Kartik

**Type:** Conference Paper
**Date:** N/A
**URL:** [https://www.semanticscholar.org/paper/Sailfish%3A-Towards-Improving-the-Latency-of-BFT-Shrestha-Shrothrium/8ed0d9ad847384a7a3b1150654fbb3b14a0010d8](https://www.semanticscholar.org/paper/Sailfish%3A-Towards-Improving-the-Latency-of-BFT-Shrestha-Shrothrium/8ed0d9ad847384a7a3b1150654fbb3b14a0010d8)

**Abstract:**
> —Directed Acyclic Graph (DAG) based BFT protocols balance consensus efforts across different parties and maintain high throughput even when some designated parties fail. However, existing DAG-based BFT protocols exhibit long latency to commit decisions, primarily because they have a leader every 2 or more “rounds”. Recent works, such as Shoal (FC’23) and Mysticeti, have deemed supporting a leader vertex in each round particularly difficult, if not impossible. Consequently, even under honest leaders, these protocols require high latency (or communication complexity) to commit the proposal submitted by the leader (leader vertex) and additional latency to commit other proposals (non-leader vertices). In this work, we present Sailfish, the first DAG-based BFT that supports a leader vertex in each round. Under honest leaders, Sailfish maintains a commit latency of one reliable broadcast (RBC) round plus 1 δ to commit the leader vertex (where δ is the actual transmission latency of a message) and only an additional RBC round to commit non-leader vertices. We also extend Sailfish to Multi-leader Sailfish, which facilitates multiple leaders within a single round and commits all leader vertices in a round with a latency of one RBC round plus 1 δ . Our experimental evaluation demonstrates that our protocols introduce significantly lower latency overhead compared to existing DAG-based protocols, with similar throughput.

---

### Bullshark: DAG BFT Protocols Made Practical
<a name="spiegelmanBullsharkDAGBFT2022"></a>

**Authors:** Spiegelman, Alexander; Giridharan, Neil; Sonnino, Alberto; Kokoris-Kogias, Lefteris

**Type:** Journal Article
**Date:** 2022-11-07
**Publication:** Proceedings of the 2022 ACM SIGSAC Conference on Computer and Communications Security
**Pages:** 2705-2718
**DOI:** [10.1145/3548606.3559361](https://doi.org/10.1145/3548606.3559361)
**URL:** [https://dl.acm.org/doi/10.1145/3548606.3559361](https://dl.acm.org/doi/10.1145/3548606.3559361)

**Abstract:**
> We present Bullshark, the first directed acyclic graph (DAG) based asynchronous Byzantine Atomic Broadcast protocol that is optimized for the common synchronous case. Like previous DAG-based BFT protocols [19, 25], Bullshark requires no extra communication to achieve consensus on top of building the DAG. That is, parties can totally order the vertices of the DAG by interpreting their local view of the DAG edges. Unlike other asynchronous DAG-based protocols, Bullshark provides a practical low latency fast-path that exploits synchronous periods and deprecates the need for notoriously complex view-change and view-synchronization mechanisms. Bullshark achieves this while maintaining all the desired properties of its predecessor DAG-Rider [25]. Namely, it has optimal amortized communication complexity, it provides fairness and asynchronous liveness, and safety is guaranteed even under a quantum adversary. In order to show the practicality and simplicity of our approach, we also introduce a standalone partially synchronous version of Bullshark, which we evaluate against the state of the art. The implemented protocol is embarrassingly simple (200 LOC on top of an existing DAG-based mempool implementation). It is highly efficient, achieving for example, 125,000 transactions per second with a 2 seconds latency for a deployment of 50 parties. In the same setting, the state of the art pays a steep 50% latency increase as it optimizes for asynchrony.

---

### In Search for an Optimal Authenticated Byzantine Agreement
<a name="spiegelmanSearchOptimalAuthenticated2021"></a>

**Authors:** Spiegelman, Alexander; Gilbert, Seth

**Type:** Conference Paper
**Date:** 2021
**Publication:** LIPIcs, Volume 209, DISC 2021
**Volume:** 209
**Pages:** 38:1-38:19
**DOI:** [10.4230/LIPICS.DISC.2021.38](https://doi.org/10.4230/LIPICS.DISC.2021.38)
**URL:** [https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.DISC.2021.38](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.DISC.2021.38)

**Abstract:**
> In this paper, we challenge the conventional approach of state machine replication systems to design deterministic agreement protocols in the eventually synchronous communication model. We first prove that no such protocol can guarantee bounded communication cost before the global stabilization time and propose a different approach that hopes for the best (synchrony) but prepares for the worst (asynchrony). Accordingly, we design an optimistic byzantine agreement protocol that first tries an efficient deterministic algorithm that relies on synchrony for termination only, and then, only if an agreement was not reached due to asynchrony, the protocol uses a randomized asynchronous protocol for fallback that guarantees termination with probability 1. 
We formally prove that our protocol achieves optimal communication complexity under all network conditions and failure scenarios. We first prove a lower bound of Ω(ft+ t) for synchronous deterministic byzantine agreement protocols, where t is the failure threshold, and f is the actual number of failures. Then, we present a tight upper bound and use it for the synchronous part of the optimistic protocol. Finally, for the asynchronous fallback, we use a variant of the (optimal) VABA protocol, which we reconstruct to safely combine it with the synchronous part. 
We believe that our adaptive to failures synchronous byzantine agreement protocol has an independent interest since it is the first protocol we are aware of which communication complexity optimally depends on the actual number of failures.

**Tags:** `Asynchronous fallback`, `Byzantine agreement`, `Optimistic`, `Security and privacy → Distributed systems security`, `Theory of computation → Distributed algorithms`

---

### Consensus Under Adversary Majority Done Right
<a name="sridharConsensusAdversaryMajority2024"></a>

**Authors:** Sridhar, Srivatsan; Tas, Ertem Nusret; Neu, Joachim; Zindros, Dionysis; Tse, David

**Type:** Preprint
**Date:** 2024-11-03
**DOI:** [10.48550/arXiv.2411.01689](https://doi.org/10.48550/arXiv.2411.01689)
**URL:** [http://arxiv.org/abs/2411.01689](http://arxiv.org/abs/2411.01689)

**Abstract:**
> A spectre is haunting consensus protocols-the spectre of adversary majority. The literature is inconclusive, with possibilities and impossibilities running abound. Dolev and Strong in 1983 showed an early possibility for up to 99% adversaries. Yet, we have known impossibility results for adversaries above 1/2 in synchrony, and above 1/3 in partial synchrony. What gives? It is high time that we pinpoint the culprit of this confusion: the critical role of the modeling details of clients. Are the clients sleepy or always-on? Are they silent or communicating? Can validators be sleepy too? We systematize models for consensus across four dimensions (sleepy/always-on clients, silent/communicating clients, sleepy/always-on validators, and synchrony/partial-synchrony), some of which are new, and tightly characterize the achievable safety and liveness resiliences with matching possibilities and impossibilities for each of the sixteen models. To this end, we unify folklore and earlier results, and fill gaps left in the literature with new protocols and impossibility theorems.

**Tags:** `Computer Science - Cryptography and Security`, `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### Stingray: Fast Concurrent Transactions Without Consensus
<a name="sridharStingrayFastConcurrent2025"></a>

**Authors:** Sridhar, Srivatsan; Sonnino, Alberto; Kokoris-Kogias, Lefteris

**Type:** Journal Article
**Date:** 2025
**DOI:** [10.48550/ARXIV.2501.06531](https://doi.org/10.48550/ARXIV.2501.06531)
**URL:** [https://arxiv.org/abs/2501.06531](https://arxiv.org/abs/2501.06531)

**Abstract:**
> Recent advances have improved the throughput and latency of blockchains by processing transactions accessing different parts of the state concurrently. However, these systems are unable to concurrently process (a) transactions accessing the same state, even if they are (almost) commutative, e.g., payments much smaller than an account's balance, and (b) multi-party transactions, e.g., asset swaps. Moreover, they are slow to recover from contention, requiring once-in-a-day synchronization. We present Stingray, a novel blockchain architecture that addresses these limitations. The key conceptual contributions are a replicated bounded counter that processes (almost) commutative transactions concurrently, and a FastUnlock protocol that uses a fallback consensus protocol for fast contention recovery. We prove Stingray's security in an asynchronous network with Byzantine faults and demonstrate on a global testbed that Stingray achieves 10,000 times the throughput of prior systems for commutative workloads.

**Tags:** `Distributed, Parallel, and Cluster Computing (cs.DC)`, `FOS: Computer and information sciences`, `Cryptography and Security (cs.CR)`, `consensusless`

---

### Towards Rational Consensus in Honest Majority
<a name="srivastavaRationalConsensusHonest2024"></a>

**Authors:** Srivastava, Varul; Gujar, Sujit

**Type:** Journal Article
**Date:** 2024-7-23
**Publication:** 2024 IEEE 44th International Conference on Distributed Computing Systems (ICDCS)
**Pages:** 1439-1441
**DOI:** [10.1109/ICDCS60910.2024.00141](https://doi.org/10.1109/ICDCS60910.2024.00141)
**URL:** [https://ieeexplore.ieee.org/document/10631033/](https://ieeexplore.ieee.org/document/10631033/)

**Abstract:**
> Rational Consensus (RC) is a more realistic modelling of the traditional Byzantine Consensus problem, motivated by the recent works in Rational Cryptography. RC is the problem of achieving consensus in the presence of Rational, Byzantine and Honest players (players- participants in the consensus protocol) in a distributed system. This work focuses on consensus in multiple rounds with additional agreement on ordering among rounds which is a more general problem called Atomic BroadCast (ABC). Blockchains is an example of application of ABC. This work abstracts rational players in three types on their incentive structure. We show the impossibility of achieving consensus for two out of the three types of rational players under some conditions. For the third type of rational players, existing work models a single round of agreement and, therefore, doesn't capture the existence of another insecure equilibrium strategy for rational players. We finally fill the gap in the literature of a Rational ABC by proposing a novel protocol for rational consensus, namely pRFT. We prove (i) the correctness of the protocol and (ii) the communication complexity of pRFT, which is a form of accountable protocol, equals the best-known accountable agreement protocols.

---

### Formal Verification of Blockchain Byzantine Fault Tolerance
<a name="tholoniatFormalVerificationBlockchain2019"></a>

**Authors:** Tholoniat, Pierre; Gramoli, Vincent

**Type:** Preprint
**Date:** 2019-10-14
**DOI:** [10.48550/arXiv.1909.07453](https://doi.org/10.48550/arXiv.1909.07453)
**URL:** [http://arxiv.org/abs/1909.07453](http://arxiv.org/abs/1909.07453)

**Abstract:**
> To implement a blockchain, the trend is now to integrate a non-trivial Byzantine fault tolerant consensus algorithm instead of the seminal idea of waiting to receive blocks to decide upon the longest branch. After a decade of existence, blockchains trade now large amounts of valuable assets and a simple disagreement could lead to disastrous losses. Unfortunately, Byzantine consensus solutions used in blockchains are at best proved correct "by hand" as we are not aware of any of them having been formally verified. In this paper, we propose two contributions: (i) we illustrate the severity of the problem by listing six vulnerabilities of blockchain consensus including two new counter-examples; (ii) we then formally verify two Byzantine fault tolerant components of Red Belly Blockchain using the ByMC model checker. First, we specify a simple broadcast primitive in 116 lines of code that is verified in 40 seconds on a 2-core Intel machine. Then, we specify a blockchain consensus algorithm in 276 lines of code that is verified in 17 minutes on a 64-core AMD machine using MPI. To conclude, we argue that it has now become both relatively simple and crucial to formally verify the correctness of blockchain consensus protocols.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### CryptoConcurrency: (Almost) Consensusless Asset Transfer with Shared Accounts
<a name="tonkikhCryptoConcurrencyAlmostConsensusless2023"></a>

**Authors:** Tonkikh, Andrei; Ponomarev, Pavel; Kuznetsov, Petr; Pignolet, Yvonne-Anne

**Type:** Preprint
**Date:** 2023-04-27
**DOI:** [10.48550/arXiv.2212.04895](https://doi.org/10.48550/arXiv.2212.04895)
**URL:** [http://arxiv.org/abs/2212.04895](http://arxiv.org/abs/2212.04895)

**Abstract:**
> A typical blockchain protocol uses consensus to make sure that mutually mistrusting users agree on the order in which their operations on shared data are executed. However, it is known that asset transfer systems, by far the most popular application of blockchains, can be implemented without consensus. Assuming that no account can be accessed concurrently and every account belongs to a single owner, one can efficiently implement an asset transfer system in a purely asynchronous, consensus-free manner. It has also been shown that implementing asset transfer with shared accounts is impossible without consensus. In this paper, we propose CryptoConcurrency, an asset transfer protocol that allows concurrent accesses to be processed in parallel, without involving consensus, whenever possible. More precisely, if concurrent transfer operations on a given account do not lead to overspending, i.e. can all be applied without the account balance going below zero, they proceed in parallel. Otherwise, the account's owners may have to access an external consensus object. Notably, we avoid relying on a central, universally-trusted, consensus mechanism and allow each account to use its own consensus implementation, which only the owners of this account trust. This provides greater decentralization and flexibility.

**Tags:** `Computer Science - Distributed, Parallel, and Cluster Computing`, `consensusless`

---

### Swiper: a new paradigm for efficient weighted distributed protocols
<a name="tonkikhSwiperNewParadigm2024"></a>

**Authors:** Tonkikh, Andrei; Freitas, Luciano

**Type:** Preprint
**Date:** 2024-11-04
**DOI:** [10.48550/arXiv.2307.15561](https://doi.org/10.48550/arXiv.2307.15561)
**URL:** [http://arxiv.org/abs/2307.15561](http://arxiv.org/abs/2307.15561)

**Abstract:**
> The majority of fault-tolerant distributed algorithms are designed assuming a nominal corruption model, in which at most a fraction $f_n$ of parties can be corrupted by the adversary. However, due to the infamous Sybil attack, nominal models are not sufficient to express the trust assumptions in open (i.e., permissionless) settings. Instead, permissionless systems typically operate in a weighted model, where each participant is associated with a weight and the adversary can corrupt a set of parties holding at most a fraction $f_w$ of the total weight. In this paper, we suggest a simple way to transform a large class of protocols designed for the nominal model into the weighted model. To this end, we formalize and solve three novel optimization problems, which we collectively call the weight reduction problems, that allow us to map large real weights into small integer weights while preserving the properties necessary for the correctness of the protocols. In all cases, we manage to keep the sum of the integer weights to be at most linear in the number of parties, resulting in extremely efficient protocols for the weighted model. Moreover, we demonstrate that, on weight distributions that emerge in practice, the sum of the integer weights tends to be far from the theoretical worst case and, sometimes, even smaller than the number of participants. While, for some protocols, our transformation requires an arbitrarily small reduction in resilience (i.e., $f_w = f_n - \epsilon$), surprisingly, for many important problems, we manage to obtain weighted solutions with the same resilience ($f_w = f_n$) as nominal ones. Notable examples include erasure-coded distributed storage and broadcast protocols, verifiable secret sharing, and asynchronous consensus.

**Tags:** `Computer Science - Cryptography and Security`, `Computer Science - Distributed, Parallel, and Cluster Computing`

---

### Thresh-Hold: Assessment of Threshold Cryptography in Leader-Based Consensus
<a name="vonseckThreshHoldAssessmentThreshold2024"></a>

**Authors:** von Seck, Richard; Rezabek, Filip; Carle, Georg

**Type:** Conference Paper
**Date:** 2024-10
**Publication:** 2024 IEEE 49th Conference on Local Computer Networks (LCN)
**Pages:** 1-8
**DOI:** [10.1109/LCN60385.2024.10639786](https://doi.org/10.1109/LCN60385.2024.10639786)
**URL:** [https://ieeexplore.ieee.org/document/10639786](https://ieeexplore.ieee.org/document/10639786)

**Abstract:**
> Byzantine fault tolerant (BFT) systems can be constructed, using the state machine replication (SMR) approach. The usage of threshold cryptography has been widely proposed to confront performance and scalability challenges. We extend the focus on BLS signatures to ECDSA and Schnorr-based schemes and study their impact on BFT-SMR systems. We analyze their suitability for BFT-SMR and study the complexity of four practical, derived schemes. We implement these schemes for the seminal, leader-based HotStuff protocol. Finally, we experimentally quantify both performance impact and replica load under varying threshold schemes and parameters. Architectural constraints limit the applicability of threshold schemes to BFT-SMR. While BLS is the most compatible of the studied schemes, it incurs a significant base cost. We observe that for smaller deployments this increased base cost outweighs the theoretical scaling and performance benefits. Using optimizations such as command batching results in comparable throughput over all studied schemes, albeit with significant latency differences. Our results suggest, that both leader and client are potential bandwidth bottlenecks, already for relatively small payload sizes.

**Tags:** `Bandwidth`, `Costs`, `Digital Signatures`, `Fault tolerance`, `Fault Tolerance`, `Fault tolerant systems`, `Measurement`, `Protocols`, `Scalability`, `Throughput`

---

### Beyond the Whitepaper: Where BFT Consensus Protocols Meet Reality
<a name="wongWhitepaperWhereBFT2024"></a>

**Authors:** Wong, David; Kolegov, Denis; Mikushin, Ivan

**Type:** Preprint
**Date:** 2024
**URL:** [https://eprint.iacr.org/2024/1242](https://eprint.iacr.org/2024/1242)

**Abstract:**
> This paper presents a collection of lessons learned from analyzing the real-world security of various Byzantine Fault Tolerant (BFT) consensus protocol implementations. Drawing upon our experience as a team of security experts who have both developed and audited BFT systems, including BA★, HotStuff variants, Paxos variants, and DAG-based algorithms like Narwhal and Bullshark, we identify and analyze a variety of security vulnerabilities discovered in the translation of theoretical protocols into real-world code. Our analysis covers a range of issues, including subtle logic errors, concurrency bugs, cryptographic vulnerabilities, and mismatches between the theoretical model and the implementation. We provide detailed case studies illustrating these vulnerabilities, discuss their potential impact, and propose mitigation strategies. This work aims to provide valuable insights for both designers and implementers of BFT consensus protocols, ultimately contributing to the development of more secure and reliable distributed systems.

**Tags:** `BFT consensus`, `implementation vulnerabilities`, `real-world security`, `security analysis`

---

### Optimal Sharding for Scalable Blockchains with Deconstructed SMR
<a name="zhangOptimalShardingScalable2024"></a>

**Authors:** Zhang, Jianting; Luo, Zhongtang; Ramesh, Raghavendra; Kate, Aniket

**Type:** Preprint
**Date:** 2024-10-05
**DOI:** [10.48550/arXiv.2406.08252](https://doi.org/10.48550/arXiv.2406.08252)
**URL:** [http://arxiv.org/abs/2406.08252](http://arxiv.org/abs/2406.08252)

**Abstract:**
> Sharding is proposed to enhance blockchain scalability. However, a size-security dilemma where every shard must be large enough to ensure its security constrains the efficacy of individual shards and the degree of sharding itself. Most existing sharding solutions therefore rely on either weakening the adversary or making stronger assumptions on network links. This paper presents Arete, an optimally scalable blockchain sharding protocol designed to resolve the dilemma based on an observation that if individual shards can tolerate a higher fraction of (Byzantine) faults, we can securely create smaller shards in a larger quantity. The key idea of Arete, therefore, is to improve the security resilience/threshold of shards by dividing the blockchain's State Machine Replication (SMR) process itself. Similar to modern blockchains, Arete first decouples SMR in three steps: transaction dissemination, ordering, and execution. However, unlike other blockchains, for Arete, a single ordering shard performs the ordering task while multiple processing shards perform the dissemination and execution of blocks. As processing shards do not run consensus, each of those can tolerate up to half compromised nodes. Moreover, the SMR process in the ordering shard is lightweight as it only operates on the block digests. Second, Arete considers safety and liveness against Byzantine failures separately to improve the safety threshold further while tolerating temporary liveness violations in a controlled manner. Apart from the creation of more optimal-size shards, such a deconstructed SMR scheme also empowers us to devise a novel certify-order-execute architecture to fully parallelize transaction handling, thereby improving the performance of sharding systems. We implement Arete and evaluate it on a AWS environment by running up to 500 nodes, showing that Arete outperforms the state-of-the-art sharding protocol.

**Tags:** `Computer Science - Cryptography and Security`
