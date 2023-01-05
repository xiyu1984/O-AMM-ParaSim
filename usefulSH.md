
cargo check -p node-template-runtime --release

cargo build --package node-template --release

./target/release/node-template --dev

cargo test  -- --nocapture