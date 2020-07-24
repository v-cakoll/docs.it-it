---
title: Come intercettare gli errori di analisi (C#)
description: Questo LINQ to XML esempio in C# rileva codice XML non valido o non valido. LINQ to XML utilizza XmlReader, che genera un'eccezione per XML non corretto o non valido.
ms.date: 07/20/2015
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
ms.openlocfilehash: 0a891097322ef6acce062ea927692b01cc425e6c
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105408"
---
# <a name="how-to-catch-parsing-errors-c"></a><span data-ttu-id="7d16b-104">Come intercettare gli errori di analisi (C#)</span><span class="sxs-lookup"><span data-stu-id="7d16b-104">How to catch parsing errors (C#)</span></span>
<span data-ttu-id="7d16b-105">In questo argomento viene illustrato come rilevare XML non corretto o non valido.</span><span class="sxs-lookup"><span data-stu-id="7d16b-105">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="7d16b-106">viene implementato usando <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="7d16b-106">is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="7d16b-107">Se a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] viene passato XML non corretto o non valido, la classe <xref:System.Xml.XmlReader> sottostante genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7d16b-107">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="7d16b-108">I vari metodi che analizzano il codice XML, ad esempio <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, non intercettano l'eccezione, che può quindi essere intercettata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d16b-108">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d16b-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d16b-109">Example</span></span>  
 <span data-ttu-id="7d16b-110">Nel codice seguente si tenta di analizzare XML non valido:</span><span class="sxs-lookup"><span data-stu-id="7d16b-110">The following code tries to parse invalid XML:</span></span>  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 <span data-ttu-id="7d16b-111">Quando viene eseguito, questo codice genera la seguente eccezione:</span><span class="sxs-lookup"><span data-stu-id="7d16b-111">When you run this code, it throws the following exception:</span></span>  
  
```console  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="7d16b-112">Per informazioni sulle eccezioni che si può prevedere vengano generate dai metodi <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> e <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, vedere la documentazione relativa a <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="7d16b-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  