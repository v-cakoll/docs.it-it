---
title: Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d9bbb14320b84a6d417c5c28026b169092de219
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45638649"
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a><span data-ttu-id="bbee2-102">Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM</span><span class="sxs-lookup"><span data-stu-id="bbee2-102">White Space and Significant White Space Handling when Loading the DOM</span></span>
<span data-ttu-id="bbee2-103">Quando si carica il documento, è possibile impostare l'opzione che consente di conservare gli spazi e creare nodi **XmlWhitespace** nell'albero del documento.</span><span class="sxs-lookup"><span data-stu-id="bbee2-103">When loading the document, you can set the option to preserve white space and create **XmlWhitespace** nodes in the document tree.</span></span> <span data-ttu-id="bbee2-104">Per creare nodi con spazi, impostare la proprietà **PreserveWhitespace** su true.</span><span class="sxs-lookup"><span data-stu-id="bbee2-104">To create white space nodes, set the **PreserveWhitespace** property to true.</span></span> <span data-ttu-id="bbee2-105">Se la proprietà è impostata su **false**, che rappresenta il valore predefinito, i nodi con spazi non vengono creati.</span><span class="sxs-lookup"><span data-stu-id="bbee2-105">If the property is set to **false**, which is the default, white space nodes are not created.</span></span> <span data-ttu-id="bbee2-106">I nodi con spazi significativi vengono sempre mantenuti e i nodi **XmlSignificantWhitespace** vengono sempre creati in memoria per rappresentare tali dati, indipendentemente dall'impostazione del flag **PreserveWhitespace**.</span><span class="sxs-lookup"><span data-stu-id="bbee2-106">Significant white spaces nodes are always preserved, and **XmlSignificantWhitespace** nodes are always created in memory to represent this data, regardless of the setting of the **PreserveWhitespace** flag.</span></span>  
  
 <span data-ttu-id="bbee2-107">Se il documento viene caricato da un lettore, l'impostazione della proprietà del flag **PreserveWhitespace** nella classe **XmlDocument** incide sulla creazione dei nodi **XmlWhitespace** solo se la proprietà **WhitespaceHandling** di **XmlTextReader** non è impostata su **WhitespaceHandling.None**.</span><span class="sxs-lookup"><span data-stu-id="bbee2-107">If the document is loaded from a reader, then setting of the **PreserveWhitespace** flag property on the **XmlDocument** class affects the creation of **XmlWhitespace** nodes only when the **WhitespaceHandling** property on the **XmlTextReader** is not set to **WhitespaceHandling.None**.</span></span> <span data-ttu-id="bbee2-108">Il valore della proprietà **WhitespaceHandling** nel lettore che ha la precedenza sull'impostazione del flag nella classe **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="bbee2-108">It is the value of the **WhitespaceHandling** property on the reader that takes precedence over the setting of that flag on the **XmlDocument**.</span></span> <span data-ttu-id="bbee2-109">Per altre informazioni su **XmlSignificantWhitespace**, vedere <xref:System.Xml.XmlSignificantWhitespace>.</span><span class="sxs-lookup"><span data-stu-id="bbee2-109">For more information on **XmlSignificantWhitespace**, see <xref:System.Xml.XmlSignificantWhitespace>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbee2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbee2-110">See also</span></span>

- [<span data-ttu-id="bbee2-111">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="bbee2-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
