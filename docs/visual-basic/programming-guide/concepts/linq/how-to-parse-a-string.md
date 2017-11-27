---
title: 'Procedura: analizzare una stringa (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10b80c72cae70437ff812c4b67b2532d708f1e69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="2d153-102">Procedura: analizzare una stringa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d153-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="2d153-103">In questo argomento viene illustrato come creare un albero XML in c#.</span><span class="sxs-lookup"><span data-stu-id="2d153-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d153-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2d153-104">Example</span></span>  
 <span data-ttu-id="2d153-105">È possibile analizzare una stringa in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] utilizzando il `XElement.Parse` metodo.</span><span class="sxs-lookup"><span data-stu-id="2d153-105">You can parse a string in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] by using the `XElement.Parse` method.</span></span> <span data-ttu-id="2d153-106">Tuttavia, è preferibile utilizzare valori letterali XML, come illustrato nel codice seguente, in quanto i valori letterali XML prive di stessi problemi di prestazioni di analisi XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="2d153-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="2d153-107">Usando valori letterali XML, è possibile copiare e incollare l'XML nel programma [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d153-107">By using XML literals, you can just copy and paste your XML into your [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d153-108">L'analisi di testo o il caricamento di un documento XML da un file di testo è un processo meno efficiente della costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="2d153-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="2d153-109">Se si inizializza un albero XML dal codice, il tempo CPU richiesto per la costruzione funzionale è inferiore rispetto all'analisi di testo.</span><span class="sxs-lookup"><span data-stu-id="2d153-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2d153-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d153-110">See Also</span></span>  
 [<span data-ttu-id="2d153-111">Analisi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d153-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
