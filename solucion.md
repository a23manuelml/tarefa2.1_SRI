## Tarefa 2.1 - Servidores DHCP Windows
![enunciado](imaxes/enunciado.png)

Os equipos ned, rob serán os servidores dns para o dominio stark.lan (Debian) e twin para lanister.lan (Windows)

Instala no equipo tyrion (Windows) o rol de servidor DHCP coa seguinte configuración: (deberás ter apagados os servidores DHCP do punto anterior)

1. Un ámbito para os equipos da rede privada lanister, con un intervalo de exclusión.

2. Deberás crear unha reserva estática que estará no rango de enderezos do seu ámbito correspondente.

3. Establece os nomes de dominio e servidores DNS primario de cada zona.

4. Deberás actualizar a zona primaria no servidor DNS tywin.

5. Engade outro ámbito para a rede primaria stark (necesitas outra interface de rede) que actualice a zona prinaria DNS definida no equipo arya.

6. Instala no equipo jaime un servizo DHCP failover para a subrede lanister.

7. Necesitarás polo menos tres clientes (Cercei,Joffrey, Myrcella) para a rede lannister e un para a  rede stark (jon).
Inclúe capturas de:
    - Configuración dos ambitos e rangos de enderezos

    - Configuración de opcións

    - Configuración da actualización

    - Vídeo no que o cliente renova a concesión, e se ve  a zona DNS unha vez que o DHCP actualiza o DNS. Tamén o cliente debe ser capaz de resolver o seu propio nome (non FQDN).

    - Clientes das dúas subredes, amosando DNS, router e enderezo IP.

    - Configuración dos servidores failover

    - Capturas dos clientes obtendo enderezos cos dous servidores failover encendidos, e con un acendido e outro apagado (de forma alterna)

**SOLUCION:**

- Configuración de DNS en Servidores Debian (Ned y Rob) para stark.lan (os pasos débense facer en Ned y Rob, ainda que só o mostro como se fai nun, xa que no outro será identico)

    - Instalamos Bind9

        ![imaxe1](imaxes/solapt1.1.png)
    
    - Configuramos a zona DNS

        ![imaxe2](imaxes/solapt1.2.png)

    - Creamos o arquivo de zona

        ![imaxe3](imaxes/solapt1.3.png)

- Configuración de DNS en Windows Server (Tywin) para lannister.lan

    - Instalamos servidor DNS en Tywin

        ![imaxe4](imaxes/solapt2.1.png)
    
    - Creamos a zona de búsqueda directa lannister.lan permitindo actualizacións dinámicas

        ![imaxe5](imaxes/solapt2.2.png)

- Configuración de DHCP en tyron para ambas subredes

    - Configuramos un ámbito para lannister.lan

        ![imaxe6](imaxes/solapt2.3.png)

    - Configuramos un ámbito para stark.lan

        ![imaxe7](imaxes/solapt2.4.png)
    
- Configuración de Failover DHCP en Jaime para lannister.lan

    - Configuramos Failover DHCP con Tyrion

        ![imaxe8](imaxes/solapt3.1.png)