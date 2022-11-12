# Troca de kernel labrador32
Troca de Kernel 4.19 para 4.14 na labrador32 para utilização da biblioteca wiringK9 ou bluetooh

Pra isso você pode baixar somente os arquivos do kernel 2 e seguir esse tutorial ótimo escrito pelo @thalyson:

    Criar diretório e montar partição

sudo mkdir /media/caninos/BOOT
sudo mount /dev/mmcblk2p1 /media/caninos/BOOT

    Copiar “kernel.dtb” e “uImage” para a raíz da partição BOOT

sudo cp -r /src/kernel.dtb /media/caninos/BOOT
sudo cp -r /src/uImage /media/caninos/BOOT

    Copiar “lib/modules” para “lib/modules” da partição SYSTEM:

sudo cp -r /src/lib/modules /lib/

    Criar arquivo e adicionar linha “blacklist labrador_s500_thermal” em “/etc/modprobe.d/blacklist.conf”

sudo su
echo "blacklist labrador_s500_thermal" >> /etc/modprobe.d/blacklist.conf"

    Desmontar partição e excluir diretório

sudo sync
sudo umount /media/caninos/BOOT
sudo rm -r /media/caninos/BOOT/

    Reiniciar a Labrador

sudo reboot

Obs: “src” é o diretório fonte onde está o kernel a ser instalado

Procedimento retirado de forum.caninosloucos.org.
