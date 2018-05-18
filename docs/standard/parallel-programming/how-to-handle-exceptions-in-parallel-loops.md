---
title: 'Procedura: gestire le eccezioni nei cicli paralleli'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11ba240d71287be91bd0b4b40a2cb69f6e2808d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a>Procedura: gestire le eccezioni nei cicli paralleli
Gli overload dei metodi <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> non presentano alcun meccanismo speciale per gestire le eccezioni eventualmente generate. Sotto questo aspetto assomigliano ai cicli `for` e `foreach` (`For` e `For Each`in Visual Basic) normali; un'eccezione non gestita fa sì che il ciclo termini immediatamente.  
  
 Quando si aggiunge una logica personalizzata di gestione delle eccezioni nei cicli paralleli, gestire il caso della generazione simultanea di eccezioni simili in più thread e il caso in cui un'eccezione generata in un determinato thread comporta la generazione di un'altra eccezione in un altro thread. Per gestire entrambi questi casi è possibile eseguire il wrapping di tutte le eccezioni del ciclo in un oggetto <xref:System.AggregateException?displayProperty=nameWithType>. L'esempio seguente mostra uno degli approcci possibili.  
  
> [!NOTE]
>  Quando "Just My Code" è abilitato, Visual Studio in alcuni casi si interromperà in corrispondenza della riga che genera l'eccezione e visualizzerà un messaggio di errore simile a "Eccezione non gestita dal codice utente". Questo errore non è grave. È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti. Per impedire l'interruzione di Visual Studio al primo errore, deselezionare semplicemente la casella di controllo "Just My Code" in **Strumenti, Opzioni, Debug, Generale**.  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono rilevate tutte le eccezioni e quindi ne viene eseguito il wrapping in un oggetto <xref:System.AggregateException?displayProperty=nameWithType> che viene generato. Il chiamante può decidere quali eccezioni gestire.  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a>Vedere anche  
 [Parallelismo dei dati](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
