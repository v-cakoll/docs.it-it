---
title: Conversione delle stringhe in tipi di dati di .NET Framework
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
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce594234e601cd8feb4723bbc383db9e3ed40522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="converting-strings-to-net-framework-data-types"></a>Conversione delle stringhe in tipi di dati di .NET Framework
Se si desidera convertire una stringa in un tipo di dati .NET Framework, usare il **XmlConvert** metodo che soddisfa i requisiti dell'applicazione. Per un elenco di tutti i metodi di conversione disponibili nel **XmlConvert** classe, vedere <xref:System.Xml.XmlConvert>.  
  
 La stringa restituita dal **ToString** metodo è una versione di dati che viene passati nella stringa. Inoltre, esistono diversi tipi di .NET Framework che convertono utilizzando il **XmlConvert** classe ma non usano i metodi nel **Convert** classe. Il **XmlConvert** classe segue la specifica di tipo di dati XML Schema (XSD) e un tipo di dati sono di tipo che il **XmlConvert** può eseguire il mapping a.  
  
 Nella tabella seguente sono elencati i tipi di dati di .NET Framework e i tipi di stringa che vengono restituiti dal mapping dei tipi di dati XML Schema (XSD). Questi tipi .NET Framework non possono essere elaborati con **Convert**.  
  
|Tipo .NET Framework|Stringa restituita|  
|-------------------------|---------------------|  
|Boolean|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|Il formato è "yyyy-MM-ddTHH:mm:sszzzzzz" e i relativi subset.|  
|TimeSpan|Il formato è PnYnMnTnHnMnS, ovvero `P2Y10M15DT10H30M20S` corrisponde a una durata di 2 anni, 10 mesi, 15 giorni, 10 ore, 30 minuti e 20 secondi.|  
  
> [!NOTE]
>  Se la conversione di uno dei tipi di .NET Framework elencati nella tabella in una stringa tramite il **ToString** metodo, la stringa restituita non è il tipo di base, ma il tipo di stringa di XML Schema (XSD).  
  
 Il **DateTime** e **Timespan** tipo valore diverso in cui un **DateTime** rappresenta un istante di tempo, mentre un **TimeSpan** rappresenta un intervallo di tempo. Il **DateTime** e **Timespan** formati vengono specificati nella specifica di tipi di dati XML Schema (XSD). Ad esempio:  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 **Output**  
  
 `<Date>2001-08-04T00:00:00</Date>`.  
  
 Il codice seguente converte un numero intero in una stringa:  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 **Output**  
  
 `<Number>200</Number>`  
  
 Tuttavia, se si converte una stringa a **booleano**, **singolo**, o **doppie**, il tipo di .NET Framework restituito non è identico al tipo restituito quando si utilizza il **Convert** classe.  
  
## <a name="string-to-boolean"></a>Stringa in Boolean  
 Nella tabella seguente viene illustrato quale tipo viene generato per le stringhe di input fornite, quando si converte una stringa in **booleano** utilizzando il **ToBoolean** metodo.  
  
|Parametro di input della stringa valido|Tipo di output di .NET Framework|  
|----------------------------------|--------------------------------|  
|"true"|Boolean.True|  
|"1"|Boolean.True|  
|"false"|Boolean.False|  
|"0"|Boolean.False|  
  
 Si consideri, ad esempio, il codice XML seguente:  
  
 **Input**  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 Entrambi possono essere interpretati dal codice seguente, e **bvalue** è **correttamente**:  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a>Stringa in Single  
 Nella tabella seguente viene illustrato quale tipo viene generato per le stringhe di input fornite, quando si converte una stringa in un **singolo** utilizzando il **ToSingle** metodo.  
  
|Parametro di input della stringa valido|Tipo di output di .NET Framework|  
|----------------------------------|--------------------------------|  
|"INF"|Single.PositiveInfinity|  
|"-INF"|Single.NegativeInfinity|  
  
## <a name="string-to-double"></a>Stringa in Double  
 Nella tabella seguente viene illustrato quale tipo viene generato per le stringhe di input fornite, quando si converte una stringa in un **singolo** utilizzando il **ToDouble** metodo.  
  
|Parametro di input della stringa valido|Tipo di output di .NET Framework|  
|----------------------------------|--------------------------------|  
|"INF"|Double.PositiveInfinity|  
|"-INF"|Double.NegativeInfinity|  
  
 Il codice seguente scrive `<Infinity>INF</Infinity>`:  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Conversione di tipi di dati XML](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [Conversione di tipi .NET Framework in stringhe](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
