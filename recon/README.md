Comando: 

`nmap` + **Parametros**

##Parametros:

`-n` Para ahorrar tiempo, no realizar la resolucion de nombre/DNS de la ip especificada

- Hosts
  
  `192.168.0.1` o `192.168.0.1/24`  (host especifico [o con CDIR])
  
  `192.168.0.1 192.168.0.2`  (multiples hosts especificos)
  
  `google.com`   (dominio  especifico)
  
  `-iL hosts.csv`  (dominios/IP  desde un archivo)
  
  `--exclude 192.168.0.10`  (excluir un host del escaneo)

- Ports

  `-p-` Escanear los 65535 puertos
  
  `-F` Escanear los 100 puertos mas comunes (**-F = [F]requent**)
  
  `-sT` Escanear usando una conexión TCP (**-[sT] = [s]can[T]CP**)
  
  `-sU` Escanear usando una conexión TCP (**-[sU] = [s]can[U]DP**)
  
  `-Pn`  (**Pn**) sin escaneo de ping, escanea host ignorando si responde o no los pings
  
- Sistema Operativo

  `-o` Escanear el sistena operativo

  `--osscan-limit` detección del sistema operativo si se encuentra al menos un puerto TCP abierto y uno cerrado


- Servicios

  `-sV` Escanear version del servicio (**-sV = [s]ervice[V]ersion**)
  
  `-sV --version-Intensity 9` Agregar 0-9 agresividad para aumentar precision de version del servicio
  

- Exportar informe
  
  `-oA` A todos los formatos (**-oA = [o]utput[A]ll**)

  `-oN` Exportar a *.file

- Informacion
  
  `-vvv` Triple Verbose especifica  la info  extraida y la hace muy  detallada del proceso
  
- Scripts
  
  `-sC` Ejecutar scripts predeterminados
  
  `--script=smb*` especificar conjunto de scripts de smb,  `*` ejecuta todos los que cominenzan por smb
  
  `--script=http-shellshock` especificar script especifico

- parametros para Webs
  
  `--script=http-enum` Escanear web en  rutas  conocidas
  
  `--script=http-headers` Escanear para obtener headers HTTP de respuesta de la web
  
  `--script=asn-query,whois,ipgeolocation-maxmind` Maximos datos sobre la IP

  
Conjunto de parametros utiles:

`nmap -sC -sV -O -T4 -n -Pn -p- -vvv  -oN datos <ip>`

Conjunto de parametros para escaneo agresivo:

`nmap -n -sS -p- -T4 -Pn -A -vvv -oN datos <ip>`

Conjuno de parametros para generar sitemap

`nmap -Pn --script=http-sitemap-generator <URL>`

Fuerza bruta para obtener  Subdominios

`nmap -Pn --script=dns-brute`

Escaneo seguro contra servicio SMB (Samba)

`nmap -n -Pn -vv -O -sV --script smb-enum,smb-ls,smb-mbenum,smb-os-discovery,smb-s,smb-vuln,smbv2 -vv <ip>`

Detectar XSS Cross Site Scripting en URLS

Primero: `nmap --script=http-enum -oN datos.txt `

Segundo: `nmap -p80  --script http-unsafe-output-escaping -iL datos.txt`




  
  
  
  
  
  
  


  

