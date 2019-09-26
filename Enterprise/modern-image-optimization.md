---
title: Optimieren von Bilder in modernen SharePoint Online-Websites
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Bilder in modernen SharePoint Online-Websites optimieren.
ms.openlocfilehash: 3884758dfb2f2a81a0a6ac10abcf51932abec666
ms.sourcegitcommit: c7764503422922cb333b05d54e8ebbdb894df2f9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "37028232"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a>Optimieren von Bilder in modernen SharePoint Online-Websites

In diesem Artikel erfahren Sie, wie Sie Bilder in modernen SharePoint Online-Websites optimieren.

Informationen zum Optimieren von Bildern in klassischen Veröffentlichungswebsites finden Sie unter [Bildoptimierung für SharePoint Online](image-optimization-for-sharepoint-online.md).

>[!NOTE]
>Weitere Informationen zur Leistung in modernen SharePoint Online-Portalen finden Sie unter [Leistung in der modernen SharePoint-Umgebung](https://docs.microsoft.com/de-DE/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a>Verwenden des Tools "Seitendiagnose für SharePoint" zum Analysieren der Bildoptimierung

Das **Tool "Seitendiagnose für SharePoint"** ist eine Browsererweiterung für Chrome und [Microsoft Edge ab Version 77](https://www.microsoftedgeinsider.com/en-us/download?form=MI13E8&OCID=MI13E8), mit der Sie Seiten in modernen und klassischen SharePoint-Veröffentlichungswebsites analysieren können. Das Tool stellt für jede analysierte Seite einen Bericht bereit, in dem die Leistung der Seite anhand einer definierten Gruppe von Leistungskriterien dargestellt wird. Wenn Sie das Tool "Seitendiagnose für SharePoint" installieren und mehr darüber erfahren möchten, besuchen Sie [Verwenden des Seitendiagnose-Tools für SharePoint Online](page-diagnostics-for-spo.md).

Wenn Sie eine moderne SharePoint-Website mit dem Tool "Seitendiagnose für SharePoint" analysieren, werden Informationen über große Bilder im Bereich _Diagnosetests_ angezeigt.

Mögliche Ergebnisse sind:

- **Handlungsbedarf** (rot): Die Seite enthält **mindestens ein** Bild mit einer Größe von über 300 KB.
- **Keine Aktion erforderlich** (grün): Die Seite enthält keine Bilder mit einer Größe von über 300 KB.

Wenn das Ergebnis **Große Bilder erkannt** in den Ergebnissen im Abschnitt **Handlungsbedarf** angezeigt wird, können Sie darauf klicken, um weitere Details anzuzeigen.

![Tool für die Seitendiagnose – Ergebnisse](media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a>Beheben von Problemen mit großen Bildern

Wenn eine Seite Bilder mit einer Größe von über 300 KB enthält, wählen Sie das Ergebnis **Große Bilder erkannt** aus, um anzuzeigen, welche Bilder zu groß sind. Auf modernen SharePoint Online-Seiten erfolgt die Wiedergabe von Bildern, und die Bilder werden an die Größe des Browserfensters und die Auflösung des Clientmonitors angepasst. Sie sollten Bilder immer für die Webverwendung optimieren, bevor Sie sie in SharePoint Online hochladen. Sehr große Bilder werden automatisch in Größe und Auflösung reduziert, was zu unerwarteten Ergebnissen bei der Wiedergabe führen kann.

Bevor Sie Seitenrevisionen zur Behebung von Leistungsproblemen durchführen, notieren Sie sich die Ladezeit der Seite in den Analyseergebnissen. Führen Sie das Tool nach Ihrer Revision erneut aus, um zu sehen, ob das neue Ergebnis innerhalb des Grenzwertes liegt, und überprüfen Sie die Ladezeit der neuen Seite, um festzustellen, ob eine Verbesserung vorliegt.

![Ergebnisse der Seitenladezeiten](media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Die Seitenladezeit kann aufgrund einer Vielzahl von Faktoren wie Netzwerklast, Tageszeit und anderen vorübergehenden Schwierigkeiten variieren. Sie sollten die Seitenladezeit einige Male vor und nach der Durchführung von Änderungen testen, um einen Mittelwert zu berechnen.

## <a name="related-topics"></a>Verwandte Themen

[Optimieren der Leistung von SharePoint Online](tune-sharepoint-online-performance.md)

[Optimieren der Leistung von Office 365](tune-office-365-performance.md)

[Leistung in der modernen SharePoint-Oberfläche](https://docs.microsoft.com/de-DE/sharepoint/modern-experience-performance.md)

[Netzwerke für die Inhaltsübermittlung](content-delivery-networks.md)

[Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-office-365-cdn-with-spo.md)