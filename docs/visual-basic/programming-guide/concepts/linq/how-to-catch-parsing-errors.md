---
title: 'Procedura: intercettare gli errori (Visual Basic) di analisi | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6065bb7656151392e4a5b7ad1078706284ba5616
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="7b214-102">Procedura: intercettare gli errori (Visual Basic) di analisi</span><span class="sxs-lookup"><span data-stu-id="7b214-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="7b214-103">In questo argomento viene illustrato come rilevare XML non corretto o non valido.</span><span class="sxs-lookup"><span data-stu-id="7b214-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="7b214-104">viene implementata utilizzando <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="7b214-104"> is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="7b214-105">Se viene passato XML non corretto o non valido per [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], sottostante <xref:System.Xml.XmlReader>classe verrà generata un'eccezione.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="7b214-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="7b214-106">I vari metodi che analizzano XML, ad esempio <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, non rilevano l'eccezione; l'eccezione può quindi essere intercettata dall'applicazione.</xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7b214-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="7b214-107">Si noti che non è possibile ottenere errori di analisi se si usano valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="7b214-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="7b214-108">Il compilatore Visual Basic intercetterà errori di XML non corretto o non valido.</span><span class="sxs-lookup"><span data-stu-id="7b214-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b214-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b214-109">Example</span></span>  
 <span data-ttu-id="7b214-110">Nel codice seguente si tenta di analizzare XML non valido:</span><span class="sxs-lookup"><span data-stu-id="7b214-110">The following code tries to parse invalid XML:</span></span>  
  
```vb  
Try  
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _  
        "    <Contact>" & vbCrLf & _  
        "        <Name>Jim Wilson</Name>" & vbCrLf & _  
        "    </Contact>" & vbCrLf & _  
        "</Contcts>")  
  
    Console.WriteLine(contacts)  
Catch e As System.Xml.XmlException  
    Console.WriteLine(e.Message)  
End Try  
```  
  
 <span data-ttu-id="7b214-111">Quando viene eseguito, questo codice genera la seguente eccezione:</span><span class="sxs-lookup"><span data-stu-id="7b214-111">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="7b214-112">Per informazioni sulle eccezioni che è possibile prevedere il <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, e <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>metodi da generare, vedere il <xref:System.Xml.XmlReader>documentazione.</xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7b214-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b214-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b214-113">See Also</span></span>  
 [<span data-ttu-id="7b214-114">Analisi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b214-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
