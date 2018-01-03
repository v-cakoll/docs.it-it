---
title: Accedere agli oggetti incorporati utilizzando l'automazione interfaccia utente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
caps.latest.revision: "17"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 37110708efa49912d0ed9c81746d125167e17985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="access-embedded-objects-using-ui-automation"></a><span data-ttu-id="36f98-102">Accedere agli oggetti incorporati utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="36f98-102">Access Embedded Objects Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="36f98-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="36f98-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="36f98-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="36f98-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="36f98-105">Questo argomento illustra come [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] possa essere usato per esporre oggetti incorporati nel contenuto di un controllo testo.</span><span class="sxs-lookup"><span data-stu-id="36f98-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose objects embedded within the content of a text control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36f98-106">Gli oggetti incorporati possono includere immagini, collegamenti ipertestuali, pulsanti, tabelle o controlli ActiveX.</span><span class="sxs-lookup"><span data-stu-id="36f98-106">Embedded objects can include images, hyperlinks, buttons, tables, or ActiveX controls.</span></span>  
  
 <span data-ttu-id="36f98-107">Gli oggetti incorporati sono considerati figli del provider di testo di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36f98-107">Embedded objects are considered children of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="36f98-108">Ciò consente di esporli con la stessa struttura ad albero di automazione interfaccia utente di tutti gli altri elementi dell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36f98-108">This allows them to be exposed through the same UI Automation tree structure as all other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elements.</span></span> <span data-ttu-id="36f98-109">La funzionalità, a sua volta, viene esposta con i pattern di controllo richiesti in genere dal tipo di controllo degli oggetti incorporati (ad esempio, poiché i collegamenti ipertestuali sono basati sul testo, supporteranno <xref:System.Windows.Automation.TextPattern>).</span><span class="sxs-lookup"><span data-stu-id="36f98-109">Functionality, in turn, is exposed through the control patterns typically required by the embedded objects control type (for example, since hyperlinks are text-based they will support <xref:System.Windows.Automation.TextPattern>).</span></span>  
  
 <span data-ttu-id="36f98-110">![Oggetti incorporati in un contenitore di testo. ] (../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span><span class="sxs-lookup"><span data-stu-id="36f98-110">![Embedded objects in a text container.](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span></span>  
<span data-ttu-id="36f98-111">Un documento di esempio con contenuto testuale, ("non tutti sanno che" ...) e due oggetti incorporati (un'immagine di una balena e un collegamento ipertestuale), utilizzati come destinazione per gli esempi di codice.</span><span class="sxs-lookup"><span data-stu-id="36f98-111">A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36f98-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="36f98-112">Example</span></span>  
 <span data-ttu-id="36f98-113">L'esempio di codice seguente illustra come recuperare una raccolta di oggetti incorporati da un provider di testo di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36f98-113">The following code example demonstrates how to retrieve a collection of embedded objects from within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="36f98-114">Per il documento di esempio fornito nell'introduzione, verranno restituiti due oggetti (un elemento immagine e un elemento testo).</span><span class="sxs-lookup"><span data-stu-id="36f98-114">For the sample document provided in the introduction, two objects would be returned (an image element and a text element).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36f98-115">All'elemento immagine sarà associato un testo intrinseco che descrive l'immagine, in genere in <xref:System.Windows.Automation.AutomationElement.NameProperty> (ad esempio, "A blue whale.").</span><span class="sxs-lookup"><span data-stu-id="36f98-115">The image element should have some intrinsic text associated with it that describes the image, typically in its <xref:System.Windows.Automation.AutomationElement.NameProperty> (for example, "A blue whale.").</span></span> <span data-ttu-id="36f98-116">Tuttavia, quando si ottiene un intervallo di testo che si estende sull'oggetto immagine, né l'immagine né questo testo descrittivo vengono restituiti nel flusso di testo.</span><span class="sxs-lookup"><span data-stu-id="36f98-116">However, when a text range spanning the image object is obtained, neither the image nor this descriptive text is returned in the text stream.</span></span>  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a><span data-ttu-id="36f98-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="36f98-117">Example</span></span>  
 <span data-ttu-id="36f98-118">L'esempio di codice seguente illustra come ottenere un intervallo di testo da un oggetto incorporato in un provider di testo di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36f98-118">The following code example demonstrates how to obtain a text range from an embedded object within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="36f98-119">L'intervallo di testo recuperato è un intervallo vuoto dove l'endpoint iniziale segue "…</span><span class="sxs-lookup"><span data-stu-id="36f98-119">The text range retrieved is an empty range where the starting endpoint follows "…</span></span> <span data-ttu-id="36f98-120">ocean.(space)" e l'endpoint finale precede il carattere "." di chiusura che rappresenta il collegamento ipertestuale incorporato (come illustrato dall'immagine fornita nell'introduzione).</span><span class="sxs-lookup"><span data-stu-id="36f98-120">ocean.(space)" and the ending endpoint precedes the closing "." representing the embedded hyperlink (as shown by the image provided in the introduction).</span></span> <span data-ttu-id="36f98-121">Anche se è un intervallo vuoto, non è considerato un intervallo degenere perché ha un'estensione diversa da zero.</span><span class="sxs-lookup"><span data-stu-id="36f98-121">Even though this is an empty range, it is not considered a degenerate range because it has a non-zero span.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36f98-122"><xref:System.Windows.Automation.TextPattern> può recuperare on oggetto incorporato basato su testo, ad esempio un collegamento ipertestuale. Tuttavia, sarà necessario ottenere un oggetto <xref:System.Windows.Automation.TextPattern> secondario dall'oggetto incorporato per esporne la funzionalità completa.</span><span class="sxs-lookup"><span data-stu-id="36f98-122"><xref:System.Windows.Automation.TextPattern> can retrieve a text-based embedded object such as a hyperlink; however, a secondary <xref:System.Windows.Automation.TextPattern> will have to be obtained from the embedded object to expose its full functionality.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a><span data-ttu-id="36f98-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36f98-123">See Also</span></span>  
 [<span data-ttu-id="36f98-124">Panoramica di TextPattern di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="36f98-124">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="36f98-125">Panoramica dei pattern di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="36f98-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="36f98-126">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="36f98-126">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="36f98-127">Aggiungere contenuto a una casella di testo usando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="36f98-127">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="36f98-128">Trovare ed evidenziare il testo usando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="36f98-128">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
