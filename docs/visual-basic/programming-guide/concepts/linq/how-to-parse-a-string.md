---
title: 'Procedura: Analizza una stringa (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: b97ce93c1018ec48649ab8b259d5f1a07109b9fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956370"
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="196c3-102">Procedura: Analizza una stringa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="196c3-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="196c3-103">In questo argomento viene illustrato come creare un albero XML C#in.</span><span class="sxs-lookup"><span data-stu-id="196c3-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="196c3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="196c3-104">Example</span></span>  
 <span data-ttu-id="196c3-105">È possibile analizzare una stringa in Visual Basic usando il `XElement.Parse` metodo.</span><span class="sxs-lookup"><span data-stu-id="196c3-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="196c3-106">Tuttavia, è più efficiente usare i valori letterali XML, come illustrato nel codice seguente, perché i valori letterali XML non risentono delle stesse sanzioni delle prestazioni dell'analisi di codice XML da una stringa.</span><span class="sxs-lookup"><span data-stu-id="196c3-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="196c3-107">Usando i valori letterali XML, è possibile copiare e incollare il codice XML nel programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="196c3-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="196c3-108">L'analisi di testo o il caricamento di un documento XML da un file di testo è un processo meno efficiente della costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="196c3-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="196c3-109">Se si inizializza un albero XML dal codice, il tempo CPU richiesto per la costruzione funzionale è inferiore rispetto all'analisi di testo.</span><span class="sxs-lookup"><span data-stu-id="196c3-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="196c3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="196c3-110">See also</span></span>

- [<span data-ttu-id="196c3-111">Analisi di XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="196c3-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
