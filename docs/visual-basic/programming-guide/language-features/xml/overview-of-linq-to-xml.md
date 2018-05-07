---
title: Cenni preliminari su LINQ to XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 1ac9c7749cb054857715fd670f1510697c18f0e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Cenni preliminari su LINQ to XML in Visual Basic
Visual Basic fornisce il supporto per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tramite valori letterali XML e proprietà axis XML. In questo modo è possibile utilizzare una sintassi familiare e utile per l'utilizzo di XML nel codice Visual Basic. *Valori letterali XML* consentono di includere dati XML direttamente nel codice. *Proprietà axis XML* consentono di accedere a nodi figlio, i nodi discendenti e gli attributi di un valore letterale XML. Per ulteriori informazioni, vedere [Cenni preliminari sui valori letterali XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) e [l'accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è progettato specificamente per sfruttare i vantaggi di API di programmazione XML in memoria [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Sebbene sia possibile chiamare il [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] direttamente le API, solo Visual Basic consente di dichiarare i valori letterali XML e accedere direttamente le proprietà axis XML.  
  
> [!NOTE]
>  Valori letterali XML e proprietà axis XML non sono supportati nel codice dichiarativo in una pagina ASP.NET. Per utilizzare le funzionalità XML di Visual Basic, inserire il codice in una pagina code-behind nell'applicazione ASP.NET.  
  
 ![collegamento alla trasmissione video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") per dimostrazioni video correlate, vedere [How Do controllabili avviato con LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) e [ricerca per categorie creare fogli di calcolo Excel usando LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536).  
  
## <a name="creating-xml"></a>Creazione di dati XML  
 Esistono due modi per creare alberi XML in Visual Basic. È possibile dichiarare letterale direttamente nel codice XML oppure è possibile utilizzare il [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] API per creare l'albero. Entrambi i processi consentono al codice in modo da riflettere la struttura finale dell'albero XML. Ad esempio, l'esempio di codice seguente crea un elemento XML:  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Per ulteriori informazioni, vedere [la creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Accesso e l'esplorazione XML  
 Visual Basic fornisce le proprietà axis XML per l'accesso e l'esplorazione di strutture XML. Queste proprietà consentono di accedere a elementi e attributi XML specificando i nomi di elemento figlio XML. In alternativa, è possibile chiamare in modo esplicito il [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] metodi per l'esplorazione e individuazione di elementi e attributi. Esempio di codice seguente, ad esempio, utilizza le proprietà axis XML per fare riferimento agli attributi e gli elementi figlio di un elemento XML. Nell'esempio di codice viene utilizzato un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query per recuperare gli elementi figlio e restituirli come elementi XML, in modo efficace eseguendo una trasformazione.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Per ulteriori informazioni, vedere [l'accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Visual Basic consente di specificare un alias per uno spazio dei nomi XML globale utilizzando il `Imports` istruzione. Nell'esempio seguente viene illustrato come utilizzare il `Imports` per importare uno spazio dei nomi XML:  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 Quando si accede alle proprietà axis XML e dichiarano i valori letterali XML per elementi e documenti XML, è possibile utilizzare un alias dello spazio dei nomi XML.  
  
 È possibile recuperare un <xref:System.Xml.Linq.XNamespace> oggetto per un prefisso dello spazio dei nomi specifico tramite il [operatore GetXmlNamespace](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Utilizzo di spazi dei nomi XML in valori letterali XML  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Xml.Linq.XElement> oggetto che utilizza lo spazio dei nomi globale `ns`:  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 Il compilatore Visual Basic converte i valori letterali XML che contengono gli alias dello spazio dei nomi XML in codice equivalente che utilizza la notazione XML per l'utilizzo di spazi dei nomi XML, con la `xmlns` attributo. Quando viene compilato, il codice di esempio della sezione precedente produce essenzialmente lo stesso codice eseguibile come nell'esempio seguente:  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Utilizzo di spazi dei nomi XML in proprietà Axis XML  
 Spazi dei nomi XML dichiarati in valori letterali XML non sono disponibili per le proprietà axis XML. Tuttavia, è possibile utilizzare gli spazi dei nomi globale con le proprietà axis XML. I due punti per separare il prefisso dello spazio dei nomi XML da utilizzare il nome locale dell'elemento. Di seguito è riportato un esempio:  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
