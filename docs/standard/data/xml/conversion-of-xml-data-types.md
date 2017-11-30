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
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="6a0a1-102">Conversione dei tipi di dati XML</span><span class="sxs-lookup"><span data-stu-id="6a0a1-102">Conversion of XML Data Types</span></span>
<span data-ttu-id="6a0a1-103">La maggior parte dei metodi trovato un **XmlConvert** utilizzata per convertire i dati tra le stringhe e i formati fortemente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="6a0a1-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly-typed formats.</span></span> <span data-ttu-id="6a0a1-104">I metodi sono indipendenti dalle impostazioni locali,</span><span class="sxs-lookup"><span data-stu-id="6a0a1-104">Methods are locale independent.</span></span> <span data-ttu-id="6a0a1-105">il che significa che le impostazioni locali non vengono prese in considerazione al momento della conversione.</span><span class="sxs-lookup"><span data-stu-id="6a0a1-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="6a0a1-106">Lettura delle stringhe come tipi</span><span class="sxs-lookup"><span data-stu-id="6a0a1-106">Reading String as types</span></span>  
 <span data-ttu-id="6a0a1-107">L'esempio seguente legge una stringa e la converte in un **DateTime** tipo.</span><span class="sxs-lookup"><span data-stu-id="6a0a1-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="6a0a1-108">Dato l'input XML seguente:</span><span class="sxs-lookup"><span data-stu-id="6a0a1-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="6a0a1-109">**Input**</span><span class="sxs-lookup"><span data-stu-id="6a0a1-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="6a0a1-110">Questo codice la stringa viene convertita la **DateTime** formato:</span><span class="sxs-lookup"><span data-stu-id="6a0a1-110">This code converts the string to the **DateTime** format:</span></span>  
  
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
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="6a0a1-111">Scrittura delle stringhe come tipi</span><span class="sxs-lookup"><span data-stu-id="6a0a1-111">Writing Strings as types</span></span>  
 <span data-ttu-id="6a0a1-112">Nell'esempio seguente legge un **Int32** e lo converte in una stringa.</span><span class="sxs-lookup"><span data-stu-id="6a0a1-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="6a0a1-113">Dato l'input XML seguente:</span><span class="sxs-lookup"><span data-stu-id="6a0a1-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="6a0a1-114">**Input**</span><span class="sxs-lookup"><span data-stu-id="6a0a1-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="6a0a1-115">Questo codice converte il **Int32** in un **stringa**:</span><span class="sxs-lookup"><span data-stu-id="6a0a1-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a0a1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a0a1-116">See Also</span></span>  
 [<span data-ttu-id="6a0a1-117">Conversione di stringhe in tipi di dati .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6a0a1-117">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [<span data-ttu-id="6a0a1-118">Conversione di tipi .NET Framework in stringhe</span><span class="sxs-lookup"><span data-stu-id="6a0a1-118">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
