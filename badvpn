
#!/bin/bash

# GAMBIARRA FEITA POR UM NOOB ENTEDIADO

fun_atualiza () {

rm -rf $HOME/badvpn.sh
rm -rf $HOME/kill.sh
rm -rf /etc/badvpn.sh
rm -rf /etc/kill.sh
rm -rf /etc/badres.sh
killall badvpn-udpgw > /dev/null 2>&1
touch /etc/badvpn.sh
touch /etc/badres.sh
chmod +x /etc/badvpn.sh
chmod +x /etc/badres.sh

echo "
#!/bin/bash

killall badvpn-udpgw
sleep 5
/bin/bash /etc/badvpn.sh" > /etc/badres.sh

cat > /etc/badvpn.sh << EOF
#!/bin/bash

screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7100 --max-clients 5000 --max-connections-for-client 1000; screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7200 --max-clients 5000 --max-connections-for-client 1000; screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7300 --max-clients 5000 --max-connections-for-client 1000; screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7400 --max-clients 5000 --max-connections-for-client 1000; screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7500 --max-clients 5000 --max-connections-for-client 1000
EOF

echo ""
while read -p "$(echo "Escolha o intervalo para Reset do BadVPN [1h-24h]: ")" _jikan ; do
if [[ $_jikan =~ ^[0-9]+$ ]] && (( $_jikan >= 1 && $_jikan <= 24)); then
(crontab -l; echo "00 */$_jikan * * * /etc/badres.sh") | crontab -
crontab -l | sed "s|.*badres.sh|00 */$_jikan * * * /etc/badres.sh|g" | crontab -
(crontab -l; echo "@reboot /etc/badvpn.sh") | awk '!x[$0]++' | crontab -

break
	else
		echo ""
		echo "Apenas Numeros de 1 a 24 zé mané"
	fi
	done
		echo ""
		sleep 1.5
		echo "Atualizado!"
rm -rf bad.sh
}

fun_conf () {

echo "Atualizando repositorios..."
echo ""
clear
apt-get update && apt-get install psmisc -y

killall badvpn-udpgw > /dev/null 2>&1
touch /etc/badvpn.sh
touch /etc/badres.sh
chmod +x /etc/badvpn.sh
chmod +x /etc/badres.sh

echo "
#!/bin/bash

killall badvpn-udpgw
sleep 5
/bin/bash /etc/badvpn.sh" > /etc/badres.sh

cat > /etc/badvpn.sh << EOF
#!/bin/bash

screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7100 --max-clients 5000 --max-connections-for-client 1000; screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7200 --max-clients 5000 --max-connections-for-client 1000; screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7300 --max-clients 5000 --max-connections-for-client 1000; screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7400 --max-clients 5000 --max-connections-for-client 1000; screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7500 --max-clients 5000 --max-connections-for-client 1000 screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7600 --max-clients 5000 --max-connections-for-client 1000 screen -dmS screen /bin/badvpn-udpgw --listen-addr 127.0.0.1:7700 --max-clients 5000 --max-connections-for-client 1000;;
EOF
	
echo ""
while read -p "$(echo "Escolha o intervalo para Reset do BadVPN [1h-24h]: ")" _jikan ; do
if [[ $_jikan =~ ^[0-9]+$ ]] && (( $_jikan >= 1 && $_jikan <= 24)); then
(crontab -l; echo "00 */$_jikan * * * /etc/badres.sh") | crontab -
(crontab -l; echo "@reboot /etc/badvpn.sh") | awk '!x[$0]++' | crontab -

break
	else
		echo ""
		echo "Apenas Numeros de 1 a 24 zé mané"
	fi
	done
		echo ""
		sleep 1.5
		echo "Instalado!"
rm -rf bad.sh
}

if [[ -e $HOME/badvpn.sh || -e /etc/badvpn.sh ]]; then
  echo ""
  read -p "$(echo "O Script Será Atualizado, Quer Continuar? [s/n]: ")" -e -i s resposta
  [[ $resposta = @(n|N) ]] && rm -rf bad.sh && sleep 0.5 && exit 0
fun_atualiza
source /etc/badvpn.sh
	else
	  echo ""
  read -p "$(echo "O Script Será Instalado, Quer Continuar? [s/n]: ")" -e -i s resposta
  [[ $resposta = @(n|N) ]] && rm -rf bad.sh && sleep 0.5 && exit 0
fun_conf
source /etc/badvpn.sh
fi
