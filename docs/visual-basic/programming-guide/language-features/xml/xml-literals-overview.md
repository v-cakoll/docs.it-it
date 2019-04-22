---
title: Cenni preliminari sui valori letterali XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: a7b70669131ae35135088418e4b33b3ae289d322
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839886"
---
# <a name="xml-literals-overview-visual-basic"></a>Cenni preliminari sui valori letterali XML (Visual Basic)
Un' *valore letterale XML* consente di incorporare XML direttamente nel codice Visual Basic. La sintassi dei valori letterali XML rappresenta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti ed è simile alla sintassi XML 1.0. Questo rende più semplice creare elementi e documenti XML a livello di codice perché il codice ha la stessa struttura il codice XML finale.  
  
 Visual Basic consente di compilare i valori letterali XML in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] fornisce un modello a oggetti semplice per la creazione e modifica di XML e questo modello si integra bene con [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.  
  
 È possibile incorporare un'espressione Visual Basic in un valore letterale XML. In fase di esecuzione, l'applicazione crea un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto per ogni valore letterale, includendo i valori delle espressioni incorporate. Ciò consente di specificare il contenuto dinamico all'interno di un valore letterale XML. Per altre informazioni, vedere [espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Per altre informazioni sulle differenze tra la sintassi dei valori letterali XML e la sintassi XML 1.0, vedere [valori letterali XML e specifica XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Valori letterali semplici  
 È possibile creare un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto nel codice Visual Basic digitando o incollando in formato XML valido. Restituisce un valore letterale elemento XML un <xref:System.Xml.Linq.XElement> oggetto. Per altre informazioni, vedere [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) e [i valori letterali XML e specifica XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). L'esempio seguente crea un elemento XML che dispone di diversi elementi figlio.  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 È possibile creare un documento XML avviando un valore letterale XML con `<?xml version="1.0"?>`, come illustrato nell'esempio seguente. Restituisce un valore letterale documento XML un <xref:System.Xml.Linq.XDocument> oggetto. Per altre informazioni, vedere [letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
>  La sintassi dei valori letterali XML in Visual Basic non è identica a quella nella specifica XML 1.0. Per altre informazioni, vedere [valori letterali XML e specifica XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Continuazione di riga  
 Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga (sequenza spazio-carattere di sottolineatura-invio). Questo rende più semplice confrontare i valori letterali XML nel codice con i documenti XML.  
  
 Il compilatore considera i caratteri di continuazione di riga come parte di un valore letterale XML. Pertanto, è necessario utilizzare la sequenza spazio-carattere di sottolineatura-invio solo quando fa parte il [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto.  
  
 Tuttavia, è necessario caratteri di continuazione di riga se si dispone di un'espressione a più righe in un'espressione incorporata. Per altre informazioni, vedere [espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Incorporare le query nei valori letterali XML  
 È possibile usare una query in un'espressione incorporata. Quando si esegue questa operazione, gli elementi restituiti dalla query vengono aggiunti all'elemento XML. Ciò consente di aggiungere contenuto dinamico, ad esempio il risultato della query dell'utente, a un valore letterale XML.  
  
 Ad esempio, il codice seguente usa una query incorporata per creare elementi XML dai membri del `phoneNumbers2` della matrice e quindi aggiungere gli elementi come elementi figlio di `contact2`.  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Come il compilatore crea gli oggetti da valori letterali XML  
 Il compilatore Visual Basic converte i valori letterali XML in chiamate nell'equivalente [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] costruttori per creare il [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto. Ad esempio, il compilatore Visual Basic verrà convertito il codice seguente in una chiamata al <xref:System.Xml.Linq.XProcessingInstruction> costruttore per l'istruzione di versione XML, le chiamate al <xref:System.Xml.Linq.XElement> costruttore per il `<contact>`, `<name>`, e `<phone>` gli elementi e le chiamate per il <xref:System.Xml.Linq.XAttribute> costruttore per la `type` attributo. In particolare, ha gli attributi nell'esempio seguente, il compilatore Visual Basic chiamerà il <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> costruttore due volte. Il primo supererà il valore `type` per il `name` parametro e il valore `home` per il `value` parametro. La seconda passa anche il valore `type` per il `name` parametro, ma il valore `work` per il `value` parametro.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Valore letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md)
