---
title: Programmazione Funzionale e programmazione procedurale (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ea1015a5-d4c8-4d79-8e1e-ba17a40a4f39
ms.openlocfilehash: d5db2f686d72390cdb7e338235a39e4039281e6f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645002"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-visual-basic"></a>Programmazione Funzionale e programmazione procedurale (LINQ to XML) (Visual Basic)
Sono disponibili diversi tipi di applicazioni XML:  
  
-   In alcune applicazioni da documenti XML di origine vengono prodotti nuovi documenti XML con una forma diversa.  
  
-   In alcune applicazioni da documenti XML di origine vengono prodotti documenti risultanti in un formato completamente diverso, ad esempio file di testo CSV o HTML.  
  
-   In alcune applicazioni da documenti XML di origine vengono inseriti record in un database.  
  
-   In alcune applicazioni dai dati di un'altra origine, ad esempio un database, vengono creati documenti XML.  
  
 Quelli elencati non sono tutti i tipi di applicazioni XML disponibili, ma sono rappresentativi dei tipi di funzionalità che i programmatori XML devono implementare.  
  
 Con tutti questi tipi di applicazioni, gli sviluppatori possono adottare due approcci completamente diversi:  
  
-   Costruzione funzionale usando un approccio dichiarativo.  
  
-   Modifica dell'albero XML in memoria usando codice procedurale.  
  
 In LINQ to XML sono supportati entrambi gli approcci.  
  
 Quando si usa l'approccio funzionale, vengono scritte trasformazioni che dai documenti di origine generano documenti completamente nuovi con la forma desiderata.  
  
 Quando si modifica un albero XML sul posto, viene scritto un codice che attraversa e si sposta attraverso i nodi in un albero XML in memoria, inserendo, eliminando e modificando i nodi secondo necessità.  
  
 È possibile usare LINQ to XML con uno di questi due approcci. Si usano le stesse classe e in alcuni casi gli stessi metodi. Tuttavia, la struttura e gli obiettivi dei due approcci sono molto diversi. In situazioni diverse, ad esempio, un approccio offre in genere prestazioni più elevate dell'altro e usa una quantità maggiore o minore di memoria. Inoltre, un approccio sarà più facile da scrivere dell'altro e produrrà codice più facilmente gestibile.  
  
 Per un confronto tra i due approcci, vedere [Differenze tra la modifica dell'albero XML in memoria e Costruzione funzionale (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md).  
  
 Per un'esercitazione sulla scrittura delle trasformazioni funzionali, vedere [trasformazioni funzionali Pure di XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).  
  
## <a name="see-also"></a>Vedere anche
- [LINQ to XML Panoramica della programmazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
