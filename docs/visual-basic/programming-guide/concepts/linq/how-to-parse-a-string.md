---
title: 'Procedura: analizzare una stringa (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
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
ms.openlocfilehash: d06a0ca84650a860a7528cefafaa1c3158e5949a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="ce6a7-102">Procedura: analizzare una stringa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce6a7-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="ce6a7-103">In questo argomento viene illustrato come creare una struttura ad albero XML in c#.</span><span class="sxs-lookup"><span data-stu-id="ce6a7-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce6a7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce6a7-104">Example</span></span>  
 <span data-ttu-id="ce6a7-105">È possibile analizzare una stringa in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] utilizzando il `XElement.Parse` metodo.</span><span class="sxs-lookup"><span data-stu-id="ce6a7-105">You can parse a string in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] by using the `XElement.Parse` method.</span></span> <span data-ttu-id="ce6a7-106">Tuttavia, è preferibile utilizzare valori letterali XML, come illustrato nel codice riportato di seguito, perché i valori letterali XML non comportano gli stessi problemi di prestazioni di analisi XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="ce6a7-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="ce6a7-107">Usando valori letterali XML, è possibile copiare e incollare l'XML nel programma [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce6a7-107">By using XML literals, you can just copy and paste your XML into your [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce6a7-108">L'analisi di testo o il caricamento di un documento XML da un file di testo è un processo meno efficiente della costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="ce6a7-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="ce6a7-109">Se si inizializza un albero XML dal codice, il tempo CPU richiesto per la costruzione funzionale è inferiore rispetto all'analisi di testo.</span><span class="sxs-lookup"><span data-stu-id="ce6a7-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce6a7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce6a7-110">See Also</span></span>  
 [<span data-ttu-id="ce6a7-111">Analisi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce6a7-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
