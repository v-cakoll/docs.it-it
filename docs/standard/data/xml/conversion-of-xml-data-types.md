---
title: Conversione dei tipi di dati XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
ms.openlocfilehash: b6e6f2c4b28e9220727bf0fe1a958a7b69111571
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202165"
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="d5b90-102">Conversione dei tipi di dati XML</span><span class="sxs-lookup"><span data-stu-id="d5b90-102">Conversion of XML Data Types</span></span>
<span data-ttu-id="d5b90-103">La maggior parte dei metodi presenti in una classe **XmlConvert** viene usata per convertire i dati tra le stringhe e i formati fortemente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="d5b90-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly typed formats.</span></span> <span data-ttu-id="d5b90-104">I metodi sono indipendenti dalle impostazioni locali,</span><span class="sxs-lookup"><span data-stu-id="d5b90-104">Methods are locale independent.</span></span> <span data-ttu-id="d5b90-105">il che significa che le impostazioni locali non vengono prese in considerazione al momento della conversione.</span><span class="sxs-lookup"><span data-stu-id="d5b90-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="d5b90-106">Lettura delle stringhe come tipi</span><span class="sxs-lookup"><span data-stu-id="d5b90-106">Reading String as types</span></span>  
 <span data-ttu-id="d5b90-107">Nell'esempio seguente viene illustrato come una stringa viene letta e convertita in un tipo **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="d5b90-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="d5b90-108">Dato l'input XML seguente:</span><span class="sxs-lookup"><span data-stu-id="d5b90-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="d5b90-109">**Input**</span><span class="sxs-lookup"><span data-stu-id="d5b90-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="d5b90-110">la stringa viene convertita dal codice nel formato **DateTime**:</span><span class="sxs-lookup"><span data-stu-id="d5b90-110">This code converts the string to the **DateTime** format:</span></span>  
  
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
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="d5b90-111">Scrittura delle stringhe come tipi</span><span class="sxs-lookup"><span data-stu-id="d5b90-111">Writing Strings as types</span></span>  
 <span data-ttu-id="d5b90-112">Nell'esempio seguente viene illustrato come un **Int32** viene letto e convertito in una stringa.</span><span class="sxs-lookup"><span data-stu-id="d5b90-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="d5b90-113">Dato l'input XML seguente:</span><span class="sxs-lookup"><span data-stu-id="d5b90-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="d5b90-114">**Input**</span><span class="sxs-lookup"><span data-stu-id="d5b90-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="d5b90-115">**Int32** viene convertito dal codice in una stringa **String**:</span><span class="sxs-lookup"><span data-stu-id="d5b90-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5b90-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5b90-116">See also</span></span>

- [<span data-ttu-id="d5b90-117">Conversione delle stringhe in tipi di dati di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d5b90-117">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
- [<span data-ttu-id="d5b90-118">Conversione dei tipi di .NET Framework in stringhe</span><span class="sxs-lookup"><span data-stu-id="d5b90-118">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
