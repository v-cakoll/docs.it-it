---
title: Modifica delle proprietà del prefisso dello spazio dei nomi
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
ms.openlocfilehash: b1df520d00d3a98b2e518092d4eff51b5d0b7741
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78158025"
---
# <a name="changing-namespace-prefix-properties"></a>Modifica delle proprietà del prefisso dello spazio dei nomi
La classe **XmlNode** consente di modificare il prefisso dello spazio dei nomi associato a un determinato nodo. Nel codice seguente, ad esempio, viene mostrata la modifica del prefisso di un elemento.  
  
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
  
 **Output**  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 La modifica del prefisso di un nodo non comporta cambiamenti dello spazio dei nomi. Lo spazio dei nomi può essere impostato solo al momento della creazione del nodo. Quando si mantiene fisso l'albero, i nuovi attributi dello spazio dei nomi possono essere mantenuti fissi per soddisfare il prefisso impostato. Se non è possibile creare il nuovo spazio dei nomi, il prefisso viene modificato in modo che il nodo conservi il nome locale e lo spazio dei nomi. Nell'esempio seguente viene illustrato come aggiungere un attributo dello spazio dei nomi.  
  
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
  
 **Output**  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 Poiché l'albero è stato reso permanente in una stringa in seguito alla chiamata a **doc.InnerXml**, l'attributo `xmlns:a='123'` è stato aggiunto per mantenere lo spazio dei nomi dell'elemento `test`. Era `'123'`, ed è rimasto `'123'`.  
  
## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
