---
title: Panoramica di LINQ to XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 0481a140541a7f45c682c5150bc1c3d647de90bd
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266898"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Cenni preliminari su LINQ to XML in Visual Basic
Visual Basic fornisce [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supporto per tramite valori letterali XML e proprietà axis XML. In questo modo è possibile utilizzare una sintassi familiare e comoda per l'utilizzo di XML nel codice Visual Basic. *I valori letterali XML* consentono di includere XML direttamente nel codice. *Le proprietà axis XML* consentono di accedere a nodi figlio, nodi discendenti e attributi di un valore letterale XML. Per ulteriori informazioni, vedere [Cenni preliminari](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) sui valori letterali XML e [Accesso all'XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]è un'API di programmazione XML in memoria progettata specificamente per sfruttare i vantaggi di Language-Integrated Query (LINQ). Sebbene sia possibile chiamare direttamente le API LINQ, solo Visual Basic consente di dichiarare valori letterali XML e accedere direttamente alle proprietà axis XML.  
  
> [!NOTE]
> I valori letterali XML e le proprietà axis XML non sono supportati nel codice dichiarativo in una pagina ASP.NET. Per utilizzare le funzionalità XML di Visual Basic, inserire il codice in una pagina code-behind nell'applicazione ASP.NET.  
  
 [Pulsante Riproduci](./media/overview-of-linq-to-xml/play-video-icon-example.gif) Per le dimostrazioni video correlate, vedere [Come iniziare a usare LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) e Come creare fogli di calcolo di Excel utilizzando LINQ to [XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).
  
## <a name="creating-xml"></a>Creazione di XML  
 Esistono due modi per creare strutture ad albero XML in Visual Basic.There are two ways to create XML trees in Visual Basic. È possibile dichiarare un valore letterale XML direttamente nel codice oppure è possibile usare le API LINQ per creare la struttura ad albero. Entrambi i processi consentono al codice di riflettere la struttura finale della struttura ad albero XML. Ad esempio, l'esempio di codice seguente crea un elemento XML:For example, the following code example creates an XML element:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Per ulteriori informazioni, vedere [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Accesso e esplorazione del codice XML  
 Visual Basic fornisce proprietà axis XML per l'accesso e lo spostamento tra strutture XML. Queste proprietà consentono di accedere agli elementi e agli attributi XML specificando i nomi degli elementi figlio XML. In alternativa, è possibile chiamare in modo esplicito i metodi LINQ per lo spostamento e l'individuazione di elementi e attributi. Ad esempio, nell'esempio di codice seguente vengono utilizzate le proprietà axis XML per fare riferimento agli attributi e agli elementi figlio di un elemento XML. Nell'esempio di codice viene utilizzata una query LINQ per recuperare gli elementi figlio e generare output come elementi XML, eseguendo in modo efficace una trasformazione.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Per ulteriori informazioni, vedere [Accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Visual Basic consente di specificare un alias per `Imports` uno spazio dei nomi XML globale utilizzando l'istruzione . Nell'esempio seguente viene `Imports` illustrato come utilizzare l'istruzione per importare uno spazio dei nomi XML:The following example shows how to use the statement to import an XML namespace:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 È possibile utilizzare un alias dello spazio dei nomi XML quando si accede alle proprietà axis XML e si dichiarano valori letterali XML per documenti ed elementi XML.  
  
 È possibile <xref:System.Xml.Linq.XNamespace> recuperare un oggetto per un determinato prefisso dello spazio dei nomi utilizzando l'operatore [GetXmlNamespace](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Per ulteriori informazioni, vedere [Istruzione Imports (spazio dei nomi XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Utilizzo di spazi dei nomi XML nei valori letterali XMLUsing XML Namespaces in XML Literals  
 Nell'esempio seguente viene <xref:System.Xml.Linq.XElement> illustrato come creare `ns`un oggetto che utilizza lo spazio dei nomi globale :  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Il compilatore Visual Basic converte i valori letterali XML che contengono alias dello spazio dei `xmlns` nomi XML in codice equivalente che utilizza la notazione XML per l'utilizzo di spazi dei nomi XML, con l'attributo . Quando viene compilato, il codice nell'esempio della sezione precedente produce essenzialmente lo stesso codice eseguibile dell'esempio seguente:When compiled, the code in the previous section's example produces essentially the same executable code as the following example:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Utilizzo di spazi dei nomi XML nelle proprietà dell'asse XMLUsing XML Namespaces in XML Axis Properties  
 Gli spazi dei nomi XML dichiarati nei valori letterali XML non sono disponibili per l'utilizzo nelle proprietà axis XML. Tuttavia, gli spazi dei nomi globali possono essere utilizzati con le proprietà axis XML. Utilizzare i due punti per separare il prefisso dello spazio dei nomi XML dal nome dell'elemento locale. Di seguito è illustrato un esempio:  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Xml](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
