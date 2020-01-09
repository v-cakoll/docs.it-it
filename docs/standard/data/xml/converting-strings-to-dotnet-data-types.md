---
title: Conversione delle stringhe in tipi di dati di .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
ms.openlocfilehash: ac7e1b68f3f43a0c84c7330666825207e5b90004
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711051"
---
# <a name="converting-strings-to-net-framework-data-types"></a>Conversione delle stringhe in tipi di dati di .NET Framework
Per convertire una stringa in un tipo di dati di .NET Framework, usare il metodo **XmlConvert** che soddisfa i requisiti dell'applicazione. Per un elenco di tutti i metodi di conversione disponibili nella classe **XmlConvert**, vedere <xref:System.Xml.XmlConvert>.  
  
 La stringa restituita dal metodo **ToString** è una versione in formato stringa dei dati passati. Esistono inoltre diversi tipi .NET Framework che consentono di eseguire la conversione usando la classe **XmlConvert**, ma che non consentono l'uso dei metodi della classe **System.Convert**. La classe **XmlConvert** è conforme alla specifica dei tipi di dati XML Schema (XSD) e ha un tipo di dati a cui è possibile eseguire il mapping di **XmlConvert**.  
  
 Nella tabella seguente sono elencati i tipi di dati di .NET Framework e i tipi di stringa che vengono restituiti dal mapping dei tipi di dati XML Schema (XSD). I tipi di .NET Framework non possono essere elaborati con **System.Convert**.  
  
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
> Se viene eseguita la conversione in una stringa di uno dei tipi di .NET Framework elencati nella tabella usando il metodo **ToString**, la stringa restituita non corrisponderà al tipo di base, ma al tipo di stringa XML Schema (XSD).  
  
 I tipi di valore **DateTime** e **TimeSpan** sono diversi perché **DateTime** rappresenta un istante nel tempo, mentre **TimeSpan** rappresenta un intervallo di tempo. I formati **DateTime** e **TimeSpan** sono definiti nella specifica dei tipi di dati di XML Schema (XSD). Ad esempio:  
  
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
  
 Se tuttavia si converte una stringa in **Boolean**, **Single** o **Double**, il tipo di .NET Framework restituito non corrisponde al tipo restituito quando si usa la classe **System.Convert**.  
  
## <a name="string-to-boolean"></a>Stringa in Boolean  
 Nella tabella seguente viene illustrato quale tipo viene generato per le stringhe di input fornite, quando si converte una stringa in **Boolean** usando il metodo **ToBoolean**.  
  
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
  
 Entrambi possono essere interpretati correttamente dal codice seguente e **bvalue** corrisponde a **System.Boolean.True**:  
  
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
 Nella tabella seguente viene illustrato quale tipo viene generato per le stringhe di input fornite, quando si converte una stringa in **Single** usando il metodo **ToSingle**.  
  
|Parametro di input della stringa valido|Tipo di output di .NET Framework|  
|----------------------------------|--------------------------------|  
|"INF"|Single.PositiveInfinity|  
|"-INF"|Single.NegativeInfinity|  
  
## <a name="string-to-double"></a>Stringa in Double  
 Nella tabella seguente viene illustrato quale tipo viene generato per le stringhe di input fornite, quando si converte una stringa in **Single** usando il metodo **ToDouble**.  
  
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

- [Conversione dei tipi di dati XML](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [Conversione dei tipi di .NET Framework in stringhe](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
