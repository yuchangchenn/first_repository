# Fitxa tècnica: Instal·lació de servidor Web Nginx

## Objectiu
Desplegar i verificar el funcionament d'un servidor web Nginx en un entorn GNU/Linux per servir pàgines web estàtiques.

## Materials
* Màquina virtual amb Ubuntu Server / Desktop.
* Connexió a Internet.
* Terminal de comandes amb permissos de `sudo`.
* Editor Visual Studio Code.

## Procediment
1. Pas inicial: Actualitzar l'índex de paquets del sistema operatiu amb `sudo apt update`.
2. Segon pas: Instal·lar el paquet principal de Nginx executant `sudo apt install nginx -y`.
3. Tercer pas: Iniciar el servei i configurar-lo per a l'arrencada automàtica amb `sudo systemctl enable --now nginx`.
4. Quart pas: Ajustar les regles del tallafocs per permetre el tràfic HTTP.

## Comprovacions
- [ ] El servei `nginx` està en estat actiu (`active (running)`).
- [ ] La pàgina per defecte carrega bé des del navegador a `http://localhost`.
- [ ] El port 80 està en escolta correctament.

## Incidències i solucions
| Incidència | Solució |
|---         |---      |
| El port 80 ja està en ús per un altre servei | Aturar el servei conflictiu amb `sudo systemctl stop apache2` o canviar el port a `/etc/nginx/sites-available/default` |
| Error `Permission denied` en editar la configuració | Executar l'editor amb privilegis elevats utilitzant la comanda `sudo` |

## Comandes principals
Per verificar l'estat del servei en quableser moment, executa la comanda següent al terminal:

```bash
sudo systemctl status nginx