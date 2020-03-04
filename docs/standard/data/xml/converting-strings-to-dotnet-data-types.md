---
title: Conversione delle stringhe in tipi di dati di .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
ms.openlocfilehash: e54990785cafd6061c6d53c13af6476a4b46e20e
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160352"
---
# <a name="converting-strings-to-net-framework-data-types"></a><span data-ttu-id="7d760-102">Conversione delle stringhe in tipi di dati di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7d760-102">Converting Strings to .NET Framework Data Types</span></span>
<span data-ttu-id="7d760-103">Per convertire una stringa in un tipo di dati di .NET Framework, usare il metodo **XmlConvert** che soddisfa i requisiti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d760-103">If you want to convert a string to a .NET Framework data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="7d760-104">Per un elenco di tutti i metodi di conversione disponibili nella classe **XmlConvert**, vedere <xref:System.Xml.XmlConvert>.</span><span class="sxs-lookup"><span data-stu-id="7d760-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="7d760-105">La stringa restituita dal metodo **ToString** è una versione in formato stringa dei dati passati.</span><span class="sxs-lookup"><span data-stu-id="7d760-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="7d760-106">Esistono inoltre diversi tipi .NET Framework che consentono di eseguire la conversione usando la classe **XmlConvert**, ma che non consentono l'uso dei metodi della classe **System.Convert**.</span><span class="sxs-lookup"><span data-stu-id="7d760-106">Additionally, there are several .NET Framework types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="7d760-107">La classe **XmlConvert** è conforme alla specifica dei tipi di dati XML Schema (XSD) e ha un tipo di dati a cui è possibile eseguire il mapping di **XmlConvert**.</span><span class="sxs-lookup"><span data-stu-id="7d760-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="7d760-108">Nella tabella seguente sono elencati i tipi di dati di .NET Framework e i tipi di stringa che vengono restituiti dal mapping dei tipi di dati XML Schema (XSD).</span><span class="sxs-lookup"><span data-stu-id="7d760-108">The following table lists .NET Framework data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="7d760-109">I tipi di .NET Framework non possono essere elaborati con **System.Convert**.</span><span class="sxs-lookup"><span data-stu-id="7d760-109">These .NET Framework types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="7d760-110">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7d760-110">.NET Framework type</span></span>|<span data-ttu-id="7d760-111">Stringa restituita</span><span class="sxs-lookup"><span data-stu-id="7d760-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="7d760-112">Boolean</span><span class="sxs-lookup"><span data-stu-id="7d760-112">Boolean</span></span>|<span data-ttu-id="7d760-113">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="7d760-113">"true", "false"</span></span>|  
|<span data-ttu-id="7d760-114">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="7d760-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="7d760-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="7d760-115">"INF"</span></span>|  
|<span data-ttu-id="7d760-116">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="7d760-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="7d760-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="7d760-117">"-INF"</span></span>|  
|<span data-ttu-id="7d760-118">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="7d760-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="7d760-119">"INF"</span><span class="sxs-lookup"><span data-stu-id="7d760-119">"INF"</span></span>|  
|<span data-ttu-id="7d760-120">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="7d760-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="7d760-121">"-INF"</span><span class="sxs-lookup"><span data-stu-id="7d760-121">"-INF"</span></span>|  
|<span data-ttu-id="7d760-122">Datetime</span><span class="sxs-lookup"><span data-stu-id="7d760-122">DateTime</span></span>|<span data-ttu-id="7d760-123">Il formato è "yyyy-MM-ddTHH:mm:sszzzzzz" e i relativi subset.</span><span class="sxs-lookup"><span data-stu-id="7d760-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="7d760-124">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="7d760-124">Timespan</span></span>|<span data-ttu-id="7d760-125">Il formato è PnYnMnTnHnMnS, ovvero `P2Y10M15DT10H30M20S` corrisponde a una durata di 2 anni, 10 mesi, 15 giorni, 10 ore, 30 minuti e 20 secondi.</span><span class="sxs-lookup"><span data-stu-id="7d760-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7d760-126">Se viene eseguita la conversione in una stringa di uno dei tipi di .NET Framework elencati nella tabella usando il metodo **ToString**, la stringa restituita non corrisponderà al tipo di base, ma al tipo di stringa XML Schema (XSD).</span><span class="sxs-lookup"><span data-stu-id="7d760-126">If converting any of the .NET Framework types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="7d760-127">I tipi di valore **DateTime** e **TimeSpan** sono diversi perché **DateTime** rappresenta un istante nel tempo, mentre **TimeSpan** rappresenta un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7d760-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="7d760-128">I formati **DateTime** e **TimeSpan** sono definiti nella specifica dei tipi di dati di XML Schema (XSD).</span><span class="sxs-lookup"><span data-stu-id="7d760-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="7d760-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7d760-129">For example:</span></span>  
  
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
  
 <span data-ttu-id="7d760-130">**Output**</span><span class="sxs-lookup"><span data-stu-id="7d760-130">**Output**</span></span>  
  
 <span data-ttu-id="7d760-131">`<Date>2001-08-04T00:00:00</Date>`.</span><span class="sxs-lookup"><span data-stu-id="7d760-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="7d760-132">Il codice seguente converte un numero intero in una stringa:</span><span class="sxs-lookup"><span data-stu-id="7d760-132">The following code converts an integer to a string:</span></span>  
  
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
  
 <span data-ttu-id="7d760-133">**Output**</span><span class="sxs-lookup"><span data-stu-id="7d760-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="7d760-134">Se tuttavia si converte una stringa in **Boolean**, **Single** o **Double**, il tipo di .NET Framework restituito non corrisponde al tipo restituito quando si usa la classe **System.Convert**.</span><span class="sxs-lookup"><span data-stu-id="7d760-134">However, if you are converting a string to **Boolean**, **Single**, or **Double**, the .NET Framework type that is returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="7d760-135">Stringa in Boolean</span><span class="sxs-lookup"><span data-stu-id="7d760-135">String to Boolean</span></span>  
 <span data-ttu-id="7d760-136">Nella tabella seguente viene illustrato quale tipo viene generato per le stringhe di input fornite, quando si converte una stringa in **Boolean** usando il metodo **ToBoolean**.</span><span class="sxs-lookup"><span data-stu-id="7d760-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="7d760-137">Parametro di input della stringa valido</span><span class="sxs-lookup"><span data-stu-id="7d760-137">Valid string input parameter</span></span>|<span data-ttu-id="7d760-138">Tipo di output di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7d760-138">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="7d760-139">"true"</span><span class="sxs-lookup"><span data-stu-id="7d760-139">"true"</span></span>|<span data-ttu-id="7d760-140">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="7d760-140">Boolean.True</span></span>|  
|<span data-ttu-id="7d760-141">"1"</span><span class="sxs-lookup"><span data-stu-id="7d760-141">"1"</span></span>|<span data-ttu-id="7d760-142">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="7d760-142">Boolean.True</span></span>|  
|<span data-ttu-id="7d760-143">"false"</span><span class="sxs-lookup"><span data-stu-id="7d760-143">"false"</span></span>|<span data-ttu-id="7d760-144">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="7d760-144">Boolean.False</span></span>|  
|<span data-ttu-id="7d760-145">"0"</span><span class="sxs-lookup"><span data-stu-id="7d760-145">"0"</span></span>|<span data-ttu-id="7d760-146">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="7d760-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="7d760-147">Si consideri, ad esempio, il codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="7d760-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="7d760-148">**Input**</span><span class="sxs-lookup"><span data-stu-id="7d760-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>
```  
  
 <span data-ttu-id="7d760-149">Entrambi possono essere interpretati correttamente dal codice seguente e **bvalue** corrisponde a **System.Boolean.True**:</span><span class="sxs-lookup"><span data-stu-id="7d760-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True**:</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="7d760-150">Stringa in Single</span><span class="sxs-lookup"><span data-stu-id="7d760-150">String to Single</span></span>  
 <span data-ttu-id="7d760-151">Nella tabella seguente viene illustrato quale tipo viene generato per le stringhe di input fornite, quando si converte una stringa in **Single** usando il metodo **ToSingle**.</span><span class="sxs-lookup"><span data-stu-id="7d760-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="7d760-152">Parametro di input della stringa valido</span><span class="sxs-lookup"><span data-stu-id="7d760-152">Valid string input parameter</span></span>|<span data-ttu-id="7d760-153">Tipo di output di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7d760-153">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="7d760-154">"INF"</span><span class="sxs-lookup"><span data-stu-id="7d760-154">"INF"</span></span>|<span data-ttu-id="7d760-155">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="7d760-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="7d760-156">"-INF"</span><span class="sxs-lookup"><span data-stu-id="7d760-156">"-INF"</span></span>|<span data-ttu-id="7d760-157">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="7d760-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="7d760-158">Stringa in Double</span><span class="sxs-lookup"><span data-stu-id="7d760-158">String to Double</span></span>  
 <span data-ttu-id="7d760-159">Nella tabella seguente viene illustrato quale tipo viene generato per le stringhe di input fornite, quando si converte una stringa in **Single** usando il metodo **ToDouble**.</span><span class="sxs-lookup"><span data-stu-id="7d760-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="7d760-160">Parametro di input della stringa valido</span><span class="sxs-lookup"><span data-stu-id="7d760-160">Valid string input parameter</span></span>|<span data-ttu-id="7d760-161">Tipo di output di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7d760-161">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="7d760-162">"INF"</span><span class="sxs-lookup"><span data-stu-id="7d760-162">"INF"</span></span>|<span data-ttu-id="7d760-163">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="7d760-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="7d760-164">"-INF"</span><span class="sxs-lookup"><span data-stu-id="7d760-164">"-INF"</span></span>|<span data-ttu-id="7d760-165">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="7d760-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="7d760-166">Il codice seguente scrive `<Infinity>INF</Infinity>`:</span><span class="sxs-lookup"><span data-stu-id="7d760-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d760-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d760-167">See also</span></span>

- [<span data-ttu-id="7d760-168">Conversione dei tipi di dati XML</span><span class="sxs-lookup"><span data-stu-id="7d760-168">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [<span data-ttu-id="7d760-169">Conversione dei tipi di .NET Framework in stringhe</span><span class="sxs-lookup"><span data-stu-id="7d760-169">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
