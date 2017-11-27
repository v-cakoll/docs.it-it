---
title: Cenni preliminari su LINQ to XML in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: baa60939654857f40d323b6412978ed4ff918177
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Cenni preliminari su LINQ to XML in Visual Basic
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]fornisce il supporto per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tramite valori letterali XML e proprietà axis XML. In questo modo è possibile utilizzare una sintassi familiare e utile per l'utilizzo di XML nel [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] codice. *Valori letterali XML* consentono di includere dati XML direttamente nel codice. *Proprietà axis XML* consentono di accedere a nodi figlio, i relativi nodi discendenti e attributi di un valore letterale XML. Per ulteriori informazioni, vedere [Cenni preliminari sui valori letterali XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) e [l'accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]è stato progettato specificamente per sfruttare i vantaggi di API di programmazione XML in memoria [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Sebbene sia possibile chiamare il [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] direttamente, le API solo [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] consente di dichiarare i valori letterali XML e accedere direttamente le proprietà axis XML.  
  
> [!NOTE]
>  Valori letterali XML e proprietà axis XML non sono supportati nel codice dichiarativo in una pagina ASP.NET. Per utilizzare le funzionalità XML di Visual Basic, inserire il codice in una pagina code-behind nell'applicazione ASP.NET.  
  
 ![collegamento a video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") per dimostrazioni video correlate, vedere [How Do controllabili avviato con LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) e [come posso creare fogli di calcolo Excel tramite LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536).  
  
## <a name="creating-xml"></a>Creazione di dati XML  
 Esistono due modi per creare alberi XML in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. È possibile dichiarare letterale direttamente nel codice XML oppure è possibile utilizzare il [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] API per creare l'albero. Entrambi i processi consentono al codice in modo da riflettere la struttura finale dell'albero XML. Ad esempio, l'esempio di codice seguente crea un elemento XML:  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Per ulteriori informazioni, vedere [la creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Accesso e l'esplorazione XML  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]fornisce le proprietà axis XML per l'accesso e l'esplorazione di strutture XML. Queste proprietà consentono di accedere a elementi e attributi XML specificando i nomi di elemento figlio XML. In alternativa, è possibile chiamare in modo esplicito il [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] metodi per l'esplorazione e individuazione di elementi e attributi. Esempio di codice seguente, ad esempio, utilizza le proprietà axis XML per fare riferimento agli attributi e gli elementi figlio di un elemento XML. Nell'esempio di codice viene utilizzato un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query per recuperare gli elementi figlio e restituirli come elementi XML, in modo efficace eseguendo una trasformazione.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Per ulteriori informazioni, vedere [l'accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Consente di specificare un alias da un spazio dei nomi XML globale utilizzando il `Imports` istruzione. Nell'esempio seguente viene illustrato come utilizzare il `Imports` per importare uno spazio dei nomi XML:  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 Quando si accede alle proprietà axis XML e dichiarano i valori letterali XML per elementi e documenti XML, è possibile utilizzare un alias dello spazio dei nomi XML.  
  
 È possibile recuperare un <xref:System.Xml.Linq.XNamespace> oggetto per un prefisso dello spazio dei nomi specifico tramite il [operatore GetXmlNamespace](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Utilizzo di spazi dei nomi XML in valori letterali XML  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Xml.Linq.XElement> oggetto che utilizza lo spazio dei nomi globale `ns`:  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore converte i valori letterali XML che contengono l'alias dello spazio dei nomi XML in codice equivalente che utilizza la notazione XML per l'uso di spazi dei nomi XML, con la `xmlns` attributo. Quando viene compilato, il codice di esempio della sezione precedente produce essenzialmente lo stesso codice eseguibile come nell'esempio seguente:  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Utilizzo di spazi dei nomi XML in proprietà Axis XML  
 Spazi dei nomi XML dichiarati in valori letterali XML non sono disponibili per le proprietà axis XML. Tuttavia, è possibile utilizzare gli spazi dei nomi globale con le proprietà axis XML. I due punti per separare il prefisso dello spazio dei nomi XML da utilizzare il nome locale dell'elemento. Di seguito è riportato un esempio:  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
