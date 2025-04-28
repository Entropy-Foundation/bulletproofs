# Bulletproofs

<img
 width="100%"
 src="https://doc.dalek.rs/assets/bulletproofs-rangeproof.png"
/>

The fastest [Bulletproofs][bp_website] implementation ever, featuring
single and aggregated range proofs, strongly-typed multiparty
computation, and a programmable constraint system API for proving
arbitrary statements (under development).

This library implements Bulletproofs using [Bls12381][bls12381]. 

This library provides implementations of:

* Single-party proofs of single or multiple ranges, using the
  aggregated rangeproof construction;

* Online multi-party computation for rangeproof aggregation between
  multiple parties, using [session types][session_type_blog] to
  statically enforce correct protocol flow;

* Online multi-party computation for aggregated constraint system proofs
  (planned future work).

These proofs are implemented using [Merlin transcripts][doc_merlin],
allowing them to be arbitrarily composed with other proofs without
implementation changes.

The development roadmap can be found in the
[Milestones][gh_milestones] section of the [Github repo][gh_repo].

## Documentation
  
The user-facing documentation for this functionality can be [found
here][doc_external].  In addition, the library *also* contains
extensive notes on how Bulletproofs work.  These notes can be found in
the library's [internal documentation][doc_internal]:

* how [Bulletproofs work][bp_notes];
* how [the range proof protocol works][rp_notes];
* how [the inner product proof protocol works][ipp_notes];
* how [the aggregation protocol works][agg_notes];
* how the Bulletproof constraint system proofs work (under development);
* how the constraint system reduction works (under development);
* how the aggregated constraint system proofs work (future work).

## Building

To compile successfully, you will need to have nightly Rust installed, rather than stable.

You can install nightly Rust with rustup:

```text
rustup default nightly
```

## Tests and Benchmarks

Run tests with `cargo test`.  Run benchmarks with `cargo bench`.  This crate
uses [criterion.rs][criterion] for benchmarks.

## About

This is a research project sponsored by [Interstellar][interstellar],
developed by Henry de Valence, Cathie Yun, and Oleg Andreev.

[bp_website]: https://crypto.stanford.edu/bulletproofs/
[doc_merlin]: https://doc.dalek.rs/merlin/index.html
[doc_external]: https://doc.dalek.rs/bulletproofs/index.html
[doc_internal]: https://doc-internal.dalek.rs/bulletproofs/index.html
[bp_notes]: https://doc-internal.dalek.rs/bulletproofs/notes/index.html
[ipp_notes]: https://doc-internal.dalek.rs/bulletproofs/inner_product_proof/index.html
[agg_notes]: https://doc-internal.dalek.rs/bulletproofs/notes/index.html#aggregated-range-proof
[criterion]: https://github.com/japaric/criterion.rs
[session_type_blog]: https://blog.chain.com/bulletproof-multi-party-computation-in-rust-with-session-types-b3da6e928d5d
[parallel_edwards]: https://medium.com/@hdevalence/accelerating-edwards-curve-arithmetic-with-parallel-formulas-ac12cf5015be
[gh_repo]: https://github.com/dalek-cryptography/bulletproofs/
[gh_milestones]: https://github.com/dalek-cryptography/bulletproofs/milestones
[interstellar]: https://interstellar.com/
