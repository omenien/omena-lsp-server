# omena-lsp-server

`omena-lsp-server` owns the Rust language-server runtime boundary for Omena.

The crate currently provides:

- a standalone stdio LSP executable (`omena-lsp-server`);
- a serializable boundary summary for VS Code and multi-editor integration;
- Rust-owned document lifecycle, workspace folder, watcher, diagnostics, hover,
  definition, references, completion, code action, code lens, and rename request
  handling;
- explicit thin-client endpoint metadata for hosts that only need to launch the
  Rust server and register static file watchers.

This crate is the split publish target for the post-4.0 LSP migration. It keeps
Node fallback out of the primary runtime path and consumes `omena-tsgo-client` as
its TypeScript 7 source-fact boundary.
