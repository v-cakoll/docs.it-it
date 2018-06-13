---
title: Cenni preliminari sui valori letterali XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: 03fc8c11b5553c9c3a63bdcb69bf6135050e2c89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655023"
---
# <a name="xml-literals-overview-visual-basic"></a>Cenni preliminari sui valori letterali XML (Visual Basic)
Un' *valore letterale XML* consente di incorporare XML direttamente nel codice Visual Basic. Sintassi del valore letterale XML rappresenta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti ed è simile alla sintassi XML 1.0. Questo rende più semplice creare elementi e documenti XML a livello di programmazione perché il codice ha la stessa struttura del XML finale.  
  
 Visual Basic compila i valori letterali XML in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] fornisce un modello a oggetti semplice per la creazione e modifica di XML e questo modello si integra bene con [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.  
  
 È possibile incorporare un'espressione Visual Basic in un valore letterale XML. In fase di esecuzione, l'applicazione crea un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto per ogni tipo di valore letterale, includendo i valori delle espressioni incorporate. Consente di specificare il contenuto dinamico all'interno di un valore letterale XML. Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Per ulteriori informazioni sulle differenze tra la sintassi del valore letterale XML e la sintassi XML 1.0, vedere [valori letterali XML e specifica XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Valori letterali semplici  
 È possibile creare un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto nel codice Visual Basic digitando o incollando il codice XML valido. Restituisce un valore letterale elemento XML un <xref:System.Xml.Linq.XElement> oggetto. Per ulteriori informazioni, vedere [XML elemento Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) e [valori letterali XML e specifica XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). L'esempio seguente crea un elemento XML che dispone di diversi elementi figlio.  
  
 [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 È possibile creare un documento XML tramite l'avvio di un valore letterale XML con `<?xml version="1.0"?>`, come illustrato nell'esempio seguente. Restituisce un valore letterale documento XML un <xref:System.Xml.Linq.XDocument> oggetto. Per ulteriori informazioni, vedere [valore letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  Sintassi del valore letterale XML in Visual Basic non è identica a quella nella specifica XML 1.0. Per ulteriori informazioni, vedere [valori letterali XML e specifica XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Continuazione di riga  
 Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga (sequenza spazio-carattere di sottolineatura-invio). Questo rende più semplice confrontare i valori letterali XML in codice con i documenti XML.  
  
 Il compilatore considera i caratteri di continuazione di riga come parte di un valore letterale XML. Pertanto, è necessario utilizzare la sequenza spazio-carattere di sottolineatura-invio solo quando fa parte di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto.  
  
 Caratteri di continuazione di riga, tuttavia, è necessaria se si dispone di un'espressione su più righe in un'espressione incorporata. Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Incorporamento di query nei valori letterali XML  
 È possibile utilizzare una query in un'espressione incorporata. Quando si esegue questa operazione, gli elementi restituiti dalla query vengono aggiunti all'elemento XML. Ciò consente di aggiungere contenuto dinamico, ad esempio il risultato di query dell'utente, a un valore letterale XML.  
  
 Ad esempio, il codice seguente usa una query incorporata per creare elementi XML dai membri del `phoneNumbers2` di matrice e quindi aggiungere tali elementi come elementi figlio di `contact2`.  
  
 [!code-vb[VbXMLSamples#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Come il compilatore crea gli oggetti da valori letterali XML  
 Il compilatore Visual Basic converte i valori letterali XML in chiamate all'equivalente [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] costruttori per creare il [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto. Ad esempio, il compilatore Visual Basic convertirà l'esempio di codice seguente in una chiamata ai <xref:System.Xml.Linq.XProcessingInstruction> costruttore per l'istruzione in versione XML, le chiamate al <xref:System.Xml.Linq.XElement> costruttore per il `<contact>`, `<name>`, e `<phone>` gli elementi e chiamate per il <xref:System.Xml.Linq.XAttribute> costruttore per il `type` attributo. In particolare, dati gli attributi nell'esempio seguente, il compilatore Visual Basic chiamerà il <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> costruttore due volte. Il primo passerà il valore `type` per il `name` parametro e il valore `home` per il `value` parametro. Il secondo passerà anche il valore `type` per il `name` parametro, ma il valore `work` per il `value` parametro.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XElement>  
 [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Valore letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md)
