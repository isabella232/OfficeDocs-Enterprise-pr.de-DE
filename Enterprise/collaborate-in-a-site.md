---
title: Zusammenarbeit mit Gästen in einer Website
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
localization_priority: Normal
description: Hier erfahren Sie, wie Sie mit Gästen in einer SharePoint-Website zusammenarbeiten.
ms.openlocfilehash: 23f55e22d4c85dcd168c403f50b35f574be9ac07
ms.sourcegitcommit: 3bba97053caf5f9cff0ef3205afb7869535f38bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2019
ms.locfileid: "36992384"
---
# <a name="collaborate-with-guests-in-a-site"></a>Zusammenarbeit mit Gästen in einer Website

Wenn Sie mit Gästen in Dokumenten, Daten und Listen zusammenarbeiten müssen, können Sie eine SharePoint-Website verwenden. Moderne SharePoint-Websites sind mit Office 365 Gruppen verbunden, die die Website Mitgliedschaft verwalten und zusätzliche Tools für die Zusammenarbeit wie ein freigegebenes Postfach und einen Kalender bereitstellen können.

In diesem Artikel werden die Microsoft 365-Konfigurationsschritte durchlaufen, die erforderlich sind, um eine SharePoint-Website für die Zusammenarbeit mit Gästen einzurichten.

## <a name="azure-organizational-relationships-settings"></a>Azure Organizational Relationships-Einstellungen

Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die Einstellungen für organisatorische Beziehungen in Azure Active Directory gesteuert. Wenn die Gast Freigabe in Azure AD deaktiviert oder eingeschränkt ist, werden alle Freigabeeinstellungen, die Sie in Microsoft 365 konfigurieren, außer Kraft gesetzt.

Überprüfen Sie die Einstellungen für Organisationsbeziehungen, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.

![Screenshot der Azure Active Directory-Seite "Organisationsbeziehungen – Einstellungen"](media/azure-ad-organizational-relationships-settings.png)

So legen Sie Einstellungen für die Organisationsbeziehung fest

1. Melden Sie sich bei Microsoft Azure [https://portal.azure.com](https://portal.azure.com)an an.
2. Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.
3. Klicken Sie im Bereich **Übersicht** auf **Organisationsbeziehungen**.
4. Klicken Sie im Bereich **Organisationsbeziehungen** auf **Einstellungen**.
5. Stellen Sie sicher, dass **Administratoren und Benutzer in der Rolle "Gast einladender" eingeladen** werden und **Mitglieder einladen können** , beide auf " **Ja**" festgelegt sind.
6. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

Beachten Sie die Einstellungen im Abschnitt Einschränkungen für die **Zusammenarbeit** . Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert werden.

## <a name="office-365-groups-guest-settings"></a>Gast Einstellungen für Office 365 Gruppen

Moderne SharePoint-Websites verwenden Office 365 Gruppen, um den Website Zugriff zu steuern. Die Gast Einstellungen für Office 365 Gruppen müssen aktiviert sein, damit der Gastzugriff auf SharePoint-Websites funktioniert.

![Screenshot von Office 365-Gruppen-Gast Einstellungen im Microsoft 365 Admin Center](media/office-365-groups-guest-settings.png)

So legen Sie die Gast Einstellungen für Office 365 Gruppen fest

1. Erweitern Sie im Microsoft 365 Admin Center in der linken Navigationsleiste **Einstellungen**.
2. Klicken Sie auf **Dienste #a0-Add-ins**.
3. Klicken Sie in der Liste auf **Office 365 Gruppen**.
4. Stellen Sie sicher, dass die Gruppen **Mitglieder außerhalb Ihrer Organisation Zugriff auf Gruppeninhalte** haben und Gruppen **Besitzer Personen außerhalb Ihrer Organisation hinzufügen zulassen** Kontrollkästchen aktiviert sind.
5. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Änderungen speichern**.


## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint-Freigabeeinstellungen auf Organisationsebene

Damit Gästezugriff auf SharePoint-Websites haben, müssen die SharePoint-Freigabeeinstellungen auf Organisationsebene für die Freigabe für Gäste zulässig sein.

Die Einstellungen auf Organisationsebene bestimmen, welche Einstellungen für einzelne Websites verfügbar sind. Websiteeinstellungen dürfen nicht so restriktiv wie die Einstellungen auf Organisationsebene sein.

Wenn Sie die Datei-und Ordnerfreigabe für anonyme Benutzer zulassen möchten, wählen Sie **jeden**aus. Wenn Sie sicherstellen möchten, dass sich alle Gäste authentifizieren müssen, wählen Sie **neue und vorhandene Gäste**aus. Wählen Sie die frei zügigste Einstellung aus, die von einer beliebigen Website in Ihrer Organisation benötigt wird.

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](media/sharepoint-organization-external-sharing-controls.png)


So legen Sie Freigabeeinstellungen für SharePoint-Organisationsebene fest

1. Klicken Sie im Microsoft 365 Admin Center in der linken Navigationsleiste unter **Admin Centers**auf **SharePoint**.
2. Klicken Sie im SharePoint Admin Center im linken Navigationsbereich auf **Freigabe**.
3. Stellen Sie sicher, dass die externe Freigabe für SharePoint auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.
4. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Standard Link Einstellungen für SharePoint-Organisationsebene

Die Standardeinstellungen für Datei-und Ordnerverknüpfung legen fest, welche Link Option dem Benutzer standardmäßig angezeigt wird, wenn er eine Datei oder einen Ordner freigegeben hat. Benutzer können den Verknüpfungstyp vor der Freigabe bei Bedarf in eine der anderen Optionen ändern.

Beachten Sie, dass sich diese Einstellung auf alle Teams und SharePoint-Websites in Ihrer Organisation auswirkt.

Wählen Sie den Linktyp aus, der standardmäßig ausgewählt ist, wenn Benutzer Dateien und Ordner freigeben:

- **Jeder, der über den Link verfügt** – wählen Sie diese Option aus, wenn Sie eine Vielzahl von Dateien und Ordnern für anonyme Benutzer freigeben möchten. Wenn Sie *jeder* Verknüpfung erlauben möchten, aber über die versehentliche anonyme Freigabe besorgt sind, sollten Sie eine der anderen Optionen als Standard verwenden. Dieser Linktyp ist nur verfügbar, wenn Sie die Freigabe von **Benutzern** aktiviert haben.
- **Nur Personen in Ihrer Organisation** – wählen Sie diese Option aus, wenn Sie davon ausgehen, dass die meisten Datei-und Ordner Freigaben für Personen in Ihrer Organisation gelten.
- **Bestimmte Personen** – diese Option wird empfohlen, wenn Sie eine Vielzahl von Datei-und Ordner Freigaben für Gäste erwarten. Diese Art von Link funktioniert mit Gästen und erfordert die Authentifizierung.
 
![Screenshot der SharePoint-Freigabeeinstellungen für Dateien und Ordner auf Organisationsebene](media/sharepoint-organization-files-folders-sharing-settings.png)


So legen Sie die Standard Link Einstellungen für die SharePoint-Organisationsebene fest

1. Navigieren Sie im SharePoint Admin Center zur Seite Freigabe.
2. Wählen Sie unter **Datei-und Ordner Links**den standardmäßigen Freigabe Link aus, den Sie verwenden möchten.
3. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="create-a-site"></a>Erstellen einer Website

Im nächsten Schritt erstellen Sie die Website, die Sie für die Zusammenarbeit mit Gästen verwenden möchten.

So erstellen Sie eine Website
1. Klicken Sie im SharePoint Admin Center unter **Websites**auf **aktive Standorte**.
2. Klicken Sie auf **Erstellen**.
3. Klicken Sie auf **Team Website**.
4. Geben Sie einen Websitenamen ein, und geben Sie einen Namen für den Gruppenbesitzer (Websitebesitzer) ein.
5. Wählen Sie unter **Erweiterte Einstellungen**aus, ob es sich um eine öffentliche oder private Website handeln soll.
6. Klicken Sie auf **Weiter**.
7. Klicken Sie auf **Fertig stellen**.

Wir laden Benutzer später ein. Als nächstes ist es wichtig, die Freigabeeinstellungen auf Standortebene für diese Website zu überprüfen.

## <a name="sharepoint-site-level-sharing-settings"></a>Freigabeeinstellungen für SharePoint-Websiteebene

Überprüfen Sie die Freigabeeinstellungen auf Standortebene, um sicherzustellen, dass die gewünschten Zugriffstypen für diese Website zulässig sind. Wenn Sie beispielsweise die Einstellungen auf Organisationsebene auf " **jeder**" festlegen, aber alle Gäste für diese Website authentifizieren möchten, stellen Sie sicher, dass die Freigabeeinstellungen auf Standortebene auf " **neu" und "vorhandene Gäste**" festgelegt sind.

Beachten Sie, dass die Website nicht für anonyme Benutzer (**jede** Einstellung) freigegeben werden kann, aber einzelne Dateien und Ordner können.

![Screenshot der externen Freigabeeinstellungen für SharePoint-Websites](media/sharepoint-site-external-sharing-settings.png)

So legen Sie Freigabeeinstellungen auf Websiteebene fest
1. Erweitern Sie im SharePoint Admin Center in der linken Navigationsleiste den Knoten **Websites** , und klicken Sie dann auf **aktive Standorte**.
2. Wählen Sie die Website aus, die Sie soeben erstellt haben.
3. Klicken Sie im Menüband auf **Freigabe**.
4. Stellen Sie sicher, dass die Freigabe auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.
5. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="invite-users"></a>Benutzer einladen

Die Einstellungen für die Gast Freigabe sind nun konfiguriert, sodass Sie mit dem Hinzufügen interner Benutzer und Gäste zu Ihrer Website beginnen können. Der Website Zugriff wird über die zugehörige Office 365 Gruppe gesteuert, sodass Benutzer dort hinzugefügt werden.

So laden Sie interne Benutzer zu einer Gruppe ein
1. Navigieren Sie zu der Website, auf der Sie Benutzer hinzufügen möchten.
2. Klicken Sie oben rechts auf **Mitglieder** .
3. Klicken Sie auf **Mitglieder hinzufügen**.
4. Geben Sie die Namen oder e-Mail-Adressen der Benutzer ein, die Sie zur Website einladen möchten, und klicken Sie dann auf **Speichern**.

Gastbenutzer können nicht von der Website hinzugefügt werden. Sie müssen Sie mit Outlook im Internet hinzufügen.

So laden Sie Gäste zu einer Website ein
1. Klicken Sie in Outlook im Internet unter **Gruppen**auf die Gruppe, der Sie Mitglieder hinzufügen möchten.
2. Öffnen Sie die Gruppen Visitenkarte, und klicken Sie dann unter **Weitere Optionen** (...) auf **Mitglieder hinzufügen**.
3. Geben Sie die e-Mail-Adressen der Gäste ein, die Sie einladen möchten, und klicken Sie dann auf **Hinzufügen**.
4. Klicken Sie auf **Schließen**.

## <a name="see-also"></a>Siehe auch