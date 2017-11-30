---
title: Conversione dei tipi di dati XML
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
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2f5f5d27b3d21ff12f5eea7613e80e73c5b6597
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-of-xml-data-types"></a>Conversione dei tipi di dati XML
La maggior parte dei metodi trovato un **XmlConvert** utilizzata per convertire i dati tra le stringhe e i formati fortemente tipizzata. I metodi sono indipendenti dalle impostazioni locali, il che significa che le impostazioni locali non vengono prese in considerazione al momento della conversione.  
  
## <a name="reading-string-as-types"></a>Lettura delle stringhe come tipi  
 L'esempio seguente legge una stringa e la converte in un **DateTime** tipo.  
  
 Dato l'input XML seguente:  
  
 **Input**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 Questo codice la stringa viene convertita la **DateTime** formato:  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a>Scrittura delle stringhe come tipi  
 Nell'esempio seguente legge un **Int32** e lo converte in una stringa.  
  
 Dato l'input XML seguente:  
  
 **Input**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 Questo codice converte il **Int32** in un **stringa**:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Conversione di stringhe in tipi di dati .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [Conversione di tipi .NET Framework in stringhe](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
