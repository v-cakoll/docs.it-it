---
title: 'Procedura: intercettare gli errori di analisi (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 240bc9770475bdf7b6da2102bd8b552a0991eea6
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-catch-parsing-errors-c"></a><span data-ttu-id="87c05-102">Procedura: intercettare gli errori di analisi (C#)</span><span class="sxs-lookup"><span data-stu-id="87c05-102">How to: Catch Parsing Errors (C#)</span></span>
<span data-ttu-id="87c05-103">In questo argomento viene illustrato come rilevare XML non corretto o non valido.</span><span class="sxs-lookup"><span data-stu-id="87c05-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="87c05-104"> viene implementato usando <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="87c05-104"> is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="87c05-105">Se a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] viene passato XML non corretto o non valido, la classe <xref:System.Xml.XmlReader> sottostante genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="87c05-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="87c05-106">I vari metodi che analizzano il codice XML, ad esempio <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, non intercettano l'eccezione, che può quindi essere intercettata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87c05-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87c05-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="87c05-107">Example</span></span>  
 <span data-ttu-id="87c05-108">Nel codice seguente si tenta di analizzare XML non valido:</span><span class="sxs-lookup"><span data-stu-id="87c05-108">The following code tries to parse invalid XML:</span></span>  
  
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
  
 <span data-ttu-id="87c05-109">Quando viene eseguito, questo codice genera la seguente eccezione:</span><span class="sxs-lookup"><span data-stu-id="87c05-109">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="87c05-110">Per informazioni sulle eccezioni che si può prevedere vengano generate dai metodi <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> e <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, vedere la documentazione relativa a <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="87c05-110">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c05-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87c05-111">See Also</span></span>  
 [<span data-ttu-id="87c05-112">Analisi di codice XML (C#)</span><span class="sxs-lookup"><span data-stu-id="87c05-112">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)

