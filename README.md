### Vayne - Mustache-inspired template compiler and interpreter for D

Vayne has been written mainly for use with vibe.d but it can be used in any other way.
It is the successor to jax, a compile-time solution.

Compiles source text/html into bytecode to be interpreted at run time.

### Features
- HTML compressor
- Parametrized macros
- Good and detailed error reporting
- Supports user defined escaping and translation


#### Options
	-r --print-preparse print preparser result
	-a      --print-ast print ast
	-i   --print-instrs print generated instructions
	-k   --print-consts print generated constant slots
	-b --print-bytecode print generated bytecode and instructions
	-t           --time display elapsed time
	-v        --verbose verbose output
	-c       --compress compress HTML in between template tags
	-o     --output-dir output directory
	-d  --dep-cache-dir dependant-cache directory
	-g   --dep-gen-only only generate dependant-cache, do not re-compile dependants
	-j         --search search path(s) to look for source files
	-e    --default-ext default source file extension (defaults to .html)


#### Tags
	{{& fileName }} - Include external template file
	{{% fileName }} - Embed external raw file
	{{%% fileName }} - Embed external file as mime-encoded content
	{{* key, value; iterable }} {{key}} {{value}} {{/}} - Iterate any iteratable symbol
	{{? expr }} true case {{: [expr] }} else case {{/}}
	{{@ expr0, expr2 as ident }} - Create symbol scopes or named copy of expressions. For symbol scopes, expression must evalute to an object or associative array.
	{{! comment }} - Comment
	{{ expr }} - Write expression to output with automatic HTML escaping
	{{{ expr }}} - Write expression to output without escaping
	{{~ message-id-expr, arg0+ }} - Translate message-id with arguments and output - use triple brackets to disable escaping
	{{#def myMacro(arg) }} macro text {{#arg}} {{#/}}
	{{#myMacro("mooo") }} - Expand a macro


Check the example directory for a working example.
