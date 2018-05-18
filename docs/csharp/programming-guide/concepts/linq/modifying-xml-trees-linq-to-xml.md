---
title: Modifica degli alberi XML (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 8ec47e6d-2363-4694-be46-8d5ca4d15fc9
ms.openlocfilehash: 4afb071b5229b3a585ea032effc2985c9a9f7c3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="modifying-xml-trees-linq-to-xml-c"></a>Modifica degli alberi XML (LINQ to XML) (C#)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è un archivio in memoria usato per un albero XML. Dopo aver caricato o analizzato un albero XML da un'origine, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consente di modificare l'albero sul posto e quindi di serializzarlo, salvandolo in un file o inviandolo a un server remoto.  
  
 Per la modifica di un albero sul posto vengono usati determinati metodi, ad esempio <xref:System.Xml.Linq.XContainer.Add%2A>.  
  
 È tuttavia disponibile un altro approccio che prevede l'uso della costruzione funzionale per generare un nuovo albero con una forma diversa. A seconda dei tipi di modifiche che è necessario apportate all'albero XML, e a seconda delle dimensioni della struttura, questo approccio può risultare più affidabile e più semplice da sviluppare. Nel primo argomento di questa sezione vengono messi a confronto questi due approcci.  
  
## <a name="in-this-section"></a>In questa sezione  
  
|Argomento|Descrizione|  
|-----------|-----------------|  
|[Differenze tra la modifica dell'albero XML in memoria e la costruzione funzionale (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)|La modifica di una struttura ad albero XML in memoria viene messa a confronto con la costruzione funzionale.|  
|[Aggiunta di elementi, attributi e nodi a un albero XML (C#)](../../../../csharp/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|Vengono fornite informazioni sull'aggiunta di elementi, attributi o nodi a un albero XML.|  
|[Modifica di elementi, attributi e nodi in un albero XML](../../../../csharp/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|Vengono fornite informazioni sulla modifica di elementi, attributi o nodi esistenti.|  
|[Rimozione di elementi, attributi e nodi da un albero XML (C#)](../../../../csharp/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|Vengono fornite informazioni sulla rimozione di elementi, attributi o nodi da un albero XML.|  
|[Gestione di coppie nome/valore (C#)](../../../../csharp/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|Viene descritto come gestire le informazioni dell'applicazione che è preferibile mantenere come coppie nome/valore, ad esempio informazioni di configurazione o impostazioni globali.|  
|[Procedura: Cambiare lo spazio dei nomi per un intero albero XML (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|Viene illustrato come spostare un albero XML da uno spazio dei nomi a un altro.|  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
