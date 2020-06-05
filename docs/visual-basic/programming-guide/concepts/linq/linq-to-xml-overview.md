---
title: Panoramica di LINQ to XML
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: afdec54ac05bb4a631de7fdb599123ffe964c443
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368738"
---
# <a name="linq-to-xml-overview-visual-basic"></a>Panoramica di LINQ to XML (Visual Basic)
XML è stato ampiamente adottato per la formattazione dei dati in una vasta gamma di contesti. Viene ad esempio usato in applicazioni Web, file di configurazione, file di Microsoft Office Word e in database.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] costituisce un approccio aggiornato e ridisegnato alla programmazione con XML. Fornisce le funzionalità di modifica dei documenti in memoria del Document Object Model (DOM) e supporta le espressioni di query LINQ. Sebbene sintatticamente diverse da XPath, queste espressioni di query offrono funzionalità simili.  
  
## <a name="linq-to-xml-developers"></a>Sviluppatori LINQ to XML  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è destinato a diversi tipi di sviluppatori. Per un sviluppatore medio che desidera solo poter eseguire una determinata operazione, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] semplifica il codice XML e consente di eseguire query in modo simile a SQL. Sono poi sufficienti competenze minime per consentire a un programmatore di imparare a scrivere query potenti e meno estese nel linguaggio di programmazione desiderato.  
  
 Gli sviluppatori professionisti possono usare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per incrementare notevolmente la propria produttività. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consente di scrivere una minor quantità di codice, che tuttavia risulta più espressivo, compatto e potente. È inoltre possibile usare espressioni di query da più domini di dati contemporaneamente.  
  
## <a name="what-is-linq-to-xml"></a>Informazioni su LINQ to XML  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è un'interfaccia di programmazione XML in memoria con supporto LINQ che consente di usare codice XML dall'interno dei linguaggi di programmazione .NET Framework.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è simile al modello DOM (Document Object Model) in quanto porta in memoria il documento XML. È quindi possibile eseguire query e modificare il documento e dopo averlo modificato salvarlo in un file o serializzarlo e inviarlo tramite Internet. Tuttavia, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differisce da Dom: fornisce un nuovo modello a oggetti più leggero e semplice da usare e che sfrutta i vantaggi delle funzionalità del linguaggio in Visual Basic.  
  
 Il vantaggio più importante di è costituito dall' [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] integrazione con LINQ (Language-Integrated Query). Grazie a tale integrazione è possibile scrivere query sul documento XML in memoria per recuperare raccolte di elementi e di attributi. La funzionalità di query di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è paragonabile a XPath e XQuery, dal punto di vista funzionale ma non sintattico. L'integrazione di LINQ in Visual Basic offre una tipizzazione più forte, il controllo in fase di compilazione e il supporto migliorato del debugger.  
  
 Un altre vantaggio di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], costituito dalla possibilità di usare risultati di query come parametri di costruttori di oggetti <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute>, consente di disporre di un approccio potente per la creazione di alberi XML. Questo approccio, chiamato *costruzione funzionale* consente agli sviluppatori di trasformare facilmente gli alberi XML da una forma all'altra.  
  
 Ad esempio, è possibile avere un ordine d'acquisto XML tipico come descritto in [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) (File XML di esempio: ordine d'acquisto tipico (LINQ to XML). Usando [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], è possibile eseguire la query seguente per ottenere il valore dell'attributo relativo al numero di parte di ciascun articolo incluso dell'ordine di acquisto:  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 Si supponga ancora, ad esempio, di voler creare un elenco, ordinato in base al numero di parte, degli articoli il cui valore è maggiore di 100 dollari. Per ottenere queste informazioni, è possibile eseguire la query seguente:  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 Oltre a queste funzionalità LINQ, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] fornisce un'interfaccia di programmazione XML migliorata. Usando [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile:  
  
- Caricare codice XML da file o flussi.  
  
- Serializzare codice XML in file o flussi.  
  
- Creare codice XML nuovo usando la costruzione funzionale.  
  
- Eseguire una query su codice XML usando assi simili a XPath.  
  
- Modificare l'albero XML in memoria usando metodi quali esempio <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>e <xref:System.Xml.Linq.XElement.SetValue%2A>.  
  
- Convalidare alberi XML usando lo schema XSD.  
  
- Usare una combinazione di queste funzionalità per trasformare strutture ad albero XML da una forma in un altra.  
  
## <a name="creating-xml-trees"></a>Creazione di strutture ad albero XML  
 Uno dei vantaggi più significativi della programmazione con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è rappresentato dalla facilità con cui è possibile creare alberi XML. Ad esempio, per creare un piccolo albero XML, è possibile scrivere il codice nel modo seguente:  
  
```vb  
Dim contacts = _  
<Contacts>  
    <Contact>  
        <Name>Patrick Hines</Name>  
        <Phone Type="Home">206-555-0144</Phone>  
        <Phone Type="Work">425-555-0145</Phone>  
        <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
        </Address>  
    </Contact>  
</Contacts>  
```  
  
 Il compilatore Visual Basic converte i valori letterali XML in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] chiamate al metodo.  
  
 Per ulteriori informazioni, vedere [creazione di alberi XML (Visual Basic)](creating-xml-trees.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq>
- [Introduzione (LINQ to XML)](getting-started-linq-to-xml.md)
- [Cenni preliminari su LINQ to XML in Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)
- [XML](../../language-features/xml/index.md)
