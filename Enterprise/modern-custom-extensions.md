---
title: Optimieren benutzerdefinierter Erweiterungen in modernen SharePoint Online-Webseiten
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Erfahren Sie, wie Sie die Leistung benutzerdefinierter Erweiterungen in modernen SharePoint Online-Webseiten optimieren können.
ms.openlocfilehash: bdc05c4e786d07a18c49766bf37aca7f4fde56da
ms.sourcegitcommit: c024b48115cebfdaadfbc724acc2d065394156e9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42603819"
---
# <a name="optimize-custom-extension-performance-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="69aac-103">Optimieren der Leistung benutzerdefinierter Erweiterungen in modernen SharePoint Online-Webseiten</span><span class="sxs-lookup"><span data-stu-id="69aac-103">Optimize custom extension performance in SharePoint Online modern site pages</span></span>

<span data-ttu-id="69aac-104">In diesem Artikel erfahren Sie, wie Sie die Auswirkungen benutzerdefinierter Erweiterungen auf die vom Benutzer empfundene Latenz bestimmen und häufig auftretende Probleme beheben können.</span><span class="sxs-lookup"><span data-stu-id="69aac-104">This article will help you understand how to determine how custom extensions affect user perceived latency, and how to remediate common issues.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-custom-extensions"></a><span data-ttu-id="69aac-105">Verwenden Sie das Tool „Seitendiagnose für SharePoint“, um benutzerdefinierte Erweiterungen zu analysieren</span><span class="sxs-lookup"><span data-stu-id="69aac-105">Use the Page Diagnostics for SharePoint tool to analyze custom extensions</span></span>

<span data-ttu-id="69aac-106">Das Tool "Seitendiagnose für SharePoint" ist eine Browsererweiterung für den neuen Microsoft Edge (https://www.microsoft.com/edge) und Chrome, mit denen Sie SharePoint Online-Seiten sowohl in modernen Portal- als auch in klassischen Veröffentlichungs-Websites analysieren können.</span><span class="sxs-lookup"><span data-stu-id="69aac-106">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="69aac-107">Das Tool stellt für jede analysierte Seite einen Bericht bereit, in dem die Leistung der Seite anhand einer definierten Gruppe von Leistungskriterien dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="69aac-107">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="69aac-108">Wenn Sie das Tool "Seitendiagnose für SharePoint" installieren und mehr darüber erfahren möchten, besuchen Sie [Verwenden des Seitendiagnose-Tools für SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="69aac-108">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="69aac-109">Das Seitendiagnose-Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint-Systemseite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69aac-109">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="69aac-110">Wenn Sie eine Seite einer SharePoint-Website mit dem Tool "Seitendiagnose für SharePoint" analysieren, werden im Ergebnis **Erweiterungen, die sich auf die Ladezeit auswirken** im Bereich _Diagnosetests_ Informationen über benutzerdefinierte Erweiterungen angezeigt, die die Baselinemetrik überschreiten.</span><span class="sxs-lookup"><span data-stu-id="69aac-110">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about custom extensions that exceed the baseline metric in the **Extensions are impacting load time** result in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="69aac-111">Mögliche Ergebnisse sind:</span><span class="sxs-lookup"><span data-stu-id="69aac-111">Possible results include:</span></span>

- <span data-ttu-id="69aac-112">**Handlungsbedarf** (rot): eine _benutzerdefinierte_ Erweiterung, bei der der Ladevorgang länger als **eine** Sekunde dauert.</span><span class="sxs-lookup"><span data-stu-id="69aac-112">**Attention required** (red): Any _custom_ extension that takes longer than **one** second to load.</span></span> <span data-ttu-id="69aac-113">Die in den Testergebnissen angezeigte Gesamtladezeit wird nach "Modul laden" und "Initialisieren" unterteilt.</span><span class="sxs-lookup"><span data-stu-id="69aac-113">Total load time as displayed in test results is broken down by module load and init.</span></span>
- <span data-ttu-id="69aac-114">**Keine Aktion erforderlich** (grün): Keine Erweiterung benötigt länger als eine Sekunde zum Laden.</span><span class="sxs-lookup"><span data-stu-id="69aac-114">**No action required** (green): No extension is taking longer than one second to load.</span></span>

<span data-ttu-id="69aac-115">Wirkt sich eine Erweiterung auf die Ladezeit von Seiten aus, wird das Ergebnis im Abschnitt **Aktion erforderlich** der Ergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69aac-115">If an extension is impacting page load time, the result appears in the **Attention required** section of the results.</span></span> <span data-ttu-id="69aac-116">Klicken Sie auf das Ergebnis, um Einzelheiten zu sehen, welche Erweiterung langsam geladen wird.</span><span class="sxs-lookup"><span data-stu-id="69aac-116">Click the result to see details about which extension is loading slowly.</span></span> <span data-ttu-id="69aac-117">Zukünftige Updates des Tools "Seitendiagnose für SharePoint" können Aktualisierungen der Analyseregeln enthalten. Stellen Sie daher sicher, dass Sie immer über die neueste Version des Tools verfügen.</span><span class="sxs-lookup"><span data-stu-id="69aac-117">Future updates to the Page Diagnostics for SharePoint tool may include updates to analysis rules, so please ensure you always have the latest version of the tool.</span></span>

![Ergebnisse der Seitenladezeiten](media/page-diagnostics-for-spo/pagediag-extensions-load-time.png)

<span data-ttu-id="69aac-119">Die verfügbaren Informationen in den Ergebnissen umfassen:</span><span class="sxs-lookup"><span data-stu-id="69aac-119">Information available in the results includes:</span></span>

- <span data-ttu-id="69aac-120">**Name und ID** zeigt identifizierende Informationen an, die Ihnen beim Auffinden der Erweiterung auf der Seite helfen können.</span><span class="sxs-lookup"><span data-stu-id="69aac-120">**Name and ID** shows identifying information that can help you find the extension on the page</span></span>
- <span data-ttu-id="69aac-121">**Gesamt** zeigt die Gesamtzeit an, in der die Erweiterung initialisiert und geladen wird.</span><span class="sxs-lookup"><span data-stu-id="69aac-121">**Total** shows the total time for the extension to initialize and load</span></span>
- <span data-ttu-id="69aac-122">**Modul laden** zeigt die Zeit an, die zum Abrufen und Laden der Erweiterung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="69aac-122">**Module Load** shows the time taken to fetch and load the extension</span></span>
- <span data-ttu-id="69aac-123">**Initialisieren** zeigt die Zeit an, die für das Initialisieren einer Erweiterung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="69aac-123">**Init** shows the time taken for the extension to initialize</span></span>

<span data-ttu-id="69aac-124">Diese Informationen dienen Designern und Entwicklern zum Beheben von Problemen.</span><span class="sxs-lookup"><span data-stu-id="69aac-124">This information is provided to help designers and developers troubleshoot issues.</span></span> <span data-ttu-id="69aac-125">Diese Informationen sollten Ihrem Entwurfs- und Entwicklungsteam bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="69aac-125">This information should be provided to your design and development team.</span></span>

## <a name="overview-of-extensions"></a><span data-ttu-id="69aac-126">Übersicht über Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="69aac-126">Overview of extensions</span></span>

<span data-ttu-id="69aac-127">Mit SharePoint-Framework(SPFx)-Erweiterungen können Sie die SharePoint-Benutzeroberfläche erweitern.</span><span class="sxs-lookup"><span data-stu-id="69aac-127">SharePoint Framework (SPFx) Extensions can be used to extend the SharePoint user experience.</span></span> <span data-ttu-id="69aac-128">Mit SharePoint-Framework-Erweiterungen können Sie weitere Facetten der SharePoint-Benutzeroberfläche anpassen, u. a. Benachrichtigungsbereiche, Symbolleisten und Listendatenansichten.</span><span class="sxs-lookup"><span data-stu-id="69aac-128">With SharePoint Framework Extensions, you can customize more facets of the SharePoint experience, including notification areas, toolbars, and list data views.</span></span>

<span data-ttu-id="69aac-129">Erweiterungen können sich auf die Leistung einer SharePoint-Seite negativ auswirken, da außerdem CPU- und Netzwerkressourcen arbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="69aac-129">Extensions can have a bad influence on the performance of a SharePoint page as it also takes CPU and network resources to do required work.</span></span>

<span data-ttu-id="69aac-130">Es gibt vier Typen von Erweiterungen:</span><span class="sxs-lookup"><span data-stu-id="69aac-130">There are four types of extensions:</span></span>

- <span data-ttu-id="69aac-131">**Anwendungscustomizer** fügen der Seite Skripts hinzu, greifen auf bekannte HTML-Element-Platzhalter zu und erweitern sie um benutzerdefinierte Renderings.</span><span class="sxs-lookup"><span data-stu-id="69aac-131">**Application Customizers** adds scripts to the page, and accesses well-known HTML element placeholders and extends them with custom renderings.</span></span>
- <span data-ttu-id="69aac-132">**Feldcustomizer** stellen modifizierte Datenansichten für Felder in einer Liste bereit.</span><span class="sxs-lookup"><span data-stu-id="69aac-132">**Field Customizers** provides modified views to data for fields within a list.</span></span>
- <span data-ttu-id="69aac-133">**Befehlssätze** erweitern die SharePoint-Befehlsoberfläche um neue Aktionen und stellen clientseitigen Code bereit, mit dessen Hilfe Sie Verhaltensweisen implementieren können.</span><span class="sxs-lookup"><span data-stu-id="69aac-133">**Command Sets** extend the SharePoint command surfaces to add new actions, and provides client-side code that you can use to implement behaviors.</span></span>
- <span data-ttu-id="69aac-134">**Suchabfrage-Modifizierer (nur Vorschau)** werden unmittelbar vor der Suchabfrage aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="69aac-134">**Search Query Modifier (preview only)** are invoked just before the search query is executed.</span></span>

## <a name="remediate-extension-performance-issues"></a><span data-ttu-id="69aac-135">Beheben von Problemen mit der Leistung von Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="69aac-135">Remediate extension performance issues</span></span>

<span data-ttu-id="69aac-136">Befolgen Sie die Anweisungen in diesem Abschnitt, um Leistungsprobleme mit Erweiterungen zu erkennen und zu beheben, die in den Ergebnissen **Erweiterungen, die sich auf die Seitenladezeit auswirken** aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="69aac-136">Follow the guidance in this section to identify and remediate performance issues with extensions listed in the **Extensions are impacting page load time** results.</span></span>

>[!NOTE]
><span data-ttu-id="69aac-137">Anwendungscustomizer können in der Frühphase des Lebenszyklus einer Seite ausgeführt werden und die Leistung anderer Erweiterungen auf der Seite beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="69aac-137">Application customizers may be executed in the early stage during the lifecycle of a page and it may influence the performance of other extensions on the page.</span></span>

<span data-ttu-id="69aac-138">Die Überwachungsergebnisse im Seitendiagnosetool zeigen zwei Phasen der Ausführung einer Erweiterung an, um die potenziellen Auswirkungen auf die Leistung zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="69aac-138">The audit results in the Page Diagnostic Tool will display two stages of executing an extension in order to help identify the potential performance impact.</span></span>

- <span data-ttu-id="69aac-139">**Modul laden** ist die Dauer des Ladens der Erweiterung, was von der Größe einer Erweiterung beeinflusst wird. Deshalb empfiehlt es sich, nur die erforderlichen Bibliotheken in der Erweiterung zu bündeln und auch kleinere Bibliotheken auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="69aac-139">**Module load** is how long it takes to load the extension, which is impacted by the size of an extension so it is a good idea to only bundle the necessary libraries in the extension and to also choose lighter libraries.</span></span>
- <span data-ttu-id="69aac-140">**Initialisieren** ist die Initialisierungszeit der Erweiterung, und Erweiterungsentwickler sollten überlegen, ob die Erweiterung unnötig arbeitet oder während der Initialisierungsphase zu viele Befehle ausführt.</span><span class="sxs-lookup"><span data-stu-id="69aac-140">**Init** is the initialization time of the extension and extension developers should consider whether the extension is doing unnecessary work or executing too many commands during the initializing stage.</span></span>

<span data-ttu-id="69aac-141">Seitenautoren können das Überwachungsergebnis auch verwenden, um festzustellen, ob eine Seite zu viele Erweiterungen hat, da sich dies negativ auf die Leistung einer Seite auswirkt.</span><span class="sxs-lookup"><span data-stu-id="69aac-141">Page authors can also use the audit result to see whether a page has too many extensions as too many extensions will negatively impact the performance of a page.</span></span>

- <span data-ttu-id="69aac-142">**Erweiterungsgröße und Abhängigkeiten**</span><span class="sxs-lookup"><span data-stu-id="69aac-142">**Extension size and dependencies**</span></span>
  - <span data-ttu-id="69aac-143">Die Verwendung von Office 365 CDN ist für den optimalen statischen Ressourcendownload erforderlich.</span><span class="sxs-lookup"><span data-stu-id="69aac-143">Use of the Office 365 CDN is required for optimal static resource download.</span></span> <span data-ttu-id="69aac-144">Öffentliche CDN-Quellen sind für _js/css_-Dateien vorzuziehen.</span><span class="sxs-lookup"><span data-stu-id="69aac-144">Public CDN origins are preferable for _js/css_ files.</span></span> <span data-ttu-id="69aac-145">Weitere Informationen zur Verwendung von Office 365 CDN finden Sie unter [Verwendung von Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-office-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="69aac-145">For more information about using the Office 365 CDN, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-office-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="69aac-146">Verwenden Sie Frameworks wie _React_ und _Fabric-Importe_, die Bestandteil des SharePoint-Frameworks (SPFx) sind.</span><span class="sxs-lookup"><span data-stu-id="69aac-146">Reuse frameworks like _React_ and _Fabric imports_ that come as part of the SharePoint Framework (SPFx).</span></span> <span data-ttu-id="69aac-147">Weitere Informationen finden Sie unter [Übersicht über das SharePoint-Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).</span><span class="sxs-lookup"><span data-stu-id="69aac-147">For more information, see [Overview of the SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).</span></span>
  - <span data-ttu-id="69aac-148">Stellen Sie sicher, dass Sie die neueste Version des SharePoint-Frameworks verwenden, und führen Sie stets Aktualisierungen auf neue Versionen durch, sobald diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="69aac-148">Ensure that you are using the latest version of the SharePoint Framework, and upgrade to new versions as they become available.</span></span>
- <span data-ttu-id="69aac-149">**Datenabruf/-zwischenspeicherung**</span><span class="sxs-lookup"><span data-stu-id="69aac-149">**Data fetching/caching**</span></span>
  - <span data-ttu-id="69aac-150">Wenn sich die Erweiterung auf zusätzliche Serveraufrufe stützt, um Daten für die Anzeige abzurufen, stellen Sie sicher, dass diese Server-APIs schnell sind und/oder clientseitige Zwischenspeicherung implementieren (z. B. die Verwendung von _localStorage_ oder _IndexDB_ für größere Sets).</span><span class="sxs-lookup"><span data-stu-id="69aac-150">If the extension relies on extra server calls to fetch data for display, ensure those server APIs are fast and/or implement client side caching (such as using _localStorage_ or _IndexDB_ for larger sets).</span></span>
  - <span data-ttu-id="69aac-151">Wenn zum Rendern wichtiger Daten mehrere Aufrufe erforderlich sind, sollten Sie die Batchverarbeitung auf dem Server oder andere Methoden zum Konsolidieren von Anforderungen in einen einzigen Anruf erwägen.</span><span class="sxs-lookup"><span data-stu-id="69aac-151">If multiple calls are required to render critical data, consider batching on the server or other methods of consolidating requests to a single call.</span></span>
  - <span data-ttu-id="69aac-152">Wenn bestimmte Datenelemente eine langsamere API benötigen, für das anfängliche Rendern aber nicht kritisch sind, entkoppeln Sie diese mit einem separaten Aufruf, der nach dem Rendern kritischer Daten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="69aac-152">Alternatively, if some elements of data require a slower API, but are not critical to initial rendering, decouple these to a separate call that is executed after critical data is rendered.</span></span>
  - <span data-ttu-id="69aac-153">Wenn mehrere Webparts dieselben Daten nutzen, verwenden Sie eine gemeinsame Datenschicht, um doppelte Aufrufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="69aac-153">If multiple parts use the same data, utilize a common data layer to avoid duplicate calls.</span></span>
- <span data-ttu-id="69aac-154">**Renderingzeit**</span><span class="sxs-lookup"><span data-stu-id="69aac-154">**Rendering time**</span></span>
  - <span data-ttu-id="69aac-155">Alle Medienquellen wie Bilder und Videos sollten an die Grenzen des Containers, Geräts und/oder Netzwerks angepasst sein, um das Herunterladen unnötig großer Anlagen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="69aac-155">Any media sources like images and videos should be sized to the limits of the container, device and/or network to avoid downloading unnecessary large assets.</span></span> <span data-ttu-id="69aac-156">Weitere Informationen zu Inhaltsabhängigkeiten finden Sie unter [Verwendung von Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-office-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="69aac-156">For more information about content dependencies, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-office-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="69aac-157">Vermeiden Sie API-Aufrufe, die einen Umbruch, komplexe CSS-Regeln oder komplizierte Animationen verursachen.</span><span class="sxs-lookup"><span data-stu-id="69aac-157">Avoid API calls that cause re-flow, complex CSS rules or complicated animations.</span></span> <span data-ttu-id="69aac-158">Weitere Informationen finden Sie unter [Minimizing browser reflow](https://developers.google.com/speed/docs/insights/browser-reflow) (Minimieren von Browserumbrüchen).</span><span class="sxs-lookup"><span data-stu-id="69aac-158">For more information, see [Minimizing browser reflow](https://developers.google.com/speed/docs/insights/browser-reflow).</span></span>
  - <span data-ttu-id="69aac-159">Vermeiden Sie die Verwendung von verketteten Aufgaben mit langen Ausführungszeiten.</span><span class="sxs-lookup"><span data-stu-id="69aac-159">Avoid use of chained long running tasks.</span></span> <span data-ttu-id="69aac-160">Verteilen Sie Aufgaben mit langen Ausführungszeiten stattdessen auf separate Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="69aac-160">Instead, break long running tasks apart into separate queues.</span></span> <span data-ttu-id="69aac-161">Weitere Informationen finden Sie unter [Optimize JavaScript Execution](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution) (Optimieren der JavaScript-Ausführung).</span><span class="sxs-lookup"><span data-stu-id="69aac-161">For more information, see [Optimize JavaScript Execution](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).</span></span>
  - <span data-ttu-id="69aac-162">Reservieren Sie entsprechenden Speicherplatz für asynchrones Rendern von Medien oder visuellen Elementen, um übersprungene Frames und Stottern zu vermeiden (auch als _Jank_ bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="69aac-162">Reserve corresponding space for asynchronously rendering media or visual elements to avoid skipped frames and stuttering (also known as _jank_).</span></span>
  - <span data-ttu-id="69aac-163">Wenn ein bestimmter Browser ein für das Rendern verwendetes Feature nicht unterstützt, laden Sie ein Polyfill, oder schließen Sie die Ausführung von abhängigem Code aus.</span><span class="sxs-lookup"><span data-stu-id="69aac-163">If a certain browser doesn't support a feature used in rendering, either load a polyfill or exclude running dependent code.</span></span> <span data-ttu-id="69aac-164">Wenn das Feature nicht kritisch ist, entfernen Sie Ressourcen wie Ereignishandler, um Speicherlecks zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="69aac-164">If the feature is not critical, dispose resources such as event handlers to avoid memory leaks.</span></span>

<span data-ttu-id="69aac-165">Bevor Sie Seitenrevisionen zur Behebung von Leistungsproblemen durchführen, notieren Sie sich die Ladezeit der Seite in den Analyseergebnissen.</span><span class="sxs-lookup"><span data-stu-id="69aac-165">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="69aac-166">Führen Sie das Tool nach Ihrer Revision erneut aus, um zu sehen, ob das neue Ergebnis innerhalb des Grenzwertes liegt, und überprüfen Sie die Ladezeit der neuen Seite, um festzustellen, ob eine Verbesserung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="69aac-166">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Ergebnisse der Seitenladezeiten](media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="69aac-168">Die Seitenladezeit kann aufgrund einer Vielzahl von Faktoren wie Netzwerklast, Tageszeit und anderen vorübergehenden Schwierigkeiten variieren.</span><span class="sxs-lookup"><span data-stu-id="69aac-168">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="69aac-169">Sie sollten die Seitenladezeit einige Male vor und nach der Durchführung von Änderungen testen, um einen Mittelwert zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="69aac-169">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="69aac-170">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="69aac-170">Related topics</span></span>

[<span data-ttu-id="69aac-171">Optimieren der Leistung von SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="69aac-171">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="69aac-172">Optimieren der Leistung von Office 365</span><span class="sxs-lookup"><span data-stu-id="69aac-172">Tune Office 365 performance</span></span>](tune-office-365-performance.md)

[<span data-ttu-id="69aac-173">Leistung in der modernen SharePoint-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="69aac-173">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="69aac-174">Netzwerke für die Inhaltsübermittlung</span><span class="sxs-lookup"><span data-stu-id="69aac-174">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="69aac-175">Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="69aac-175">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-office-365-cdn-with-spo.md)