---
title: Trasformazione funzionale di XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: fdbe5b91-f457-4b4e-a11b-def4bdd77bab
ms.openlocfilehash: 06803feb0fe23ae4afe2237b64bf920f6e229060
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190476"
---
# <a name="functional-transformation-of-xml-visual-basic"></a>Trasformazione funzionale di XML (Visual Basic)
In questo argomento viene illustrato l'approccio alla modifica di documenti XML basato sulla trasformazione funzionale pure. Tale approccio viene quindi messo a confronto con un approccio procedurale.  
  
## <a name="modifying-an-xml-document"></a>Modifica di un documento XML  
 Una delle attività più comuni richieste a un programmatore XML è la trasformazione di codice XML da una forma a un'altra. Per forma di un documento XML si intende la struttura del documento, che include:  
  
-   La gerarchia espressa dal documento.  
  
-   I nomi di elementi e attributi.  
  
-   I tipi di dati di elementi e attributi.  
  
 In generale, l'approccio più efficace alla trasformazione di codice XML da una forma a un'altra è quello basato sulla trasformazione funzionale pure. In questo approccio l'attività principale del programmatore consiste nel creare una trasformazione che viene applicata all'intero documento XML (o a uno o più nodi definiti rigidamente). La trasformazione funzionale è decisamente la più facile da codificare (una volta che il programmatore ha familiarizzato con l'approccio), consente di ottenere codice più conservabile ed offre spesso maggior compattezza rispetto agli approcci alternativi.  
  
### <a name="xml-functional-transformational-technologies"></a>Tecnologie per la trasformazione funzionale XML  
 Microsoft offre due tecnologie per la trasformazione funzionale utilizzabili con i documenti XML, ovvero XSLT e LINQ to XML. XSLT è supportato nello spazio dei nomi gestito <xref:System.Xml.Xsl> e nell'implementazione COM nativa di MSXML. Sebbene XSLT sia una tecnologia affidabile per la modifica di documenti XML, richiede una certa esperienza in un dominio specializzato, ovvero quello del linguaggio XSLT e delle API che lo supportano.  
  
 LINQ to XML fornisce gli strumenti necessari per codificare trasformazioni funzionali pure in modo espressivo e potente all'interno di codice C# o Visual Basic. Ad esempio, in molti degli esempi della documentazione di LINQ to XML viene usato un approccio funzionale pure. Inoltre, nella [esercitazione: modifica del contenuto in un documento WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) esercitazione usiamo LINQ to XML in un approccio funzionale per modificare le informazioni in un documento Microsoft Word.  
  
 Per un confronto più completo tra LINQ to XML e altre tecnologie XML Microsoft, vedere [LINQ to XML e altre tecnologie XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).  
  
 XSLT è lo strumento consigliato per effettuare trasformazioni basate su documenti in cui il documento di origine è caratterizzato da una struttura irregolare. Tuttavia, anche LINQ to XML è in grado di eseguire trasformazioni basate su documenti. Per altre informazioni, vedere [procedura: usare annotazioni per trasformare alberi LINQ to XML in uno stile XSLT (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md).  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle trasformazioni funzionali Pure (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
- [LINQ to XML e altre tecnologie XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)
