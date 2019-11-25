---
title: Modifica delle dichiarazioni dello spazio dei nomi in un documento XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5457eab1f34eb3e7424d508509f5dd6a42ffb51f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976942"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Modifica delle dichiarazioni dello spazio dei nomi in un documento XML
Le dichiarazioni dello spazio dei nomi e gli attributi **xmlns** vengono esposti da **XmlDocument** come parte del modello a oggetti del documento e archiviati in **XmlDocument**, perché il documento mantenga la posizione degli attributi quando viene salvato. La modifica di questi attributi non ha effetto sulle proprietà **Name**, **NamespaceURI** e **Prefix** degli altri nodi già presenti nell'albero. Se ad esempio si carica il documento seguente, l'elemento `test` ha **NamespaceURI** `123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 Se si rimuove l'attributo `xmlns` nel modo seguente, l'elemento `test` ha ancora il **NamespaceURI** `123`.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Analogamente, se si aggiunge un attributo `xmlns` diverso all'elemento `doc` nel seguente modo, l'elemento `test` ha ancora il **NamespaceURI** `123`.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 La modifica degli attributi `xmlns` non avrà quindi alcun effetto fino a quando l'oggetto **XmlDocument** non verrà salvato e ricaricato.  
  
## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
