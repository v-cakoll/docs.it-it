---
title: Modifica delle proprietà del prefisso dello spazio dei nomi
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
ms.openlocfilehash: e6b811d58ef9d98c51e9a45a46a1965c4fa12b55
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711116"
---
# <a name="changing-namespace-prefix-properties"></a><span data-ttu-id="276b5-102">Modifica delle proprietà del prefisso dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="276b5-102">Changing Namespace Prefix Properties</span></span>
<span data-ttu-id="276b5-103">La classe **XmlNode** consente di modificare il prefisso dello spazio dei nomi associato a un determinato nodo.</span><span class="sxs-lookup"><span data-stu-id="276b5-103">The **XmlNode** class allows you to change the namespace prefix associated with a given node.</span></span> <span data-ttu-id="276b5-104">Nel codice seguente, ad esempio, viene mostrata la modifica del prefisso di un elemento.</span><span class="sxs-lookup"><span data-stu-id="276b5-104">For example, the following code shows the prefix of an element being changed.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="276b5-105">**Output**</span><span class="sxs-lookup"><span data-stu-id="276b5-105">**Output**</span></span>  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 <span data-ttu-id="276b5-106">La modifica del prefisso di un nodo non comporta cambiamenti dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="276b5-106">Changing the prefix of a node does not change its namespace.</span></span> <span data-ttu-id="276b5-107">Lo spazio dei nomi può essere impostato solo al momento della creazione del nodo.</span><span class="sxs-lookup"><span data-stu-id="276b5-107">The namespace can only be set when the node is created.</span></span> <span data-ttu-id="276b5-108">Quando si mantiene fisso l'albero, i nuovi attributi dello spazio dei nomi possono essere mantenuti fissi per soddisfare il prefisso impostato.</span><span class="sxs-lookup"><span data-stu-id="276b5-108">When you persist the tree, new namespace attributes may be persisted out to satisfy the prefix you set.</span></span> <span data-ttu-id="276b5-109">Se non è possibile creare il nuovo spazio dei nomi, il prefisso viene modificato in modo che il nodo conservi il nome locale e lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="276b5-109">If the new namespace cannot be created, then the prefix is changed so the node preserves its local name and namespace.</span></span> <span data-ttu-id="276b5-110">Nell'esempio seguente viene illustrato come aggiungere un attributo dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="276b5-110">The following example shows a namespace attribute being added.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="276b5-111">**Output**</span><span class="sxs-lookup"><span data-stu-id="276b5-111">**Output**</span></span>  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 <span data-ttu-id="276b5-112">Poiché l'albero è stato reso permanente in una stringa in seguito alla chiamata a **doc.InnerXml**, l'attributo `xmlns:a='123'` è stato aggiunto per mantenere lo spazio dei nomi dell'elemento `test`.</span><span class="sxs-lookup"><span data-stu-id="276b5-112">When the tree was persisted to a string as a result of the call to **doc.InnerXml**, the `xmlns:a='123'` attribute was added to preserve the namespace of the `test` element.</span></span> <span data-ttu-id="276b5-113">Era `'123'`, ed è rimasto `'123'`.</span><span class="sxs-lookup"><span data-stu-id="276b5-113">It was `'123'`, and it remained `'123'`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="276b5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="276b5-114">See also</span></span>

- [<span data-ttu-id="276b5-115">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="276b5-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
