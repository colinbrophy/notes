

  Terminate a process using the default SIGTERM (terminate) signal:

      killall process_name

  List available signal names (to be used without the `SIG` prefix):

      killall [-l|--list]

  Interactively ask for confirmation before termination:

      killall [-i|--interactive] process_name

  Terminate a process using the SIGINT (interrupt) signal, which is the same signal sent by pressing `<Ctrl c>`:

      killall -INT process_name

  Force kill a process:

      killall -KILL process_name