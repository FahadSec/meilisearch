FROM fuzzers/cargo-fuzz:0.11.0 as builder

ADD . /meilisearch
WORKDIR /meilisearch

RUN cd json-depth-checker/fuzz/ && cargo fuzz build

FROM ubuntu:20.04

COPY --from=builder /meilisearch/json-depth-checker/fuzz/target/x86_64-unknown-linux-gnu/release/depth /
