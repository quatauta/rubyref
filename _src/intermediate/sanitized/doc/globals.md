## Pre-defined global variables

* `$!`: The Exception object set by `Kernel#raise`.
* `$@`: The same as `$!.backtrace`.
* `$~`: The information about the last match in the current scope (thread-local
    and frame-local).

* `$&`: The string matched by the last successful match.
* <code class="highlighter-rouge">$`</code>: The string to the left  of the last successful match.
* `$'`: The string to the right of the last successful match.
* `$+`: The highest group matched by the last successful match.
* `$1`: The Nth group of the last successful match. May be > 1.
* `$=`: This variable is no longer effective. Deprecated.
* `$/`: The input record separator, newline by default. Aliased to `$-`0.
* `$\`: The output record separator for `Kernel#print` and `IO#write`. Default is
    `nil`.

* `$,`: The output field separator for `Kernel#print` and `Array#join`. Non-nil $,
    will be deprecated.

* `$;`: The default separator for `String#split`. Non-nil $; will be deprecated.
    Aliased to `$-`F.

* `$.`: The current input line number of the last file that was read.
* `$<`: The same as ARGF.
* `$>`: The default output stream for `Kernel#print` and `Kernel#printf`. `$stdout` by
    default.

* `$_`: The last input line of string by gets or readline.
* `$0`: Contains the name of the script being executed. May be assignable.
* `$*`: The same as ARGV.
* `$$`: The process number of the Ruby running this script. Same as Process.pid.
* `$?`: The status of the last executed child process (thread-local).
* `$LOAD_PATH`: Load path for searching Ruby scripts and extension libraries used by
    Kernel#load and Kernel#require. Aliased to `$:` and $-I. Has a singleton
    method `$LOAD_PATH.resolve_feature_path(feature)` that returns [`:rb` or
    `:so`, path], which resolves the feature to the path the original
    Kernel#require method would load.

* `$LOADED_FEATURES`: The array contains the module names loaded by require. Aliased to `$"`.
* `$DEBUG`: The debug flag, which is set by the `-d` switch.  Enabling debug output
    prints each exception raised to `$stderr` (but not its backtrace).  Setting
    this to a true value enables debug output as if `-d` were given on the
    command line.  Setting this to a false value disables debug output.
    Aliased to `$-`d.

* `$FILENAME`: Current input filename from ARGF. Same as ARGF.filename.
* `$stderr`: The current standard error output.
* `$stdin`: The current standard input.
* `$stdout`: The current standard output.
* `$VERBOSE`: The verbose flag, which is set by the `-w` or `-v` switch. Setting this to
    a true value enables warnings as if `-w` or `-v` were given on the command
    line.  Setting this to `nil` disables warnings, including from
    Kernel#warn. Aliased to `$-`v and $-w.

* `$-a`: True if option `-a` is set. Read-only variable.
* `$-i`: In in-place-edit mode, this variable holds the extension, otherwise `nil`.
* `$-l`: True if option `-l` is set. Read-only variable.
* `$-p`: True if option `-p` is set. Read-only variable.


## Pre-defined global constants

* `TRUE`: The typical true value. Deprecated.
* `FALSE`: The `false` itself. Deprecated.
* `NIL`: The `nil` itself. Deprecated.
* `STDIN`: The standard input. The default value for `$stdin`.
* `STDOUT`: The standard output. The default value for `$stdout`.
* `STDERR`: The standard error output. The default value for $stderr.
* `ENV`: The hash contains current environment variables.
* `ARGF`: The virtual concatenation of the files given on command line (or from
    `$stdin` if no files were given).

* `ARGV`: An Array of command line arguments given for the script.
* `DATA`: The file object of the script, pointing just after `__END__`.
* `TOPLEVEL_BINDING`: The Binding of the top level scope.
* `RUBY_VERSION`: The Ruby language version.
* `RUBY_RELEASE_DATE`: The release date string.
* `RUBY_PLATFORM`: The platform identifier.
* `RUBY_PATCHLEVEL`: The patchlevel for this Ruby.  If this is a development build of Ruby the
    patchlevel will be -1.

* `RUBY_REVISION`: The GIT commit hash for this Ruby.
* `RUBY_COPYRIGHT`: The copyright string for Ruby.
* `RUBY_ENGINE`: The name of the Ruby implementation.
* `RUBY_ENGINE_VERSION`: The version of the Ruby implementation.
* `RUBY_DESCRIPTION`: The same as `ruby --version`, a String describing various aspects of the
    Ruby implementation.