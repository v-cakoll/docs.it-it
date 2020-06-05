---
title: Cenni preliminari sui valori letterali XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: e889de4eefae6a943c70735f8a16474cb76d1149
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403291"
---
# <a name="xml-literals-overview-visual-basic"></a>Cenni preliminari sui valori letterali XML (Visual Basic)
Un *valore letterale XML* consente di incorporare XML direttamente nel codice Visual Basic. La sintassi dei valori letterali XML rappresenta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti ed è simile alla sintassi xml 1,0. Questo rende più semplice la creazione di elementi e documenti XML a livello di codice, perché il codice ha la stessa struttura del codice XML finale.  
  
 Visual Basic compila i valori letterali XML in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]fornisce un modello a oggetti semplice per la creazione e la modifica di XML e questo modello si integra bene con LINQ (Language-Integrated Query). Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.  
  
 È possibile incorporare un'espressione Visual Basic in un valore letterale XML. In fase di esecuzione, l'applicazione crea un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto per ogni valore letterale, incorporando i valori delle espressioni incorporate. Ciò consente di specificare contenuto dinamico all'interno di un valore letterale XML. Per ulteriori informazioni, vedere [espressioni incorporate in XML](embedded-expressions-in-xml.md).  
  
 Per ulteriori informazioni sulle differenze tra la sintassi dei valori letterali XML e la sintassi XML 1,0, vedere [valori letterali XML e la specifica xml 1,0](xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Valori letterali semplici  
 È possibile creare un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto nel codice Visual Basic digitando o incollando in XML valido. Un valore letterale elemento XML restituisce un <xref:System.Xml.Linq.XElement> oggetto. Per ulteriori informazioni, vedere [valore letterale elemento XML](../../../language-reference/xml-literals/xml-element-literal.md) e [valori letterali XML e specifica XML 1,0](xml-literals-and-the-xml-1-0-specification.md). Nell'esempio seguente viene creato un elemento XML con diversi elementi figlio.  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 È possibile creare un documento XML avviando un valore letterale XML con `<?xml version="1.0"?>` , come illustrato nell'esempio seguente. Un valore letterale di documento XML restituisce un <xref:System.Xml.Linq.XDocument> oggetto. Per altre informazioni, vedere [valore letterale documento XML](../../../language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
> La sintassi dei valori letterali XML in Visual Basic non è identica alla sintassi nella specifica XML 1,0. Per ulteriori informazioni, vedere [valori letterali XML e specifica xml 1,0](xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Continuazione di riga  
 Un valore letterale XML può estendersi su più righe senza usare caratteri di continuazione di riga, ovvero la sequenza di sottolineatura di spazio. Questo consente di confrontare più facilmente i valori letterali XML nel codice con documenti XML.  
  
 Il compilatore considera i caratteri di continuazione di riga come parte di un valore letterale XML. Pertanto, è necessario utilizzare la sequenza di sottolineatura spazio-invio solo quando appartiene all' [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto.  
  
 Tuttavia, se si dispone di un'espressione su più righe in un'espressione incorporata, è necessario utilizzare caratteri di continuazione di riga. Per ulteriori informazioni, vedere [espressioni incorporate in XML](embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Incorporamento di query in valori letterali XML  
 È possibile utilizzare una query in un'espressione incorporata. Quando si esegue questa operazione, gli elementi restituiti dalla query vengono aggiunti all'elemento XML. Ciò consente di aggiungere contenuto dinamico, ad esempio il risultato della query di un utente, a un valore letterale XML.  
  
 Il codice seguente, ad esempio, usa una query incorporata per creare elementi XML dai membri della `phoneNumbers2` matrice e quindi aggiungerli come elementi figlio di `contact2` .  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Come il compilatore crea oggetti dai valori letterali XML  
 Il compilatore Visual Basic converte i valori letterali XML in chiamate ai costruttori equivalenti [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per creare l' [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetto. Il compilatore Visual Basic, ad esempio, tradurrà l'esempio di codice seguente in una chiamata al <xref:System.Xml.Linq.XProcessingInstruction> costruttore per l'istruzione di versione XML, le chiamate al <xref:System.Xml.Linq.XElement> costruttore per gli `<contact>` elementi, e e le `<name>` `<phone>` chiamate al <xref:System.Xml.Linq.XAttribute> costruttore per l' `type` attributo. In particolare, dato gli attributi nell'esempio seguente, il compilatore Visual Basic chiamerà <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> due volte il costruttore. Il primo passerà il valore `type` per il `name` parametro e il valore `home` per il `value` parametro. Il secondo passerà anche il valore `type` per il `name` parametro, ma il valore `work` per il `value` parametro.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- [Creazione di XML in Visual Basic](creating-xml.md)
- [Espressioni incorporate in XML](embedded-expressions-in-xml.md)
- [Valore letterale di documento XML](../../../language-reference/xml-literals/xml-document-literal.md)
- [Valore letterale di elemento XML](../../../language-reference/xml-literals/xml-element-literal.md)
- [Valori letterali XML](../../../language-reference/xml-literals/index.md)
