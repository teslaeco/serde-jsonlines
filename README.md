[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip) <!-- [![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active) -->
[![CI Status](https://github.com/jwodder/jsonlines/actions/workflows/test.yml/badge.svg)](https://github.com/jwodder/jsonlines/actions/workflows/test.yml)
[![codecov.io](https://codecov.io/gh/jwodder/jsonlines/branch/master/graph/badge.svg)](https://codecov.io/gh/jwodder/jsonlines)
[![MIT License](https://img.shields.io/github/license/jwodder/jsonlines.svg)](https://opensource.org/licenses/MIT)

[GitHub](https://github.com/jwodder/jsonlines) <!-- | [crates.io](https://crates.io/crates/jsonlines) | [Documentation](https://docs.rs/jsonlines) --> | [Issues](https://github.com/jwodder/jsonlines/issues)

JSON Lines (a.k.a. newline-delimited JSON) is a simple format for storing
sequences of JSON values in which each value is serialized on a single line and
terminated by a newline sequence.  The `jsonlines` crate provides functionality
for reading & writing these documents (whether all at once or line by line)
using `serde`'s serialization & deserialization features.

Basic usage involves simply importing the `BufReadExt` or `WriteExt` extension
trait and then using the `json_lines()` or `write_json_lines()` method on a
`BufRead` or `Write` value to read or write a sequence of JSON Lines values.
Convenience functions are also provided for the common case of reading or
writing a JSON Lines file given as a filepath.

At a lower level, values can be read or written one at a time (which is useful
if, say, different lines are different types) by wrapping a `BufRead` or
`Write` value in a `JsonLinesReader` or `JsonLinesWriter` and then calling the
wrapped structure's `read()` or `write()` method, respectively.
