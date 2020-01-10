---
title: Modifica delle dichiarazioni dello spazio dei nomi in un documento XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
ms.openlocfilehash: b8aa670764deb8e77cfb67fd16dbcf8b1cc9b4c0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711129"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="f747f-102">Modifica delle dichiarazioni dello spazio dei nomi in un documento XML</span><span class="sxs-lookup"><span data-stu-id="f747f-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="f747f-103">Le dichiarazioni dello spazio dei nomi e gli attributi **xmlns** vengono esposti da **XmlDocument** come parte del modello a oggetti del documento</span><span class="sxs-lookup"><span data-stu-id="f747f-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="f747f-104">e archiviati in **XmlDocument**, perché il documento mantenga la posizione degli attributi quando viene salvato.</span><span class="sxs-lookup"><span data-stu-id="f747f-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="f747f-105">La modifica di questi attributi non ha effetto sulle proprietà **Name**, **NamespaceURI** e **Prefix** degli altri nodi già presenti nell'albero.</span><span class="sxs-lookup"><span data-stu-id="f747f-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="f747f-106">Se ad esempio si carica il documento seguente, l'elemento `test` avrà il **NamespaceURI** `123.`</span><span class="sxs-lookup"><span data-stu-id="f747f-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="f747f-107">Se si rimuove l'attributo `xmlns` nel modo seguente, l'elemento `test` ha ancora il **NamespaceURI**`123`.</span><span class="sxs-lookup"><span data-stu-id="f747f-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="f747f-108">Analogamente, se si aggiunge un attributo `xmlns` diverso all'elemento `doc`, come indicato di seguito, l'elemento `test` avrà ancora `123`**namespaceURI** .</span><span class="sxs-lookup"><span data-stu-id="f747f-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="f747f-109">La modifica degli attributi `xmlns` non avrà quindi alcun effetto fino a quando l'oggetto **XmlDocument** non verrà salvato e ricaricato.</span><span class="sxs-lookup"><span data-stu-id="f747f-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f747f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f747f-110">See also</span></span>

- [<span data-ttu-id="f747f-111">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="f747f-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
