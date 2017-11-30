---
title: Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82401a18132801f9aa5368832b96be3cb67a8642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a><span data-ttu-id="17d13-102">Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM</span><span class="sxs-lookup"><span data-stu-id="17d13-102">White Space and Significant White Space Handling when Loading the DOM</span></span>
<span data-ttu-id="17d13-103">Quando si carica il documento, è possibile impostare l'opzione per mantenere gli spazi vuoti e creare **XmlWhitespace** nodi nell'albero del documento.</span><span class="sxs-lookup"><span data-stu-id="17d13-103">When loading the document, you can set the option to preserve white space and create **XmlWhitespace** nodes in the document tree.</span></span> <span data-ttu-id="17d13-104">Per creare nodi con spazi vuoti, impostare il **PreserveWhitespace** proprietà su true.</span><span class="sxs-lookup"><span data-stu-id="17d13-104">To create white space nodes, set the **PreserveWhitespace** property to true.</span></span> <span data-ttu-id="17d13-105">Se la proprietà è impostata su **false**, ovvero l'impostazione predefinita, i nodi spazi vuoti non vengono creati.</span><span class="sxs-lookup"><span data-stu-id="17d13-105">If the property is set to **false**, which is the default, white space nodes are not created.</span></span> <span data-ttu-id="17d13-106">I nodi spazi vuoti significativi vengono sempre conservati e **XmlSignificantWhitespace** nodi vengono sempre creati in memoria per rappresentare i dati, indipendentemente dall'impostazione del **PreserveWhitespace** flag.</span><span class="sxs-lookup"><span data-stu-id="17d13-106">Significant white spaces nodes are always preserved, and **XmlSignificantWhitespace** nodes are always created in memory to represent this data, regardless of the setting of the **PreserveWhitespace** flag.</span></span>  
  
 <span data-ttu-id="17d13-107">Se il documento viene caricato da un lettore, l'impostazione del **PreserveWhitespace** flag di proprietà di **XmlDocument** classe influisce sulla creazione di **XmlWhitespace** nodi solo quando il **WhitespaceHandling** proprietà il **XmlTextReader** non è impostata su **WhitespaceHandling**.</span><span class="sxs-lookup"><span data-stu-id="17d13-107">If the document is loaded from a reader, then setting of the **PreserveWhitespace** flag property on the **XmlDocument** class affects the creation of **XmlWhitespace** nodes only when the **WhitespaceHandling** property on the **XmlTextReader** is not set to **WhitespaceHandling.None**.</span></span> <span data-ttu-id="17d13-108">È il valore della **WhitespaceHandling** il lettore ha la precedenza sull'impostazione del flag nella proprietà di **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="17d13-108">It is the value of the **WhitespaceHandling** property on the reader that takes precedence over the setting of that flag on the **XmlDocument**.</span></span> <span data-ttu-id="17d13-109">Per ulteriori informazioni su **XmlSignificantWhitespace**, vedere <xref:System.Xml.XmlSignificantWhitespace>.</span><span class="sxs-lookup"><span data-stu-id="17d13-109">For more information on **XmlSignificantWhitespace**, see <xref:System.Xml.XmlSignificantWhitespace>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d13-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17d13-110">See Also</span></span>  
 [<span data-ttu-id="17d13-111">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="17d13-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
