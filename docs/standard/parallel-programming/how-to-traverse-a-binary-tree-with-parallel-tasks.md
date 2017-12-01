---
title: "Procedura: Attraversare un albero binario con attività in parallelo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c029a763faaa0b4d6ea5612efe079e47415b6fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>Procedura: Attraversare un albero binario con attività in parallelo
Nell'esempio seguente vengono illustrati due i modi in cui è possibile utilizzare l'attività in parallelo per attraversare una struttura di dati. La creazione dell'albero stesso viene lasciata come un esercizio.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 I due metodi illustrati sono funzionalmente equivalenti. Tramite il <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> metodo per creare ed eseguire le attività, si ottiene un handle di attività che può essere utilizzata per attendere le attività e gestire le eccezioni.  
  
## <a name="see-also"></a>Vedere anche  
 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
