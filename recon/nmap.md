Comando: 

`nmap` + **Parametros

Parametros:

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


  

