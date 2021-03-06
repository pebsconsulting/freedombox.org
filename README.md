# freedombox.org

Source code for the [freedombox.org](https://freedombox.org/) website

## Compiling

freedombox.org is a simple set of static web pages.  These pages are
generated by a static site generator called
[lektor](https://www.getlektor.com/).  To see the final HTML output of
this source code one needs to install lektor and compile with it.

1. Install dependencies.

        $ sudo apt install virtualenv python-dev libssl-dev

2. Create a virtual python environment.  Lektor is not available as a
   Debian package so we install it from source code.  In order not to
   mess up the existing system with its installation and to be able
   use it without administrator privileges, will install in a Python
   virtual environment (basically a directory) and use the environment
   whenever we need lektor.

        $ virtualenv lektorenv

3. Activate the environment.  This will set proper Python paths
   etc. so that when Python packages are installed, they will be done
   to this virtual environment directory.

        $ source lektorenv/bin/activate

4. Install lektor.

        $ pip install lektor

5. Compile the project.

        $ lektor build

    This will create an output directory in ~/.cache/lektor/builds and
    place all the generated files there.  If you wish to output to a
    specific directory do it as follows:

        $ lektor build --output-path=my_build_output_dir

## Recompling

To recompile the project, simply activate the virtual environment and
compile the project.

## Lektor's Web Interface

Lektor provides a built-in web server that is useful for creating new
content.  Instead of editing lektor files for creating new pages, one
can create that them from a simple web interface provided by lektor
server.  Creating new models, flowblocks, styling content etc. will
still need to be done using regular text editors.

When a server is started, any changes to source directory will
automatically result in a rebuild of the project.

1. To run lektor server.

        $ lektor server

    This will start a web server on 5000 port and will also start
    monitoring your source code directory for changes to build them
    immediately.

2. Visit http://localhost:5000
