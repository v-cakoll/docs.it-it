---
title: Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d9bbb14320b84a6d417c5c28026b169092de219
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46706132"
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a><span data-ttu-id="7b361-102">Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM</span><span class="sxs-lookup"><span data-stu-id="7b361-102">White Space and Significant White Space Handling when Loading the DOM</span></span>
<span data-ttu-id="7b361-103">Quando si carica il documento, è possibile impostare l'opzione che consente di conservare gli spazi e creare nodi **XmlWhitespace** nell'albero del documento.</span><span class="sxs-lookup"><span data-stu-id="7b361-103">When loading the document, you can set the option to preserve white space and create **XmlWhitespace** nodes in the document tree.</span></span> <span data-ttu-id="7b361-104">Per creare nodi con spazi, impostare la proprietà **PreserveWhitespace** su true.</span><span class="sxs-lookup"><span data-stu-id="7b361-104">To create white space nodes, set the **PreserveWhitespace** property to true.</span></span> <span data-ttu-id="7b361-105">Se la proprietà è impostata su **false**, che rappresenta il valore predefinito, i nodi con spazi non vengono creati.</span><span class="sxs-lookup"><span data-stu-id="7b361-105">If the property is set to **false**, which is the default, white space nodes are not created.</span></span> <span data-ttu-id="7b361-106">I nodi con spazi significativi vengono sempre mantenuti e i nodi **XmlSignificantWhitespace** vengono sempre creati in memoria per rappresentare tali dati, indipendentemente dall'impostazione del flag **PreserveWhitespace**.</span><span class="sxs-lookup"><span data-stu-id="7b361-106">Significant white spaces nodes are always preserved, and **XmlSignificantWhitespace** nodes are always created in memory to represent this data, regardless of the setting of the **PreserveWhitespace** flag.</span></span>  
  
 <span data-ttu-id="7b361-107">Se il documento viene caricato da un lettore, l'impostazione della proprietà del flag **PreserveWhitespace** nella classe **XmlDocument** incide sulla creazione dei nodi **XmlWhitespace** solo se la proprietà **WhitespaceHandling** di **XmlTextReader** non è impostata su **WhitespaceHandling.None**.</span><span class="sxs-lookup"><span data-stu-id="7b361-107">If the document is loaded from a reader, then setting of the **PreserveWhitespace** flag property on the **XmlDocument** class affects the creation of **XmlWhitespace** nodes only when the **WhitespaceHandling** property on the **XmlTextReader** is not set to **WhitespaceHandling.None**.</span></span> <span data-ttu-id="7b361-108">Il valore della proprietà **WhitespaceHandling** nel lettore che ha la precedenza sull'impostazione del flag nella classe **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="7b361-108">It is the value of the **WhitespaceHandling** property on the reader that takes precedence over the setting of that flag on the **XmlDocument**.</span></span> <span data-ttu-id="7b361-109">Per altre informazioni su **XmlSignificantWhitespace**, vedere <xref:System.Xml.XmlSignificantWhitespace>.</span><span class="sxs-lookup"><span data-stu-id="7b361-109">For more information on **XmlSignificantWhitespace**, see <xref:System.Xml.XmlSignificantWhitespace>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b361-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b361-110">See also</span></span>

- [<span data-ttu-id="7b361-111">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="7b361-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
