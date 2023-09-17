reproducing kibot `qr_lib` config problem


using minimal config, assuming all other defaults are ok for me

```yaml
  - name: qr_lib
    type: qr_lib
    options:
      output: 'lib/footprint/qr.kicad_mod'
      qrs:
        - text: 'url-to-current-board-documentation'
```

runtime errors, I assumed I dont need to delete configuration after first use.

```
- '' (qr_lib) [qr_lib]
Traceback (most recent call last):
  File "/usr/bin/kibot", line 33, in <module>
    sys.exit(load_entry_point('kibot==1.6.0', 'console_scripts', 'kibot')())
  File "/usr/lib/python3/dist-packages/kibot/__main__.py", line 403, in main
    generate_outputs(outputs, args.target, args.invert_sel, args.skip_pre, args.cli_order, args.no_priority,
  File "/usr/lib/python3/dist-packages/kibot/kiplot.py", line 515, in generate_outputs
    _generate_outputs(outputs, targets, invert, skip_pre, cli_order, no_priority, dont_stop)
  File "/usr/lib/python3/dist-packages/kibot/kiplot.py", line 506, in _generate_outputs
    run_output(out, dont_stop)
  File "/usr/lib/python3/dist-packages/kibot/kiplot.py", line 419, in run_output
    out.run(get_output_dir(out.dir, out))
  File "/usr/lib/python3/dist-packages/kibot/out_base.py", line 192, in run
    self.options.run(self.expand_filename(output_dir, output))
  File "/usr/lib/python3/dist-packages/kibot/out_qr_lib.py", line 524, in run
    os.makedirs(dir_pretty, exist_ok=True)
  File "/usr/lib/python3.9/os.py", line 225, in makedirs
    mkdir(name, mode)
FileExistsError: [Errno 17] File exists: '/tmp/workdir/project/lib/footprint/qr.kicad_mod'
```

trying to load footprint editor

```
Errors were encountered loading footprints:
Unknown token 'kicad_symbol_lib' in '.../test-lib-qr/project/lib/footprint/qr.kicad_mod', line 1, offset 2. 
```



![PCB 3d main](gen/img_pcb_3d_main.png)




Dev NOTE: before commit, run `./kibot.sh` to regenerate documentation, gerbers and other assets.

* [schematics.pdf](gen/schematics.pdf)
* [pcb.pdf with dimensions](gen/pcb.pdf)

![PCB 2d front bare](gen/img_pcb_2d_front_bare.jpg)
![PCB 2d back bare](gen/img_pcb_2d_back_bare.jpg)

![PCB 3d front](gen/img_pcb_3d_front.png)



