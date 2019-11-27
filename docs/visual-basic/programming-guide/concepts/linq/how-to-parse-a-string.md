---
title: 'Procedura: analizzare una stringa'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 31bae00eb3ebf0d8e64fc657693e8c0767c4f5d4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344492"
---
# <a name="how-to-parse-a-string-visual-basic"></a>Procedura: analizzare una stringa (Visual Basic)
In questo argomento viene illustrato come creare un albero XML C#in.  
  
## <a name="example"></a>Esempio  
 È possibile analizzare una stringa in Visual Basic usando il metodo `XElement.Parse`. Tuttavia, è più efficiente usare i valori letterali XML, come illustrato nel codice seguente, perché i valori letterali XML non risentono delle stesse sanzioni delle prestazioni dell'analisi di codice XML da una stringa.  
  
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

- [Analisi di XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
