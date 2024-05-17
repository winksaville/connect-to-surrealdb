# Connect-to-SurrealDB

Example [connect-to-surrealdb](https://surrealdb.com/docs/surrealdb/embedding/rust#connect-to-surrealdb)

Added crated as suggested in [Install the SDK](https://surrealdb.com/docs/surrealdb/embedding/rust#install-the-sdk)

Added crates:
```
cargo add surrealdb --features kv-mem 
cargo add serde --features derive
cargo add tokio --features macros,rt-multi-thread
```

## Run

Debug:
`cargo run` or `target/debug/connect-to-surrealdb`

Release:
`cargp run --release` or `target/release/connect-to-surrealdb`

```
wink@3900x 24-05-17T22:05:59.698Z:~/prgs/SurrealDB/connect-to-surrealdb (main)
$ cargo run
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.15s
     Running `target/debug/connect-to-surrealdb`
[src/main.rs:50:5] created = [
    Record {
        id: Thing {
            tb: "person",
            id: String(
                "n8rhocjljm2lqqqpya3u",
            ),
        },
    },
]
[src/main.rs:57:5] updated = Some(
    Record {
        id: Thing {
            tb: "person",
            id: String(
                "jaime",
            ),
        },
    },
)
[src/main.rs:61:5] people = [
    Record {
        id: Thing {
            tb: "person",
            id: String(
                "jaime",
            ),
        },
    },
    Record {
        id: Thing {
            tb: "person",
            id: String(
                "n8rhocjljm2lqqqpya3u",
            ),
        },
    },
]
[src/main.rs:68:5] groups = Response {
    client: Surreal {
        router: OnceLock(
            Router {
                sender: Sender,
                last_id: 0,
                features: {
                    LiveQueries,
                    Backup,
                },
            },
        ),
        engine: PhantomData<surrealdb::api::engine::any::Any>,
    },
    results: {
        0: (
            Stats {
                execution_time: Some(
                    282.31µs,
                ),
            },
            Ok(
                Array(
                    Array(
                        [
                            Object(
                                Object(
                                    {
                                        "count": Number(
                                            Int(
                                                2,
                                            ),
                                        ),
                                        "marketing": Bool(
                                            true,
                                        ),
                                    },
                                ),
                            ),
                        ],
                    ),
                ),
            ),
        ),
    },
    live_queries: {},
}
wink@3900x 24-05-17T22:06:02.748Z:~/prgs/SurrealDB/connect-to-surrealdb (main)
```

## License

Licensed under either of

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or http://apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall
be dual licensed as above, without any additional terms or conditions.
