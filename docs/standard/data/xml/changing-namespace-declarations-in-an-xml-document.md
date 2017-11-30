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
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Modifica delle dichiarazioni dello spazio dei nomi in un documento XML
Il **XmlDocument** espone le dichiarazioni dello spazio dei nomi e **xmlns** attributi come parte del modello a oggetti documento. Questi elementi sono archiviati nel **XmlDocument**, pertanto quando si salva il documento, è possibile mantenere il percorso di questi attributi. La modifica di questi attributi non ha effetto sul **nome**, **NamespaceURI**, e **prefisso** proprietà degli altri nodi già presenti nell'albero. Se si carica il documento seguente, ad esempio il `test` elemento ha **NamespaceURI**`123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 Se si rimuove il `xmlns` attributo come indicato di seguito, quindi il `test` elemento ha ancora il **NamespaceURI** di `123`.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Analogamente, se si aggiunge un altro `xmlns` attributo il `doc` elemento come indicato di seguito, quindi il `test` elemento ha ancora **NamespaceURI** `123`.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Pertanto, la modifica `xmlns` attributi non avranno effetto fino a quando non verrà salvato e ricaricato il **XmlDocument** oggetto.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
