---

copyright:

  years:  2016, 2018

lastupdated: "2018-09-21"

---

# Hybridity Bundle aus einer vCenter Server-Instanz entfernen

Zum Entfernen der Hybridity Bundle-Lizenz aus Ihrer vCenter Server-Instanz müssen Sie die Schlüssel der VMware NSX- und VMware vSAN-Mietlizenzen in VMware vSphere Web Client durch Schlüssel eigener Lizenzen (BYOL – Bring Your Own License) ersetzen. Darüber hinaus müssen Sie ein Support-Ticket öffnen, um die Gebühren für die Mietlizenzen zu stornieren.

**Wichtig:** Wenn Sie für Ihre Lizenz ein Downgrade durchführen, kann dies zum Fehlschlagen Ihrer vCenter Server-Instanz führen. Sie können auswählen, auf eigenes Risiko ein Downgrade für Ihre Lizenz durchzuführen; betrachten Sie jedoch zunächst die Funktionen, die nach einem Downgrade nicht verfügbar sein werden. Weitere Informationen finden Sie im [Vergleichsdiagramm für VMware-Komponenteneditionen](../archiref/solution/appendix.html).

## Vor dem Entfernen von Hybridity Bundle

Überprüfen Sie folgende Voraussetzungen, bevor Sie Hybridity Bundle entfernen:

* Sie verfügen über eine vCenter Server-Instanz mit Version 2.4 oder höher, in der Hybridity Bundle aktiviert ist.
* In Ihrer vCenter Server-Instanz ist nicht der Service "VMware HCX on {{site.data.keyword.cloud_notm}}" installiert.
* Sie haben als Administrator Zugriff auf VMware vSphere Web Client.
* Falls noch nicht angewendet, verfügen Sie über BYOL-Schlüssel, die für das VMware NSX-Cluster und jedes VMware vSAN-Cluster verfügbar sind.
* Optional und falls noch nicht angewendet, verfügen Sie über BYOL-Schlüssel, die für die Anwendung auf die Lizenzen von VMware vCenter Server und VMware vSphere Enterprise Plus verfügbar sind.

## Vorgehensweise zum Entfernen von Hybridity Bundle

1. Melden Sie sich bei VMware vSphere Web Client als **Administrator** an.
2. Klicken Sie auf die Optionen für **Home > Administration > Lizenzierung > Lizenzen**.
3. Klicken Sie auf die Registerkarte für **Assets**.
4. Führen Sie folgende Schritte aus, um für VMware NSX eine eigene Lizenz (BYOL) zu installieren:
   1. Klicken Sie auf die Registerkarte **Lösungen**.
   2. Wählen Sie "NSX for vSphere" aus und klicken Sie auf die Optionen für **Alle Aktionen > Lizenz zuordnen**.
   3. Klicken Sie auf das Symbol für **Hinzufügen** und geben Sie den Lizenzschlüssel ein. Klicken Sie auf **Weiter**.
   4. Geben Sie den Namen für die Lizenz ein und klicken Sie auf **Weiter**. Klicken Sie auf **Fertigstellen**, um die Lizenz hinzuzufügen.
   5. Wählen Sie den neuen Lizenzschlüssel aus.
   6. Notieren Sie sich die vollständigen Lizenzschlüssel für sowohl die angewendete Lizenz als auch die ersetzte Lizenz. **Wichtig:** Halten Sie die Lizenzdetails für eine spätere Verwendung in diesem Verfahren bereit.
   7. Klicken Sie auf **OK**, damit die Lizenz zugeordnet wird.
5. Führen Sie folgende Schritte aus, um für VMware vSAN eine eigene Lizenz (BYOL) zu installieren:
   1. Klicken Sie auf die Registerkarte **Cluster**.
   2. Führen Sie folgende Schritte für jeden vSAN-Cluster aus, der Ihrer vCenter Server-Instanz zugeordnet ist:
    1. Wählen Sie ein vSAN-Cluster aus und klicken Sie auf die Optionen für **Alle Aktionen > Lizenz zuordnen**.
    2. Klicken Sie auf das Symbol für **Hinzufügen** und geben Sie den Lizenzschlüssel ein. Klicken Sie auf **Weiter**.
    3. Geben Sie den Namen für die Lizenz ein und klicken Sie auf **Weiter**. Klicken Sie auf **Fertigstellen**, um die Lizenz hinzuzufügen.
    4. Wählen Sie den neuen Lizenzschlüssel aus.
    5. Notieren Sie sich den Clusternamen und die Volllizenzschlüssel sowohl der angewendeten als auch der ersetzten Lizenz. **Wichtig:** Halten Sie die Lizenzdetails für eine spätere Verwendung in diesem Verfahren bereit.
    6. Klicken Sie auf **OK**, damit die Lizenz zugeordnet wird.
6. Führen Sie optional folgende Schritte aus, um für VMware vCenter Server eine eigene Lizenz (BYOL) zu installieren:
   1. Klicken Sie auf die Registerkarte für **vCenter Server-Systeme**.
   2. Wählen Sie "vCenter Server" aus und klicken Sie auf die Optionen für **Alle Aktionen > Lizenz zuordnen**.
   3. Klicken Sie auf das Symbol für **Hinzufügen** und geben Sie den Lizenzschlüssel ein. Klicken Sie auf **Weiter**.
   4. Geben Sie den Namen für die Lizenz ein und klicken Sie auf **Weiter**. Klicken Sie auf **Fertigstellen**, um die Lizenz hinzuzufügen.
   5. Wählen Sie den neuen Lizenzschlüssel aus.
   6. Notieren Sie sich die Volllizenzschlüssel sowohl der angewendeten als auch der ersetzten Lizenz.**Wichtig:** Halten Sie die Lizenzdetails für eine spätere Verwendung in diesem Verfahren bereit.
   7. Klicken Sie auf **OK**, damit die Lizenz zugeordnet wird.
7. Führen Sie optional folgende Schritte aus, um für VMware vSphere Enterprise Plus eine eigene Lizenz (BYOL) zu installieren:
  1. Klicken Sie auf die Registerkarte für **Hosts**.
  2. Führen Sie folgende Schritte für jeden Cluster aus, der Ihrer vCenter Server-Instanz zugeordnet ist, oder führen Sie folgende Schritte gleichzeitig für alle Cluster aus, wenn dieselbe Lizenz auf alle Cluster angewendet wird, die Ihrem vCenter-Server zugeordnet sind:
    1. Wählen Sie alle Ihrem Cluster zugeordneten Hosts aus und klicken Sie auf die Optionen für **Alle Aktionen > Lizenz zuordnen**.
    2. Klicken Sie auf das Symbol für **Hinzufügen** und geben Sie den Lizenzschlüssel ein. Klicken Sie auf **Weiter**.
    3. Geben Sie den Namen für die Lizenz ein und klicken Sie auf **Weiter**. Klicken Sie auf **Fertigstellen**, um die Lizenz hinzuzufügen.
    4. Wählen Sie den neuen Lizenzschlüssel aus.
    5. Notieren Sie sich den Clusternamen und die Volllizenzschlüssel sowohl der angewendeten als auch der ersetzten Lizenz. **Wichtig:** Halten Sie die Lizenzdetails für eine spätere Verwendung in diesem Verfahren bereit. Schreiben Sie die den einzelnen Lizenzschlüsseln zugeordneten Clusternamen auf, falls die Lizenzschlüssel nicht für alle Cluster gleich sind.
    6. Klicken Sie auf **OK**, damit die Lizenz zugeordnet wird.
8. Entfernen Sie die Mietlizenzen.
   1. Klicken Sie auf die Registerkarte **Lizenzen**.
   2. Wählen Sie die Lizenzen aus, die Sie in den Schritten 4 bis 7 ersetzt haben.
   3. Klicken Sie auf das Symbol **Lizenzen entfernen**.
9. Öffnen Sie ein Support-Ticket und geben Sie folgende Informationen an, um die Gebühren für die Mietlizenzen zu stornieren:
  * Der Name Ihrer vCenter Server-Instanz.
  * Die Ihrer vCenter Server-Instanz zugeordnete ID.
  * Eine Liste der BYOL-Lizenzschlüssel, die Sie in diesem Verfahren installiert haben. Geben Sie, soweit zutreffend, den Clusternamen mit den Lizenzschlüsseln für das vSphere-Cluster und die vSAN-Cluster an.
  * Eine Liste der Mietlizenzschlüssel, die Sie in diesem Verfahren entfernt haben. Geben Sie, soweit zutreffend, den Clusternamen mit den Lizenzschlüsseln für vSphere-Cluster und vSAN-Cluster an.

  **Anmerkung:** Die IBM Support- und Operationsteams greifen auf die vCenter-Managementschicht Ihres Kontos der {{site.data.keyword.cloud_notm}}-Infrastruktur (SoftLayer) zu, um zu prüfen, dass die Mietlizenzen entfernt wurden, bevor die Gebühren für die Hybridity Bundle-Mietlizenz storniert werden.

### Zugehörige Links

* [vCenter Server with Hybridity Bundle-Instanzen bestellen](vc_hybrid_orderinginstance.html)
* [vCenter Server with Hybridity Bundle-Instanzen anzeigen](vc_hybrid_viewinginstances.html)
* [Kontaktaufnahme mit dem IBM Support](../vmonic/trbl_support.html)