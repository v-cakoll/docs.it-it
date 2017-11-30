---
title: Modifica delle dichiarazioni dello spazio dei nomi in un documento XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 627882efcbc41310ee177cba984e4add5b07bd15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="538b3-102">Modifica delle dichiarazioni dello spazio dei nomi in un documento XML</span><span class="sxs-lookup"><span data-stu-id="538b3-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="538b3-103">Il **XmlDocument** espone le dichiarazioni dello spazio dei nomi e **xmlns** attributi come parte del modello a oggetti documento.</span><span class="sxs-lookup"><span data-stu-id="538b3-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="538b3-104">Questi elementi sono archiviati nel **XmlDocument**, pertanto quando si salva il documento, è possibile mantenere il percorso di questi attributi.</span><span class="sxs-lookup"><span data-stu-id="538b3-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="538b3-105">La modifica di questi attributi non ha effetto sul **nome**, **NamespaceURI**, e **prefisso** proprietà degli altri nodi già presenti nell'albero.</span><span class="sxs-lookup"><span data-stu-id="538b3-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="538b3-106">Se si carica il documento seguente, ad esempio il `test` elemento ha **NamespaceURI**`123.`</span><span class="sxs-lookup"><span data-stu-id="538b3-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="538b3-107">Se si rimuove il `xmlns` attributo come indicato di seguito, quindi il `test` elemento ha ancora il **NamespaceURI** di `123`.</span><span class="sxs-lookup"><span data-stu-id="538b3-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="538b3-108">Analogamente, se si aggiunge un altro `xmlns` attributo il `doc` elemento come indicato di seguito, quindi il `test` elemento ha ancora **NamespaceURI** `123`.</span><span class="sxs-lookup"><span data-stu-id="538b3-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="538b3-109">Pertanto, la modifica `xmlns` attributi non avranno effetto fino a quando non verrà salvato e ricaricato il **XmlDocument** oggetto.</span><span class="sxs-lookup"><span data-stu-id="538b3-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="538b3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="538b3-110">See Also</span></span>  
 [<span data-ttu-id="538b3-111">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="538b3-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
