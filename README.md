# Troca de kernel labrador32
Troca de Kernel 4.19 para 4.14 na labrador32 para utilização da biblioteca wiringK9 ou bluetooh

Clone o repositorio:

      git clone https://github.com/DelioMg/troca-de-kernel-labrador32
      
      cd troca-de-kernel-labrador32
 
Criar diretório e montar partição

       sudo mkdir /media/caninos/BOOT
       sudo mount /dev/mmcblk2p1 /media/caninos/BOOT

Copiar “kernel.dtb” e “uImage” para a raíz da partição BOOT

       sudo cp -r kernel.dtb /media/caninos/BOOT
       sudo cp -r uImage /media/caninos/BOOT

Copiar “lib/modules” para “lib/modules” da partição SYSTEM:

       sudo cp -r modules /lib/

Criar arquivo e adicionar linha “blacklist labrador_s500_thermal” em “/etc/modprobe.d/blacklist.conf”

       sudo su
       echo "blacklist labrador_s500_thermal" >> /etc/modprobe.d/blacklist.conf"
       Ctrl+c

Desmontar partição e excluir diretório

       sync
       umount /media/caninos/BOOT
       rm -r /media/caninos/BOOT/

Reiniciar a Labrador

       exit
       sudo reboot

Procedimento base retirado do forum.caninosloucos.org
