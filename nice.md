nice -n 19 grep -ri "config.json" . --exclude-dir=node_modules 2>/dev/null

  -n 19 is lowest priority (nicest to other processes).