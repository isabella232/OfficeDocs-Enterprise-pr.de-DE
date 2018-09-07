---
title: Bildoptimierung für SharePoint Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/19/2018
ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: Erfahren Sie, wie von Darstellungen und Sprites zum Verbessern der Leistung von Bild auf Ihrer SharePoint Online-Websites.
ms.openlocfilehash: 313046dec885a38062635254699301bcf556d698
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "22540742"
---
# <a name="image-optimization-for-sharepoint-online"></a><span data-ttu-id="c0576-103">Bildoptimierung für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c0576-103">Image optimization for SharePoint Online</span></span>

<span data-ttu-id="c0576-p101">Die Geschwindigkeit beim Laden einer Webseite hängt die Gesamtgröße aller Komponenten, die zum Rendern der Seite, einschließlich Bilder, HTML, JavaScript und CSS-erforderlich. Bilder sind eine hervorragende Möglichkeit zum Ihrer Website ansprechender zu gestalten, aber ihre Größe kann die Leistung beeinträchtigen. Durch Optimieren der Abbilder mit Komprimierung und Ändern der Größe und Verwendung von Sprites, können Sie die Effekte der sehr großen Bilder versetzen. Bilddarstellungen SharePoint verwenden, können Sie ein einzelnes großes Bild hochladen und Anzeigen von Abschnitten des Bilds, sodass es, sondern wiederverwendet werden erneut geladen.</span><span class="sxs-lookup"><span data-stu-id="c0576-p101">The loading speed of a webpage depends on the combined size of all the components required to render the page including images, HTML, JavaScript, and CSS. Images are a great way to make your site more appealing, but their size can affect performance. By optimizing your images with compression and resizing, and using sprites, you can offset the effects of very large images. Using SharePoint image renditions, you can upload a single large image, and display sections of the image allowing it to be reused rather than reloaded.</span></span>
  
## <a name="using-sprites-to-speed-up-image-loading-in-sharepoint-online"></a><span data-ttu-id="c0576-108">Verwenden von Sprites für ein schnelleres Laden von Bildern in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c0576-108">Using sprites to speed up image loading in SharePoint Online</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="c0576-p102">Ein Bild Sprite enthält viele kleinere Bilder heruntergeladen. Verwendung von CSS, wählen Sie einen Teil der zusammengesetzten Bilds auf einem bestimmten Teil der Seite mit absolute Positionierung angezeigt. Im Grunde Sie ein einzelnes Bild auf der Seite anstelle von laden mehrere Bilder zu verschieben, und stellen einen kleinen Teil dieses Bild sichtbar über einem kleinen Fenster, in dem die erforderliche Komponente des Bilds Sprite angezeigt wird, für den Endbenutzer. SharePoint Online verwendet Sprites, um die verschiedenen Symbole in der Sprite spcommon.png anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c0576-p102">An image sprite contains many smaller images. Using CSS you select a part of the composite image to display on a particular part of the page with absolute positioning. Basically, you move a single image around the page instead of loading multiple images, and make a small part of that image visible through a small window where the required part of the sprite image is shown to the end user. SharePoint Online uses sprites to display its various icons in the sprite spcommon.png.</span></span>  <br/>  <span data-ttu-id="c0576-113">Was ist hier behandelt:</span><span class="sxs-lookup"><span data-stu-id="c0576-113">What's covered here:</span></span>  <br/>  <span data-ttu-id="c0576-114">Bildkomprimierung</span><span class="sxs-lookup"><span data-stu-id="c0576-114">Image compression</span></span>  <br/>  <span data-ttu-id="c0576-115">Bild-Optimierung</span><span class="sxs-lookup"><span data-stu-id="c0576-115">Image optimization</span></span>  <br/>  <span data-ttu-id="c0576-116">SharePoint-bilddarstellungen</span><span class="sxs-lookup"><span data-stu-id="c0576-116">SharePoint image renditions</span></span>  <br/> |![Screenshot des spcommon](media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)|
   
<span data-ttu-id="c0576-p103">Dies kann die Leistung verbessern, da Sie nur ein Bild anstelle mehrerer herunterladen und Zwischenspeichern und das Abbild. Selbst wenn das Bild nicht zwischengespeicherten, bleibt, wenn ein einzelnes Bild anstatt mehrere Bilder, reduziert diese Methode die Gesamtzahl der HTTP-Anforderungen an den Server, und wie oft Laden der Seite wird. Dies ist eine Form des Image bündeln. Dies ist ein sehr nützliches Verfahren wenn die Bilder nicht sehr häufig, z. B. Symbole an, ändern wie im obigen Beispiel SharePoint dargestellt. Sie können zum [Web Essentials](http://vswebessentials.com/), ein Projekt von Drittanbietern, Open Source, Community-basierten ganz einfach in Microsoft Visual Studio dazu verwenden. Weitere Informationen finden Sie unter [Verkleinerung und bündeln in SharePoint Online](https://go.microsoft.com/fwlink/?LinkId=708698).</span><span class="sxs-lookup"><span data-stu-id="c0576-p103">This can increase performance because you download only one image instead of several and then cache and reuse that image. Even if the image does not remain cached, by having a single image instead of multiple images, this method reduces the total number of HTTP requests to the server which will reduce page loading times. This is really a form of image bundling. This is a very useful technique if the images are not changing very often, for example, icons, as shown in the SharePoint example provided above. You can how to use [Web Essentials](http://vswebessentials.com/), a third-party, open-source, community-based project to achieve this easily in Microsoft Visual Studio. For more information, see [Minification and bundling in SharePoint Online](https://go.microsoft.com/fwlink/?LinkId=708698).</span></span>
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading-in-sharepoint"></a><span data-ttu-id="c0576-124">Verwenden von Bildkomprimierung und -optimierung für ein schnelleres Laden von Seiten in SharePoint</span><span class="sxs-lookup"><span data-stu-id="c0576-124">Using image compression and optimization to speed up page loading in SharePoint</span></span>

<span data-ttu-id="c0576-p104">Bei Bildkomprimierung und -optimierung wird dafür gesorgt, dass die Dateigröße der Bilder reduziert wird, die Sie auf Ihrer Website verwenden. Oft ist die beste Methode zum Reduzieren der Größe eines Bilds, die Größe des Bilds auf die maximalen Abmessungen zu ändern, mit denen es auf der Website angezeigt wird. Es ist nicht sinnvoll, ein Bild größer zu machen, als es je angezeigt wird. Mit einem Bildeditor können Sie sicherstellen, dass die Bilder die richtigen Maße haben, und so die Größe Ihrer Seite schnell und einfach verringern.</span><span class="sxs-lookup"><span data-stu-id="c0576-p104">Image compression and optimization is about reducing the file size of the images you use on your site. Often, the best technique to reduce the size of an image is to resize the image to the maximum dimensions that it will be viewed on the site. There is no sense in having an image larger than it will ever be viewed. Making sure images are of the correct dimensions using an image editor is a quick and easy way to reduce the size of your page.</span></span>
  
<span data-ttu-id="c0576-p105">Nachdem die richtige Größe sind, besteht der nächste Schritt die Komprimierung von diese Bilder zu optimieren. Es gibt verschiedene Tools zur Verfügung, für die Komprimierung und Optimierung, einschließlich Photo Gallery und Drittanbietertools verwenden. Die Komprimierung ist die Dateigröße so weit wie möglich zu verringern, ohne Beeinträchtigung der alle erkennbaren Qualität für Endbenutzer. Stellen Sie sicher, dass Sie testen die komprimierten Dateien auf einem High-Definition-Display, um sicherzustellen, dass sie immer noch eine gute aussieht.</span><span class="sxs-lookup"><span data-stu-id="c0576-p105">Once images are the right size, the next step is to optimize the compression of these images. There are various tools available to use for compression and optimization, including Photo Gallery and third-party tools. The key to compression is to reduce the file size as much as possible without losing any discernible quality for end users. Make sure you test your compressed files on a high-definition display to ensure they will still look good.</span></span>
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a><span data-ttu-id="c0576-133">Beschleunigen von Seitendownloads mithilfe von SharePoint-Bildwiedergaben</span><span class="sxs-lookup"><span data-stu-id="c0576-133">Speed up page downloads by using SharePoint image renditions</span></span>

<span data-ttu-id="c0576-p106">Bilddarstellungen sind ein Feature in SharePoint Online, die verschiedenen Versionen von Images basierend auf vordefinierten Image Dimensionen bereitgestellt werden können. Dies ist besonders wichtig, wenn benutzergenerierten Bildinhalt vorhanden ist oder der Bildgröße, z. B. Breite und Höhe durch den CSS-Code auf der Website behoben werden. Selbst wenn ein Bild durch CSS behoben ist, wird das vollständige Lösung Bild noch geladen. In diesem Fall kann die Dateigröße mithilfe von bilddarstellungen reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="c0576-p106">Image renditions are a feature in SharePoint Online that allows you to serve up different versions of images based on pre-defined image dimensions. This is especially important when there is user-generated image content or the image dimensions such as width and height are fixed by the CSS on the site. Even if an image is fixed by CSS, the full resolution image is still loaded. In this case the file size can be reduced by using image renditions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0576-p107">Darstellungen sind nur verfügbar für SharePoint, wenn die Veröffentlichung aktiviert ist. Sie können die Veröffentlichung unter Einstellungen aktivieren \> Websiteeinstellungen \> Websitefeatures verwalten \> SharePoint Server-Veröffentlichung. Die Option wird andernfalls nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0576-p107">Renditions are only available for SharePoint when publishing is enabled. You can enable publishing under Settings \> Site Settings \> Manage site features \> SharePoint Server Publishing. The option will not appear otherwise.</span></span> 
  
<span data-ttu-id="c0576-p108">Bei der Größenänderung durch Bildwiedergaben wird die kleinste Dimension, die Sie definieren, herangezogen, entweder Breite oder Höhe. Dann wird die Größe des Bilds so geändert, dass automatisch auch die Größe der anderen Dimension auf dem gesperrten Seitenverhältnis geändert wird. Standardmäßig wird durch die verbleibenden Dimensionen das Bild von der Mitte zugeschnitten. Beispiel: Wenn Sie eine Bildwiedergabe mit 100 Pixel Breite und 50 Pixel Höhe definieren und das ursprüngliche Bild 1.000 Pixel breit und 800 Pixel hoch ist, wird dessen Größe so geändert, dass die Dimension der 800 Pixel jetzt 50 Pixel beträgt, und die Dimension der 1.000 Pixel (jetzt 62,5 Pixel) wird von der Mitte des Bilds zugeschnitten.</span><span class="sxs-lookup"><span data-stu-id="c0576-p108">The image rendition resizing works by taking the smallest dimension you define, either width or height, and then resizing the image so that the other dimension is automatically resized based on the locked aspect ratio. By default, it will crop the image from the center by the remaining dimensions. For example, if you define a rendition of 100px wide and 50px high and your original image is 1000px wide and 800px high, it will be resized so that the 800px dimension is now 50px and the 1000px dimension (now 62.5px) is cropped from the center of the image.</span></span>
  
<span data-ttu-id="c0576-p109">Die Schritte sind relativ einfach. Damit für Bilder aber Bildwiedergaben verwendet werden können, müssen sich die Bildwiedergaben auf der SharePoint-Website befinden, bevor Sie die Bilder hinzufügen. Darüber hinaus müssen Sie auch die Funktionen SharePoint Server-Veröffentlichungsinfrastruktur (Websitesammlungsebene) und SharePoint Server-Veröffentlichung (Websiteebene) aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="c0576-p109">The steps are relatively simple but for images to use the renditions, the renditions need to be on the SharePoint site before you add the images. In addition, you also need to have the SharePoint Server Publishing Infrastructure (Site Collection Level) and SharePoint Server Publishing (Site Level) features turned on.</span></span>
  
 <span data-ttu-id="c0576-146">**Hinzufügen einer Wiedergabe eines beschnittenen Bildes um Laden der Seite zu beschleunigen**</span><span class="sxs-lookup"><span data-stu-id="c0576-146">**Add an image rendition to speed up page loading**</span></span>
  
1. <span data-ttu-id="c0576-147">Stellen Sie sicher, dass das Benutzerkonto, mit das dieser Vorgang ausgeführt wird, mindestens Entwurfsberechtigungen für die Website auf oberster Ebene der Websitesammlung, und die Website auf einer Webseite veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="c0576-147">Verify that the user account that is performing this procedure has, at minimum, Design permissions to the top-level site of the site collection, and that the site is being published to a webpage.</span></span>
    
2. <span data-ttu-id="c0576-148">Wechseln Sie in einem Webbrowser zu der Website auf oberster Ebene der veröffentlichenden Websitesammlung.</span><span class="sxs-lookup"><span data-stu-id="c0576-148">In a web browser, go to the top-level site of the publishing site collection.</span></span>
    
3. <span data-ttu-id="c0576-149">Wählen Sie das Symbol **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="c0576-149">Choose the **Settings** icon.</span></span> 
    
4. <span data-ttu-id="c0576-150">Auf der Seite **Websiteeinstellungen** im Abschnitt **Aussehen und Verhalten** sehen Sie die integrierten Bildwiedergaben.</span><span class="sxs-lookup"><span data-stu-id="c0576-150">On the **Site Settings** page, in the **Look and Feel** section, you will see the built-in image renditions.</span></span> 
    
    <span data-ttu-id="c0576-151">Sie können sofort nutzbare Bildwiedergaben verwenden oder **Bildwiedergaben** auswählen, um eine neue zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0576-151">You can use the out of the box renditions or choose **Image Renditions** to create a new one.</span></span> 
    
    ![Screenshot der Wiedergabe eines beschnittenen Bildes](media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. <span data-ttu-id="c0576-153">Wählen Sie auf der Seite **Bildwiedergaben** die Option **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="c0576-153">On the **Image Renditions** page, choose **Add new item**.</span></span>
    
    ![Screenshot von "Neues Element hinzufügen"](media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. <span data-ttu-id="c0576-155">Geben Sie auf der Seite **Neue Bildwiedergabe** im Feld **Name** einen Namen für die Bildwiedergabe ein.</span><span class="sxs-lookup"><span data-stu-id="c0576-155">On the **New Image Rendition** page, in the **Name** box, enter a name for the rendition.</span></span> 
    
7. <span data-ttu-id="c0576-156">Geben Sie in den Textfeldern **Breite** und **Höhe** die Breite und Höhe für die Bildwiedergabe in Pixel ein, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c0576-156">In the **Width** and **Height** text boxes, enter the width and height, in pixels, of the rendition, and then choose **Save**.</span></span>
    
    ![Screenshot des Bildwiedergabenamens](media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions-in-sharepoint"></a><span data-ttu-id="c0576-158">Benutzerdefiniertes Zuschneiden mit Bildwiedergaben in SharePoint</span><span class="sxs-lookup"><span data-stu-id="c0576-158">Custom cropping with image renditions in SharePoint</span></span>

<span data-ttu-id="c0576-p110">Standardmäßig wird eine Wiedergabe eines beschnittenen Bildes aus der Mitte des Bilds generiert. Sie können die Wiedergabe eines beschnittenen Bildes für einzelne Bilder anpassen, indem Sie zuschneiden den Teil des Bilds, das Sie verwenden möchten. Sie können die Bilder einzeln, pro Wiedergabe zuschneiden. Zuschneiden die Bilder beschleunigt mithilfe SharePoints BLOB-Cache, erstellen Sie eine Version des Bilds für jede Wiedergabe Laden der Seite ab. Auf diese Weise die Serverlast wird reduziert, da das Bild nur einmal Größe wird und bereit ist, um mehrere Male für Endbenutzer zu verarbeiten. Weitere Informationen zum ein Wiedergabe eines beschnittenen Bildes zuzuschneiden finden Sie unter [ein Wiedergabe eines beschnittenen Bildes zuzuschneiden](https://go.microsoft.com/fwlink/p/?LinkId=525626).</span><span class="sxs-lookup"><span data-stu-id="c0576-p110">By default, an image rendition is generated from the center of the image. You can adjust the image rendition for individual images by cropping the portion of the image that you want to use. You can crop the images on an individual basis, per rendition. Cropping the images speeds up page loading by using SharePoint's blob cache to create a version of the image for each rendition. This way the server load is reduced because the image is only resized once and is then ready to serve to end users multiple times. For more information on how to crop an image rendition, see [Crop an image rendition](https://go.microsoft.com/fwlink/p/?LinkId=525626).</span></span>
  
