---
title: Programmazione funzionale e procedurale (LINQ to XML) (C
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: e87114d2edcda4b2df14eb2d84f62ebe9638b5eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69594257"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a>Programmazione funzionale e procedurale (LINQ to XML) (C
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
  
 Per vedere i due approcci a contrasto, vedere Modifica della struttura [ad albero XML in memoria e costruzione funzionale (LINQ to XML) (C )](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).  
  
 Per un'esercitazione sulla scrittura delle trasformazioni funzionali, vedere [Trasformazioni funzionali pure di XML (C#)](./introduction-to-pure-functional-transformations.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della programmazione con LINQ to XML (C#)](./linq-to-xml-overview.md)
