---
title: "Procedura: Restituire un valore da un'attività"
description: Vedere come usare il tipo System. Threading. Tasks. Task <TResult> per restituire un valore dalla proprietà Result in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 051cef7cac654e4369ec1486884876004370ba0b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767975"
---
# <a name="how-to-return-a-value-from-a-task"></a>Procedura: Restituire un valore da un'attività
In questo esempio viene illustrato come usare il tipo <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> per restituire un valore dalla proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>. È necessaria la presenza della directory C:\Users\Public\Pictures\Sample Pictures\ e che in essa siano contenuti dei file.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 La proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> blocca il thread chiamante fino al termine dell'attività.  
  
 Per informazioni su come passare il risultato di un oggetto <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> a un'attività di continuazione, vedere [Concatenamento di attività tramite attività di continuazione](chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione asincrona basata su attività](task-based-asynchronous-programming.md)
- [Espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md)
