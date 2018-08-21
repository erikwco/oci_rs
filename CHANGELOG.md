# Change Log

## v0.8.0

Added support for setting the pre-fetch value and fixed a bug that caused bind parameters to be read from wrong memory addresses.

## v0.7.0

Merges in support for windows via the `windows-gnu` toolchain along with some tidying up 
refactoring. Thanks for the contributions.

## v0.6.0

Fixes issue #4. Now the library correctly handles database that are not configured to use 24 hour clock. In previous versions dates on the Rust side were converted into string representations before passing to OCI. This fell apart when the format didn't match the time setup in the DB. This version uses the Oracle binary format instead, thereby avoiding any question of formatting. Fixes issue #2 where infinte loops could be created during DB log on. Fixes issue #3 where panics could dump ugly bytes at the end of error messages.

## v0.5.0

Support for `CHAR` and `TIMESTAMP WITH TIMEZONE` added.

## v0.4.0

Support for `DATE` and `TIMESTAMP` added. On the Rust side this are converted into Date<Utc> and DateTime<Utc> from the chrono crate respectively.
