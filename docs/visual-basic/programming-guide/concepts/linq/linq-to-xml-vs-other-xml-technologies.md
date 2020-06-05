---
title: LINQ to XML rispetto ad altri Technologies2 XML
ms.date: 07/20/2015
ms.assetid: 72ce3a82-ffc6-488c-98e7-b9b40f3591ec
ms.openlocfilehash: ee855c40e61a6b63c2891d8f30072fc8e235fe4b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389319"
---
# <a name="linq-to-xml-vs-other-xml-technologies"></a>LINQ to XML e altre tecnologie XML
In questo argomento viene illustrato un confronto tra [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] e le seguenti tecnologie XML: <xref:System.Xml.XmlReader>, XSLT, MSXML e XmlLite. Queste informazioni possono risultare utili per decidere quale tecnologia usare.  
  
 Per un confronto tra [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] e il Document Object Model (Dom), vedere [LINQ to XML e dom (Visual Basic)](linq-to-xml-vs-dom.md).  
  
## <a name="linq-to-xml-vs-xmlreader"></a>Differenze tra LINQ to XML e XmlReader  
 <xref:System.Xml.XmlReader> è un parser rapido, di tipo forward-only, che non supporta la memorizzazione nella cache.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] viene implementato sopra <xref:System.Xml.XmlReader>, con cui è strettamente integrato. Tuttavia, è possibile usare <xref:System.Xml.XmlReader> anche in modo autonomo.  
  
 Si supponga ad esempio di compilare un servizio Web per l'analisi di centinaia di documenti XML al secondo e che i documenti abbiano la stessa struttura, per cui è necessario scrivere un'unica implementazione del codice di analisi. In questo caso, è preferibile usare <xref:System.Xml.XmlReader> in modo autonomo.  
  
 Se al contrario si compila un sistema per l'analisi di vari documenti XML più piccoli, diversi uno dall'altro, è consigliabile sfruttare i miglioramenti per la produttività offerti da [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="linq-to-xml-vs-xslt"></a>Differenze tra LINQ to XML e XSLT  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] e in XSLT sono disponibili funzionalità complete per la trasformazione di documenti XML. XSLT è un approccio dichiarativo, basato su regole. I programmatori XSLT avanzati scrivono codice XSLT in uno stile di programmazione funzionale che enfatizza un approccio senza stato. Le trasformazioni possono essere scritte con funzioni pure implementate senza effetti collaterali. Questo approccio basato su regole o funzionale non è noto a tutti gli sviluppatori e può risultare un processo lungo e difficile da apprendere.  
  
 XSLT può essere un sistema molto produttivo che consente di generare applicazioni a elevate prestazioni. Alcune grandi società Web, ad esempio, usano XSLT per generare HTML dall'XML recuperato da un'ampia varietà di archivi dati. Il motore XSLT gestito compila XSLT in codice CLR e in alcuni scenari offre prestazioni ancora più elevate rispetto al motore XSLT nativo.  
  
 Tuttavia, XSLT non consente di sfruttare le conoscenze di C# e Visual Basic di cui dispongono molti sviluppatori. Richiede la scrittura di codice in un linguaggio di programmazione diverso e complesso. Con l'uso di due sistemi di sviluppo non integrati, quali C# (o Visual Basic) e XSLT, i sistemi software risultanti sono più difficili da sviluppare e mantenere.  
  
 Per gli sviluppatori che hanno acquisito una buona familiarità con le espressioni di query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], le trasformazioni [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] rappresentano una tecnologia potente di facile utilizzo. Essenzialmente, il documento XML viene creato usando la costruzione funzionale, recuperando i dati da vari origini, costruendo dinamicamente oggetti <xref:System.Xml.Linq.XElement> e assemblando l'insieme in un nuovo albero XML. La trasformazione può generare un documento completamente nuovo. La costruzione di trasformazioni in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è un processo relativamente semplice e intuitivo e il codice risultante è leggibile, con una conseguente riduzione dei costi di sviluppo e manutenzione.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] non è progettato per sostituire XSLT, che rimane lo strumento ideale per trasformazioni XML complicate e basate su documenti, soprattutto se la struttura del documento non è ben definita.  
  
 XSLT presenta il vantaggio di essere uno standard W3C (World Wide Web Consortium). Se è necessario rispettare il requisito di usare solo tecnologie che corrispondono a standard, XSLT può rivelarsi la soluzione più appropriata.  
  
 XSLT equivale a XML, pertanto può essere modificato a livello di codice.  
  
## <a name="linq-to-xml-vs-msxml"></a>Differenze tra LINQ to XML MSXML  
 MSXML è la tecnologia basata su COM per l'elaborazione di codice XML inclusa in Microsoft Windows. Fornisce un'implementazione nativa di DOM (Document Object Model) con supporto per XPath e XSLT. Contiene inoltre il parser SAX2 basato su eventi che non supporta la memorizzazione nella cache.  
  
 MSXML offre prestazioni soddisfacenti, è sicuro per impostazione predefinita nella maggior parte degli scenari ed è accessibile in Internet Explorer per eseguire l'elaborazione XML lato client nelle applicazioni in stile AJAX. Può essere usato da qualsiasi linguaggio di programmazione che supporta COM, tra cui C++, JavaScript e Visual Basic 6.0.  
  
 L'utilizzo di MSXML non è consigliato in codice gestito basato sul CLR (Common Language Runtime).  
  
## <a name="linq-to-xml-vs-xmllite"></a>Differenze tra LINQ to XML e XmlLite  
 XmlLite è un parser di tipo pull e forward-only che non supporta la memorizzazione nella cache. Gli sviluppatori usano XmlLite principalmente con C++. Non è consigliabile usare XmlLite con codice gestito.  
  
 Il vantaggio principale di XmlLite è che si tratta di un parser XML veloce e leggero, sicuro nella maggior parte degli scenari. La superficie di rischio è molto ridotta. Se è necessario analizzare documenti non attendibili e si desidera proteggersi da attacchi di tipo Denial of Service o esposizione di dati, XmlLite rappresenta una buona soluzione.  
  
 XmlLite non è integrato con LINQ (Language-Integrated Query). Non produce i miglioramenti alla produttività dei programmatori che sono la forza motivazione alla base di LINQ.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione (LINQ to XML)](getting-started-linq-to-xml.md)
