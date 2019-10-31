---
title: 'Procedura: Attraversare un albero binario con attività in parallelo'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
ms.openlocfilehash: b79337e6ee8057506ff87c696cecd6b038eeebfc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141637"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="8bd1a-102">Procedura: Attraversare un albero binario con attività in parallelo</span><span class="sxs-lookup"><span data-stu-id="8bd1a-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="8bd1a-103">L'esempio seguente mostra due modi in cui è possibile usare le attività parallele per attraversare una struttura dei dati ad albero.</span><span class="sxs-lookup"><span data-stu-id="8bd1a-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="8bd1a-104">La creazione dell'albero stesso viene svolta come esercizio.</span><span class="sxs-lookup"><span data-stu-id="8bd1a-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bd1a-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="8bd1a-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="8bd1a-106">I due metodi illustrati sono equivalenti dal punto di vista funzionale.</span><span class="sxs-lookup"><span data-stu-id="8bd1a-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="8bd1a-107">Usando il metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> per creare ed eseguire le attività, si ottiene un handle dalle attività che è possibile usare per attendere le attività e gestire le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="8bd1a-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd1a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bd1a-108">See also</span></span>

- [<span data-ttu-id="8bd1a-109">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="8bd1a-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
