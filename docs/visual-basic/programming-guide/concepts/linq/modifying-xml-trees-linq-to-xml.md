---
title: Modifica degli alberi XML (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
ms.openlocfilehash: 3402188c4e34ef81bad41ed49f9236b4fb7c47ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406885"
---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a>Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è un archivio in memoria usato per un albero XML. Dopo aver caricato o analizzato un albero XML da un'origine, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consente di modificare l'albero sul posto e quindi di serializzarlo, salvandolo in un file o inviandolo a un server remoto.  
  
 Per la modifica di un albero sul posto vengono usati determinati metodi, ad esempio <xref:System.Xml.Linq.XContainer.Add%2A>.  
  
 È tuttavia disponibile un altro approccio che prevede l'uso della costruzione funzionale per generare un nuovo albero con una forma diversa. A seconda dei tipi di modifiche che è necessario apportate all'albero XML, e a seconda delle dimensioni della struttura, questo approccio può risultare più affidabile e più semplice da sviluppare. Nel primo argomento di questa sezione vengono messi a confronto questi due approcci.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
  
|Argomento|Descrizione|  
|-----------|-----------------|  
|[Modifica dell'albero XML in memoria rispetto alla costruzione funzionale (LINQ to XML) (Visual Basic)](in-memory-xml-tree-modification-vs-functional-construction.md)|La modifica di una struttura ad albero XML in memoria viene messa a confronto con la costruzione funzionale.|  
|[Aggiunta di elementi, attributi e nodi a un albero XML (Visual Basic)](adding-elements-attributes-and-nodes-to-an-xml-tree.md)|Vengono fornite informazioni sull'aggiunta di elementi, attributi o nodi a un albero XML.|  
|[Modifica di elementi, attributi e nodi in un albero XML](modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|Vengono fornite informazioni sulla modifica di elementi, attributi o nodi esistenti.|  
|[Rimozione di elementi, attributi e nodi da un albero XML (Visual Basic)](removing-elements-attributes-and-nodes-from-an-xml-tree.md)|Vengono fornite informazioni sulla rimozione di elementi, attributi o nodi da un albero XML.|  
|[Gestione delle coppie nome/valore (Visual Basic)](maintaining-name-value-pairs.md)|Viene descritto come gestire le informazioni dell'applicazione che è preferibile mantenere come coppie nome/valore, ad esempio informazioni di configurazione o impostazioni globali.|  
|[Procedura: modificare lo spazio dei nomi per un intero albero XML (Visual Basic)](how-to-change-the-namespace-for-an-entire-xml-tree.md)|Viene illustrato come spostare un albero XML da uno spazio dei nomi a un altro.|  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori (LINQ to XML) (Visual Basic)](programming-guide-linq-to-xml.md)
