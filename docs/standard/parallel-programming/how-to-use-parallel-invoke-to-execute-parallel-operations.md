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
ms.openlocfilehash: f61bbf10bbeef736f66710f50e621c3619355a1d
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635794"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Procedura: utilizzare Parallel.Invoke per eseguire operazioni in parallelo

Questo esempio mostra come parallelizzare le operazioni usando <xref:System.Threading.Tasks.Parallel.Invoke%2A> in Task Parallel Library. Vengono eseguite tre operazioni in un'origine dati condivisa. Le operazioni possono essere eseguite in parallelo in modo semplice, perché nessuna di esse modifica l'origine.

> [!NOTE]
> Questa documentazione usa espressioni lambda per definire delegati in TPL. Se non si ha familiarità con le espressioni lambda in Visual Basic o in Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Esempio

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

Con <xref:System.Threading.Tasks.Parallel.Invoke%2A>, è sufficiente esprimere le azioni che si desidera eseguire contemporaneamente e il runtime gestisce tutti i dettagli di pianificazione dei thread, incluso il ridimensionamento automatico in base al numero di core nel computer host.

Questo esempio parallelizza le operazioni, ma non i dati. Come approccio alternativo, è possibile parallelizzare le query LINQ usando PLINQ ed eseguire le query in sequenza. In alternativa, è possibile parallelizzare i dati usando PLINQ. Un'altra possibilità consiste nel parallelizzare sia le query che le attività. Anche se l'overhead risultante potrebbe ridurre le prestazioni nei computer host con relativamente pochi processori, è scalabile meglio su computer con molti processori.

## <a name="compile-the-code"></a>Compilare il codice

Copiare e incollare l'esempio completo in un progetto di Microsoft Visual Studio e premere **F5**.

## <a name="see-also"></a>Vedere anche

- [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)
- [Procedura: annullare un'attività e i relativi figli](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
