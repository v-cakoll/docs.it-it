---
title: 'Procedura: Analizzare una stringa (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 815e94b3b41c2c0cc1d18d598307ab292919bea4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827302"
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="3d418-102">Procedura: Analizzare una stringa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d418-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="3d418-103">In questo argomento viene illustrato come creare un albero XML in C#.</span><span class="sxs-lookup"><span data-stu-id="3d418-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d418-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d418-104">Example</span></span>  
 <span data-ttu-id="3d418-105">È possibile analizzare una stringa in Visual Basic usando il `XElement.Parse` (metodo).</span><span class="sxs-lookup"><span data-stu-id="3d418-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="3d418-106">Tuttavia, è più efficiente usare valori letterali XML, come illustrato nel codice seguente, perché i valori letterali XML non sono soggetti a stessi problemi di prestazioni come l'analisi XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="3d418-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="3d418-107">Usando i valori letterali XML, è possibile solo copiare e incollare nel codice XML nel programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3d418-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d418-108">L'analisi di testo o il caricamento di un documento XML da un file di testo è un processo meno efficiente della costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="3d418-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="3d418-109">Se si inizializza un albero XML dal codice, il tempo CPU richiesto per la costruzione funzionale è inferiore rispetto all'analisi di testo.</span><span class="sxs-lookup"><span data-stu-id="3d418-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d418-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d418-110">See also</span></span>

- [<span data-ttu-id="3d418-111">Analisi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d418-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
