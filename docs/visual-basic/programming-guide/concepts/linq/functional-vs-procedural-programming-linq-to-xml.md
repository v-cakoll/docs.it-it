---
title: Programmazione Programmazione procedurale (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: ea1015a5-d4c8-4d79-8e1e-ba17a40a4f39
ms.openlocfilehash: 0b525f13298e7402369b890516434cec47e01542
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398435"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-visual-basic"></a>Programmazione funzionale e procedurale (LINQ to XML) (Visual Basic)
Sono disponibili diversi tipi di applicazioni XML:  
  
- In alcune applicazioni da documenti XML di origine vengono prodotti nuovi documenti XML con una forma diversa.  
  
- In alcune applicazioni da documenti XML di origine vengono prodotti documenti risultanti in un formato completamente diverso, ad esempio file di testo CSV o HTML.  
  
- In alcune applicazioni da documenti XML di origine vengono inseriti record in un database.  
  
- In alcune applicazioni dai dati di un'altra origine, ad esempio un database, vengono creati documenti XML.  
  
 Quelli elencati non sono tutti i tipi di applicazioni XML disponibili, ma sono rappresentativi dei tipi di funzionalità che i programmatori XML devono implementare.  
  
 Con tutti questi tipi di applicazioni, gli sviluppatori possono adottare due approcci completamente diversi:  
  
- Costruzione funzionale usando un approccio dichiarativo.  
  
- Modifica dell'albero XML in memoria usando codice procedurale.  
  
 In LINQ to XML sono supportati entrambi gli approcci.  
  
 Quando si usa l'approccio funzionale, vengono scritte trasformazioni che dai documenti di origine generano documenti completamente nuovi con la forma desiderata.  
  
 Quando si modifica un albero XML sul posto, viene scritto un codice che attraversa e si sposta attraverso i nodi in un albero XML in memoria, inserendo, eliminando e modificando i nodi secondo necessità.  
  
 È possibile usare LINQ to XML con uno di questi due approcci. Si usano le stesse classe e in alcuni casi gli stessi metodi. Tuttavia, la struttura e gli obiettivi dei due approcci sono molto diversi. In situazioni diverse, ad esempio, un approccio offre in genere prestazioni più elevate dell'altro e usa una quantità maggiore o minore di memoria. Inoltre, un approccio sarà più facile da scrivere dell'altro e produrrà codice più facilmente gestibile.  
  
 Per visualizzare i due approcci contrapposti, vedere la pagina relativa alla [modifica dell'albero XML in memoria rispetto alla costruzione funzionale (LINQ to XML) (Visual Basic)](in-memory-xml-tree-modification-vs-functional-construction.md).  
  
 Per un'esercitazione sulla scrittura di trasformazioni funzionali, vedere la pagina relativa alle [trasformazioni funzionali pure di XML (Visual Basic)](pure-functional-transformations-of-xml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della programmazione LINQ to XML (Visual Basic)](linq-to-xml-programming-overview.md)
