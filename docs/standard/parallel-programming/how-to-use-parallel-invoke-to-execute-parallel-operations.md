---
title: 'Procedura: Usare Parallel.Invoke per eseguire operazioni parallele'
description: Vedere come usare il metodo Parallel. Invoke nella Task Parallel Library (TPL), che esegue operazioni parallele su un'origine dati condivisa in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: 084ade48b1406d23a11eb311739525f35ac973df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596345"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Procedura: Usare Parallel.Invoke per eseguire operazioni parallele

Questo esempio mostra come parallelizzare le operazioni usando <xref:System.Threading.Tasks.Parallel.Invoke%2A> in Task Parallel Library. Vengono eseguite tre operazioni in un'origine dati condivisa. Le operazioni possono essere eseguite in parallelo in modo semplice, perché nessuna modifica l'origine.

> [!NOTE]
> Questa documentazione usa espressioni lambda per definire delegati in TPL. Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Esempio

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

Con <xref:System.Threading.Tasks.Parallel.Invoke%2A> , è sufficiente esprimere le azioni che si desidera eseguire simultaneamente e il runtime gestisce tutti i dettagli di pianificazione dei thread, inclusa la scalabilità automatica al numero di core nel computer host.

Questo esempio parallelizza le operazioni, ma non i dati. Come approccio alternativo, è possibile parallelizzare le query LINQ usando PLINQ ed eseguire le query in sequenza. In alternativa, è possibile parallelizzare i dati usando PLINQ. Un'altra possibilità consiste nel parallelizzare sia le query che le attività. Anche se il sovraccarico risultante potrebbe compromettere le prestazioni nei computer host con un numero relativamente basso di processori, la scalabilità è migliore nei computer con molti processori.

## <a name="compile-the-code"></a>Compilare il codice

Copiare e incollare l'esempio completo in un progetto di Microsoft Visual Studio e premere **F5**.

## <a name="see-also"></a>Vedere anche

- [Programmazione parallela](index.md)
- [Procedura: Annullare un'attività e i relativi figli](how-to-cancel-a-task-and-its-children.md)
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
