---
title: Parallel LINQ (PLINQ)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ, overview
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fe7edffd53023cba6dac1454e620d6e0d7e9513
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210195"
---
# <a name="parallel-linq-plinq"></a>Parallel LINQ (PLINQ)
Parallel LINQ (PLINQ) è un'implementazione parallela di LINQ to Objects. PLINQ implementa il set completo di operatori di query standard LINQ come metodi di estensione per lo spazio dei nomi <xref:System.Linq> e dispone di operatori aggiuntivi per le operazioni parallele. PLINQ combina la semplicità e la leggibilità della sintassi di LINQ con la potenza di programmazione in parallelo. Proprio come il codice destinato alla Task Parallel Library, le query di PLINQ ridimensionano il livello di concorrenza in base alle funzionalità del computer host.  
  
 In molti scenari, PLINQ può aumentare notevolmente la velocità delle query di LINQ to Objects usando tutti i core disponibili nel computer host in modo più efficiente. Il miglioramento nella prestazione comporta una potenza di elaborazione ad alte prestazioni sul desktop.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Introduzione a PLINQ](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [Conservazione dell'ordine in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [Opzioni di merge in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [Procedura: Creare ed eseguire una query PLINQ semplice](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [Procedura: Controllare l'ordine in una query PLINQ](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [Procedura: Combinare query LINQ parallele e sequenziali](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [Procedura: Gestire le eccezioni in una query PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [Procedura: Annullare una query PLINQ](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [Procedura: Scrivere una funzione di aggregazione PLINQ personalizzata](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [Procedura: Specificare la modalità di esecuzione in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [Procedura: Specificare le opzioni di merge in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [Procedura: Scorrere le directory dei file con PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [Procedura: Misurare le prestazioni di esecuzione delle query di PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.ParallelEnumerable>  
- [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)  
- [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
