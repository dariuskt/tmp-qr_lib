reproducing kibot `qr_lib` config problem


defining dir for output files created defined dir, 
but files are created in the project dir anyways, 
and footprint is always in the `project-qr.pretty` dir

```yaml
  - name: qr_lib
    type: qr_lib
    dir: '../project/lib/qr'
    options:
      qrs:
        - text: 'url-to-current-board-documentation'
```



![PCB 3d main](gen/img_pcb_3d_main.png)




Dev NOTE: before commit, run `./kibot.sh` to regenerate documentation, gerbers and other assets.

* [schematics.pdf](gen/schematics.pdf)
* [pcb.pdf with dimensions](gen/pcb.pdf)

![PCB 2d front bare](gen/img_pcb_2d_front_bare.jpg)
![PCB 2d back bare](gen/img_pcb_2d_back_bare.jpg)

![PCB 3d front](gen/img_pcb_3d_front.png)



