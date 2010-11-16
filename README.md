This is my version of a plugin to allow vim to push code to a running iPython
instance. The two can be started separately, for iPython, you need to add the
following code to the 'main()' function in your iPython config::

~~~
    def _start_vim_server_f(self, parameter_s=''):
        import ipy_vimserver
        server = "vimserver"
        if parameter_s != '': server = parameter_s
        ipy_vimserver.setup(server)
    ip.expose_magic('vimserver', _start_vim_server_f)
~~~

Then you can call %vimserver [servername], and the iPython will listen for
code from vim. In vim, you can use any of the commands defined at the end
of the plugin.

Patches welcome!
