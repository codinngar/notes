```bash
# choosing the fastest 20 mirrors
sudo reflector --verbose --completion-percent 100 --protocol https --score 20 --sort rate --save /etc/pacman.d/mirrorlist
```