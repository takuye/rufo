# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]
### Added
- Added Idempotency check to source_specs/ tester.

## Fixed
- Fix printing of extraneous trailing semicolons from inline classes, modules, methods (issue [#59](https://github.com/ruby-formatter/rufo/issues/59))
- Fix unhandled white space between array getter/setters `x[0] [0]` (issue [#62](https://github.com/ruby-formatter/rufo/issues/62))

## [0.2.0] - 2017-11-13
### Changed
Config parsing and handling:
- No longer using `eval` to parse config files
- Warnings have been added for invalid config keys and values

The default for the following options has changed:
- parens_in_def: `:dynamic` > `:yes`
- trailing_commas: `:dynamic` > `true`

Valid options for:
- trailing_commas: `[:always, :never]` > `[true, false]`

### Removed
The following configuration options have been **removed**, and replaced with non-configurable sane defaults, [per discussion](https://github.com/ruby-formatter/rufo/issues/2):
- align_assignments
- align_comments
- align_hash_keys
- indent_size
- spaces_after_comma
- spaces_after_lambda_arrow
- spaces_around_block_brace
- spaces_around_dot
- spaces_around_equal
- spaces_around_hash_arrow
- spaces_around_unary
- spaces_around_when
- spaces_in_commands
- spaces_in_suffix
- spaces_in_ternary
- spaces_inside_array_bracket
- spaces_inside_hash_brace
- visibility_indent
- double_newline_inside_type
- spaces_around_binary

### Fixed
- Fix crash in Ruby <= 2.3.4, <= 2.4.1 in the presence of certain squiggly doc (`<<~`) with multiple embedded expressions. The real fix here is to upgrade Ruby to >= 2.3.5 / >= 2.4.2
- Fix dedent bug and bad formatting caused by comments within chained calls (issue [#49](https://github.com/ruby-formatter/rufo/issues/49))
- Fix formatting bug for `for i, in [[1, 2]] ; x ; end` (issue [#45](https://github.com/ruby-formatter/rufo/issues/45))

## [0.1.0] - 2017-10-08
Beginning of logging changes!
