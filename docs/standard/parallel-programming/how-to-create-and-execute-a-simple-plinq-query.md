---
title: 'Procedura: Creare ed eseguire una query PLINQ semplice'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: a9c044254423d0f9d266539c728a6604f562e97d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290006"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a>Procedura: Creare ed eseguire una query PLINQ semplice

Nell'esempio riportato in questo articolo viene illustrato come creare una semplice query LINQ (Parallel Language Integrated Query) utilizzando il <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> metodo di estensione sulla sequenza di origine ed eseguendo la query tramite il <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithTyp> metodo.  
  
> [!NOTE]
> Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ. Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 Questo esempio illustra il modello di base per la creazione e l'esecuzione di qualsiasi query LINQ parallela quando l'ordinamento della sequenza di risultati non è importante. Le query non ordinate sono in genere più veloci rispetto alle query ordinate. La query partiziona l'origine in attività eseguita in modo asincrono su più thread. L'ordine di completamento di ogni attività dipende non solo dalla quantità di lavoro necessario per l'elaborazione degli elementi nella partizione, ma anche da fattori esterni, ad esempio il modo in cui il sistema operativo pianifica ogni thread. Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md). Per altre informazioni su come mantenere l'ordinamento degli elementi in una query, vedere [Procedura: Controllare l'ordinamento in una query PLINQ](how-to-control-ordering-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
