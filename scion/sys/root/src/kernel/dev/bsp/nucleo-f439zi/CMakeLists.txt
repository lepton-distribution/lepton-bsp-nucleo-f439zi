# BSP nucleo-f429zi : paramètres hors manifeste (PA-7 Q3), inclus par le CMakeLists.txt racine
# du greffon noyau quand LEPTON_BOARD=nucleo-f429zi. XML mklepton : LEPTON_MKCONF du preset.
# HSE_VALUE (manifeste) : MCO du ST-LINK (8 MHz, HSE en bypass), UM1974.
set(LEPTON_NET_STACK lwip)   # USE_LWIP dans include/user_kernel_mkconf.h
set(LEPTON_BOARD_UNAME_MACHINE cortexM4-stm32f4)   # __KERNEL_CPU_DEVICE_NAME (kernelconf.h)
# carte réelle (étape 5) : console série du ST-LINK (sonde : manifeste, champ openocd)
set(LEPTON_BOARD_SERIAL_PORT "" CACHE STRING
    "Port série de la console de la carte (ex. /dev/ttyACM0) : active le test de fumée sur carte")
# test réseau sur carte (labels board et net, tests/board_net.py) : adresse de la carte (.init),
# fichier téléchargé par FTP et sa source ; l'adresse de l'hôte sur le câble de la carte dépend
# du banc (ex. 192.168.2.20) : vide, le test n'est pas créé
set(LEPTON_NET_TEST_GUEST_IP 192.168.2.5)
set(LEPTON_NET_TEST_FTP_FILE /usr/etc/.boot)
set(LEPTON_NET_TEST_FTP_REFERENCE sys/user/tauon-basic/etc/nucleo-f439zi/.boot)
set(LEPTON_NET_TEST_HOST_IP "" CACHE STRING
    "Adresse de l'hôte sur le lien Ethernet de la carte : active le test réseau sur carte")
