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
# <a name="how-to-parse-a-string-visual-basic"></a>Procedura: analizzare una stringa (Visual Basic)
In questo argomento viene illustrato come creare un albero XML in C#.  
  
## <a name="example"></a>Esempio  
 È possibile analizzare una stringa in Visual Basic usando il `XElement.Parse` metodo. Tuttavia, è più utile usare valori letterali XML, come illustrato nel codice seguente, perché i valori letterali XML non comportano gli stessi problemi di prestazioni dell'analisi XML da una stringa.  
  
 Usando i valori letterali XML, è possibile copiare e incollare il codice XML nel programma Visual Basic.  
  
> [!NOTE]
> L'analisi di testo o il caricamento di un documento XML da un file di testo è un processo meno efficiente della costruzione funzionale. Se si inizializza un albero XML dal codice, il tempo CPU richiesto per la costruzione funzionale è inferiore rispetto all'analisi di testo.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Analisi di XML (Visual Basic)](parsing-xml.md)
