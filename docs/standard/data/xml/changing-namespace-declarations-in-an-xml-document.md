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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6db78e689b8529ef62a3b42c2cefb6a5b3d3f02f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="4f960-102">Modifica delle dichiarazioni dello spazio dei nomi in un documento XML</span><span class="sxs-lookup"><span data-stu-id="4f960-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="4f960-103">Le dichiarazioni dello spazio dei nomi e gli attributi **xmlns** vengono esposti da **XmlDocument** come parte del modello a oggetti del documento</span><span class="sxs-lookup"><span data-stu-id="4f960-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="4f960-104">e archiviati in **XmlDocument**, perché il documento mantenga la posizione degli attributi quando viene salvato.</span><span class="sxs-lookup"><span data-stu-id="4f960-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="4f960-105">La modifica di questi attributi non ha effetto sulle proprietà **Name**, **NamespaceURI** e **Prefix** degli altri nodi già presenti nell'albero.</span><span class="sxs-lookup"><span data-stu-id="4f960-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="4f960-106">Se ad esempio si carica il documento seguente, l'elemento `test` ha **NamespaceURI** `123.`</span><span class="sxs-lookup"><span data-stu-id="4f960-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="4f960-107">Se si rimuove l'attributo `xmlns` nel modo seguente, l'elemento `test` ha ancora il **NamespaceURI** `123`.</span><span class="sxs-lookup"><span data-stu-id="4f960-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="4f960-108">Analogamente, se si aggiunge un attributo `xmlns` diverso all'elemento `doc` nel seguente modo, l'elemento `test` ha ancora il **NamespaceURI** `123`.</span><span class="sxs-lookup"><span data-stu-id="4f960-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="4f960-109">La modifica degli attributi `xmlns` non avrà quindi alcun effetto fino a quando l'oggetto **XmlDocument** non verrà salvato e ricaricato.</span><span class="sxs-lookup"><span data-stu-id="4f960-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f960-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f960-110">See Also</span></span>  
 [<span data-ttu-id="4f960-111">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="4f960-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
