---
title: Query di aggregazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4aa6c0a9103bc4a906ecdfb51a55069e6b8b790
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="aggregate-queries"></a>Query di aggregazione
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono supportati gli operatori di aggregazione `Average`, `Count`, `Max`, `Min` e `Sum`. Di seguito sono riportate le caratteristiche degli operatori di aggregazione in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:  
  
-   Le query di aggregazione vengono eseguite immediatamente.  
  
     Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
-   Le query di aggregazione restituiscono in genere un numero anziché una raccolta.  
  
     Per ulteriori informazioni, vedere [operazioni di aggregazione](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4).  
  
-   Non è possibile chiamare aggregati per tipi anonimi.  
  
 Gli esempi negli argomenti riportati di seguito derivano dal database di esempio Northwind. Per ulteriori informazioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Restituire il valore medio da una sequenza numerica](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Average%2A>.  
  
 [Contare il numero di elementi in una sequenza](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Count%2A>.  
  
 [Trovare il valore massimo in una sequenza numerica](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Max%2A>.  
  
 [Trovare il valore minimo in una sequenza numerica](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Min%2A>.  
  
 [Calcolare la somma dei valori in una sequenza numerica](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Sum%2A>.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 Vengono forniti i collegamenti alle query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in Visual Basic e C#.  
  
 [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 Vengono forniti i collegamenti ad argomenti in cui sono descritti i concetti per la progettazione di query [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 Viene spiegato il funzionamento delle query in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].
