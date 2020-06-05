---
title: Panoramica di LINQ to XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 044aca634f5a0aa6e557a7dd9c0e1de64e35dc15
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374655"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Cenni preliminari su LINQ to XML in Visual Basic
Visual Basic fornisce supporto per i [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] valori letterali XML e le proprietà Axis XML. In questo modo è possibile utilizzare una sintassi familiare e pratica per l'utilizzo di XML nel codice Visual Basic. I *valori letterali XML* consentono di includere codice XML direttamente nel codice. Le *Proprietà Axis XML* consentono di accedere a nodi figlio, nodi discendenti e attributi di un valore letterale XML. Per ulteriori informazioni, vedere [Cenni preliminari sui valori letterali XML](xml-literals-overview.md) e [accesso a XML in Visual Basic](accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]è un'API di programmazione XML in memoria progettata specificamente per sfruttare i vantaggi di LINQ (Language-Integrated Query). Sebbene sia possibile chiamare direttamente le API LINQ, solo Visual Basic consente di dichiarare i valori letterali XML e di accedere direttamente alle proprietà Axis XML.  
  
> [!NOTE]
> I valori letterali XML e le proprietà Axis XML non sono supportati nel codice dichiarativo in una pagina ASP.NET. Per usare Visual Basic funzionalità XML, inserire il codice in una pagina code-behind nell'applicazione ASP.NET.  
  
 [Pulsante Riproduci](./media/overview-of-linq-to-xml/play-video-icon-example.gif) Per le dimostrazioni video correlate, vedere la pagina relativa alla procedura per iniziare [a usare LINQ to XML](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) e [come creare fogli di calcolo di Excel con LINQ to XML](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).
  
## <a name="creating-xml"></a>Creazione di XML  
 Esistono due modi per creare alberi XML in Visual Basic. È possibile dichiarare un valore letterale XML direttamente nel codice oppure è possibile usare le API LINQ per creare l'albero. Entrambi i processi consentono al codice di riflettere la struttura finale dell'albero XML. Nell'esempio di codice seguente, ad esempio, viene creato un elemento XML:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Per ulteriori informazioni, vedere [creazione di codice XML in Visual Basic](creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Accesso ed esplorazione di XML  
 Visual Basic fornisce proprietà Axis XML per l'accesso e l'esplorazione di strutture XML. Queste proprietà consentono di accedere a elementi e attributi XML specificando i nomi degli elementi figlio XML. In alternativa, è possibile chiamare in modo esplicito i metodi LINQ per lo spostamento e l'individuazione di elementi e attributi. Nell'esempio di codice seguente, ad esempio, vengono utilizzate le proprietà Axis XML per fare riferimento agli attributi e agli elementi figlio di un elemento XML. Nell'esempio di codice viene utilizzata una query LINQ per recuperare gli elementi figlio e restituirli come elementi XML, eseguendo in modo efficace una trasformazione.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Per ulteriori informazioni, vedere [accesso a XML in Visual Basic](accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Visual Basic consente di specificare un alias per uno spazio dei nomi XML globale utilizzando l' `Imports` istruzione. Nell'esempio seguente viene illustrato come utilizzare l' `Imports` istruzione per importare uno spazio dei nomi XML:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 È possibile utilizzare un alias dello spazio dei nomi XML quando si accede alle proprietà Axis XML e si dichiarano valori letterali XML per documenti ed elementi XML.  
  
 È possibile recuperare un <xref:System.Xml.Linq.XNamespace> oggetto per un prefisso dello spazio dei nomi specifico usando l' [operatore GetXmlNamespace](../../../language-reference/operators/getxmlnamespace-operator.md).  
  
 Per altre informazioni, vedere [istruzione Imports (spazio dei nomi XML)](../../../language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Utilizzo di spazi dei nomi XML nei valori letterali XML  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Xml.Linq.XElement> oggetto che utilizza lo spazio dei nomi globale `ns` :  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Il compilatore Visual Basic converte i valori letterali XML che contengono alias dello spazio dei nomi XML in codice equivalente che utilizza la notazione XML per l'utilizzo di spazi dei nomi XML, con l' `xmlns` attributo. Quando viene compilato, il codice nell'esempio della sezione precedente produce essenzialmente lo stesso codice eseguibile dell'esempio seguente:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Utilizzo di spazi dei nomi XML in Proprietà Axis XML  
 Gli spazi dei nomi XML dichiarati in valori letterali XML non sono disponibili per l'utilizzo nelle proprietà Axis XML. È tuttavia possibile utilizzare gli spazi dei nomi globali con le proprietà dell'asse XML. Usare i due punti per separare il prefisso dello spazio dei nomi XML dal nome dell'elemento locale. Di seguito è illustrato un esempio:  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [XML](index.md)
- [Creazione di XML in Visual Basic](creating-xml.md)
- [Accesso a XML in Visual Basic](accessing-xml.md)
- [Modifica di XML in Visual Basic](manipulating-xml.md)
