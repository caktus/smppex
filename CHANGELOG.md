# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [2.0.0] - 2017-08-30
This release contains significant architectural changes and API incompatibilities.

### Changed
- Added single `SMPPEX.Session` behavior instead of seperate `SMPPEX.ESME` and `SMPPEX.MC` behaviours.
- `SMPPEX.Session` callbacks are more `GenServer` compliant.
- Most of `SMPPEX.Session` callbacks are allowed to return stop indicating tuple.
- Most of `SMPPEX.Session` callbacks are allowed to return a list of PDUs to send.
- All methods interacting with `SMPPEX.Session` are synchronous.

### Added
- Elixir 1.5 builds in CI.

### Removed
- Usage of a separate process for ESME/MC connections.
- Usage of `ranch` supervisor of launching ESME connections.
- Special methods for sending PDU replies to ESME/MC in favor of `Pdu.as_reply_to/2` method.

## [1.0.1] - 2017-08-30
### Changed
- `ex_doc` updated to 1.x.


## [1.0.0] - 2017-08-30
This is the first stable release introduced from numerous 0.x.x versions. Although this library has been already used in production for quite a while, it's only purpose is to designate the divergence from 2.x.x branch.

### Added
- ESME functionality.
- MC functionality.
- Synchronous ESME client.