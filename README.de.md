# Ansible Rolle: Systemweite Zeitzone setzen

Eine einfache, leicht integrierbare Ansible-Rolle, um die systemweite **Zeitzone** auf Linux-Servern wie Red Hat Enterprise Linux, AlmaLinux, Rocky Linux, Debian, Ubuntu, openSUSE, Arch Linux und vielen weiteren Linux-Distributionen festzulegen.

🇩🇪 **Hinweis:** Diese Rolle wurde mit viel ❤️ in Deutschland erstellt.

---

## Hauptfunktionen

- Schnelle Konfiguration der Systemzeitzone.
- Einfache Integration in Foreman/Katello (Importvorlage als Job-Vorlage liegt bei).
- Unterstützt alle gängigen Linux-Distributionen.

---

## Anforderungen

- Ansible Version 2.14 oder neuer
- Unterstützte Betriebssysteme:
  - Red Hat Enterprise Linux 7, 8, 9
  - AlmaLinux 8, 9
  - Rocky Linux 8, 9
  - Debian (buster, bullseye, bookworm)
  - Ubuntu (focal, jammy, lunar, noble)
  - openSUSE Leap 15.x
  - Arch Linux

---

## Rollen-Variablen

| Parameter                 | Erforderlich | Benutzereingabe | Standardwert     | Beschreibung                                               |
|---------------------------|--------------|-----------------|------------------|------------------------------------------------------------|
| `n_selected_timezone`     | Nein         | Ja              | `Europe/Berlin`  | Die Zeitzone, die auf dem System eingestellt werden soll (z.B. `Europe/Berlin`, `America/Chicago`). |

---

## Beispielhafte Verwendung

So nutzt du diese Rolle in einem Ansible-Playbook:

```yaml
---
- hosts: all
  become: true
  roles:
    - role: ansible-role-linux_timezone
      n_selected_timezone: "{{ general_timezone }}"
```

---

## Foreman/Katello Integration

Für die einfache Integration und Ausführung der Rolle über Foreman/Katello liegt eine ERB-Datei bei:

```
files/ansible-role-linux_timezone.erb
```

Diese kannst du wie folgt in dein Foreman-Backend importieren:

```
Hosts → Vorlagen → Job-Vorlagen
```

---

## Lizenz

Dieses Projekt steht unter der **MIT Lizenz** – weitere Details findest du in der [LICENSE](LICENSE) Datei.

---

## Autor

Pierre by NAWKO

