---
title: 'Procedura: Analizzare una stringa'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 0a9076fc516bb8e6bc74732ca252fabfeda43d53
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398012"
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="3b12f-102">Procedura: analizzare una stringa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b12f-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="3b12f-103">In questo argomento viene illustrato come creare un albero XML in C#.</span><span class="sxs-lookup"><span data-stu-id="3b12f-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b12f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3b12f-104">Example</span></span>  
 <span data-ttu-id="3b12f-105">È possibile analizzare una stringa in Visual Basic usando il `XElement.Parse` metodo.</span><span class="sxs-lookup"><span data-stu-id="3b12f-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="3b12f-106">Tuttavia, è più utile usare valori letterali XML, come illustrato nel codice seguente, perché i valori letterali XML non comportano gli stessi problemi di prestazioni dell'analisi XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="3b12f-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="3b12f-107">Usando i valori letterali XML, è possibile copiare e incollare il codice XML nel programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3b12f-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b12f-108">L'analisi di testo o il caricamento di un documento XML da un file di testo è un processo meno efficiente della costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="3b12f-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="3b12f-109">Se si inizializza un albero XML dal codice, il tempo CPU richiesto per la costruzione funzionale è inferiore rispetto all'analisi di testo.</span><span class="sxs-lookup"><span data-stu-id="3b12f-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b12f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b12f-110">See also</span></span>

- [<span data-ttu-id="3b12f-111">Analisi di XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b12f-111">Parsing XML (Visual Basic)</span></span>](parsing-xml.md)
