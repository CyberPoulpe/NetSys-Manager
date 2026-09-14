# 🐙 CephaloShell

> **CephaloShell** est un outil CLI interactif et modulaire en PowerShell conçu pour simplifier l'administration système, le diagnostic réseau et la gestion quotidienne d'un domaine Active Directory (AD).

---

## 📸 Aperçu

CephaloShell repose sur un menu interactif dynamique habillé d'une mascotte poulpe en ASCII Art. Il permet d'exécuter rapidement des tâches d'administration locales et distantes sans avoir à ressaisir manuellement de longues commandes PowerShell.

```text
⠀⠀⠀⠀⠀⠀⢀⣀⣠⣀⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⣠⣾⣿⣿⣿⣿⣿⣿⣷⣦⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⢠⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⡀⠀⠀⠀⣠⣶⣾⣷⣶⣄⠀⠀⠀⠀⠀
⠀⠀⠀⢸⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣧⠀⠀⢰⣿⠟⠉⠻⣿⣿⣷⠀⠀⠀⠀
⠀⠀⠀⠈⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠿⢷⣄⠘⠿⠀⠀⠀⢸⣿⣿⡆⠀⠀⠀
⠀⠀⠀⠀⠈⠿⣿⣿⣿⣿⣿⣀⣸⣿⣷⣤⣴⠟⠀⠀⠀⠀⢀⣼⣿⣿⠁⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠈⠙⣛⣿⣿⣿⣿⣿⣿⣿⣿⣦⣀⣀⣀⣴⣾⣿⣿⡟⠀⠀⠀⠀
⠀⠀⠀⢀⣠⣴⣾⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡿⠟⠋⣠⣤⣀⠀⠀
⠀⠀⣴⣿⣿⣿⠿⠟⠛⠛⢛⣿⣿⣿⣿⣿⣿⣧⡈⠉⠁⠀⠀⠀⠈⠉⢻⣿⣧⠀
⠀⣼⣿⣿⠋⠀⠀⠀⠀⢠⣾⣿⣿⠟⠉⠻⣿⣿⣿⣦⣄⠀⠀⠀⠀⠀⣸⣿⣿⠃
⠀⣿⣿⡇⠀⠀⠀⠀⠀⣿⣿⡿⠃⠀⠀⠀⠈⠛⢿⣿⣿⣿⣿⣶⣿⣿⣿⡿⠋⠀
⠀⢿⣿⣧⡀⠀⣶⣄⠘⣿⣿⡇⠀⠀⠀⣸⣿⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠈⠻⣿⣿⣿⣿⠏⠀⢻⣿⣿⣄⠀⠀⠀⣸⣿⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠻⣿⣿⣿⣶⣾⣿⣿⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠛⠛⠛⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
```

---

## ✨ Fonctionnalités Principales

### 🌐 Diagnostics & Administration Réseau
* **Connexion / Exécution distante SSH :** Exécution de commandes à distance via `Invoke-Command`.
* **Configuration IP & Diagnostics :** Affichage d'IPConfig, `ping`, `nslookup`, `tracert`.
* **Scan Réseau rapide :** Balayage d'une plage d'adresses IP (`/24`) pour identifier les hôtes actifs.
* **Diagnostic Réseau Rapide :** Test automatique de connectivité Internet (Ping DNS public 8.8.8.8, Google, résolution DNS).
* **Wake-on-LAN (WoL) :** Envoi de paquets magiques (*Magic Packet*) sur le port UDP 4000 pour démarrer un poste à distance via son adresse MAC.

### 🛡️ Gestion Active Directory (Sous-menus complets)
* **Gestion des Utilisateurs :**
  * Recherche par nom de famille (avec sélection interactive en cas de doublons).
  * Consultations des informations détaillées et groupes d'appartenance.
  * Ajout / Suppressions de groupes AD.
  * Déplacement d'unité d'organisation (OU).
  * Réinitialisation de mot de passe (avec forçage de changement à la prochaine session).
  * Activation / Désactivation de compte.
* **Gestion des Groupes :**
  * Affichage des membres du groupe.
  * Ajout / Suppression d'utilisateurs ou d'ordinateurs dans un groupe.
  * Déplacement du groupe dans une OU.
  * Export de la liste des membres au format CSV (`<NomGroupe>-members.csv`).
* **Gestion des Ordinateurs :**
  * Inspection des détails du poste et test Ping direct.
  * Déplacement dans l'AD et gestion des groupes associés.
  * Consultation du mot de passe Administrateur Local via **LAPS** (`Get-AdmPwdPassword`).
  * Force la mise à jour des GPO à distance (`Invoke-GPUpdate`).
  * Ouverture d'une session de commande distante.
* **Statut de Réplication AD :** Exécution directe de `repadmin /replsum`.

### 🔄 Maintenance WSUS & GPO
* **Réinitialisation WSUS (Local et Distant) :**
  * Arrêt du service Windows Update (`wuauserv`).
  * Nettoyage du dossier `C:\Windows\SoftwareDistribution`.
  * Suppression de la clé de registre `SusClientId`.
  * Redémarrage des services et re-détection immédiate (`wuauclt /resetauthorization /detectnow /reportnow`).
  * Export automatique des logs Windows Update (`Get-WindowsUpdateLog`) et mise à jour GPO.
* **GPUpdate /force :** Déclenchement à distance sur la machine ciblée.

---

## 🚀 Prérequis & Installation

### Prérequis
* **Système d'exploitation :** Windows 10 / 11 ou Windows Server.
* **Environnement :** PowerShell 5.1 ou PowerShell 7+.
* **Modules PowerShell requis :**
  * RSAT / Module Active Directory (`ActiveDirectory`).
  * Support LAPS (Optionnel, pour la fonction de lecture du mot de passe admin local).
* **Privilèges :** Exécution en tant qu'**Administrateur** recommandée (nécessaire pour la gestion AD, l'exécution distante `Invoke-Command` et l'arrêt des services local/distant).

### Exécution

1. Clônez le dépôt ou téléchargez le fichier de script :
   ```powershell
   git clone https://github.com/CyberPoulpe/CephaloShell.git
   cd CephaloShell
   ```

2. Débloquez le fichier script si nécessaire :
   ```powershell
   Unblock-File -Path .\CephaloShell.ps1
   ```

3. Lancez le script dans une console PowerShell exécutée en tant qu'administrateur :
   ```powershell
   .\CephaloShell.ps1
   ```

---

## 📖 Utilisation

1. **Menu Principal :** Saisissez le numéro correspondant à la fonctionnalité souhaitée.
2. **Navigation :** Pour retourner au menu précédent ou quitter le script, entrez la touche `q`.
3. **Recherche AD :** Saisissez simplement le nom de l'utilisateur ou du groupe. Si plusieurs correspondances sont trouvées, un sous-menu numéroté vous permettra de sélectionner la bonne cible.

---

## 📄 Licence

Ce projet est sous licence MIT. Consulter le fichier `LICENSE` pour plus de détails.
