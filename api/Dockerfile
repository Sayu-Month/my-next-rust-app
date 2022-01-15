FROM rust:1.57

WORKDIR /api
COPY Cargo.toml Cargo.toml

RUN mkdir src
RUN echo "fn main(){}" > src/main.rs
RUN cargo build --release

COPY . .
RUN rm -f target/release/deps/api*
RUN cargo build --release
RUN cargo install --path .

CMD ["api"]
