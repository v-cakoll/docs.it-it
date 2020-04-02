---
title: 'Procedura: utilizzare Parallel.Invoke per eseguire operazioni in parallelo'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: 7189c478e132a41971a364b833f0fabda6ff84d4
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588406"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Procedura: utilizzare Parallel.Invoke per eseguire operazioni in parallelo

Questo esempio mostra come parallelizzare le operazioni usando <xref:System.Threading.Tasks.Parallel.Invoke%2A> in Task Parallel Library. Vengono eseguite tre operazioni in un'origine dati condivisa. Poiché nessuna delle operazioni modifica l'origine, possono essere eseguite in parallelo in modo semplice.

> [!NOTE]
> Questa documentazione usa espressioni lambda per definire delegati in TPL. Se non si ha familiarità con le espressioni lambda in Visual Basic o in Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Esempio

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

Si noti che con <xref:System.Threading.Tasks.Parallel.Invoke%2A>, basta indicare le azioni che si desidera eseguire simultaneamente e il runtime gestisce tutti i dettagli di pianificazione dei thread, tra cui l'adattamento automatico al numero di core nel computer host.

Questo esempio parallelizza le operazioni, ma non i dati. Come approccio alternativo, è possibile parallelizzare le query LINQ usando PLINQ ed eseguire le query in sequenza. In alternativa, è possibile parallelizzare i dati usando PLINQ. Un'altra possibilità consiste nel parallelizzare sia le query che le attività. Anche se il sovraccarico risultante potrebbe comportare problemi di prestazioni nei computer host con un numero relativamente basso di processori, la scalabilità sarebbe decisamente migliore nei computer con molti processori.

## <a name="compile-the-code"></a>Compilare il codice

Copiare e incollare l'esempio completo in un progetto di Microsoft Visual Studio e premere **F5**.

## <a name="see-also"></a>Vedere anche

- [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)
- [Procedura: annullare un'attività e i relativi figli](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
