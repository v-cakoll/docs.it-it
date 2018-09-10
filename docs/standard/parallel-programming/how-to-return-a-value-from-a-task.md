---
title: "Procedura: Restituire un valore da un'attività"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2af0f82e66da1c8db5e17863dfad861c8a7d195e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44217217"
---
# <a name="how-to-return-a-value-from-a-task"></a>Procedura: Restituire un valore da un'attività
In questo esempio viene illustrato come usare il tipo <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> per restituire un valore dalla proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>. È necessaria la presenza della directory C:\Users\Public\Pictures\Sample Pictures\ e che in essa siano contenuti dei file.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 La proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> blocca il thread chiamante fino al termine dell'attività.  
  
 Per informazioni su come passare il risultato di un oggetto <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> a un'attività di continuazione, vedere [Concatenamento di attività tramite attività di continuazione](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione asincrona basata su attività](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
- [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
