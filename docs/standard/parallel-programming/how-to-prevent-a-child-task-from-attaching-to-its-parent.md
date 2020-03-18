---
title: "Procedura: Evitare l'associazione di un'attività figlio alla relativa attività padre"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
ms.openlocfilehash: 265b6d06f17a1dfbee3f009feff1ee1645e62a46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139252"
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a>Procedura: Evitare l'associazione di un'attività figlio alla relativa attività padre
In questo documento viene illustrato come impedire a un'attività figlio di essere associata all'attività padre. L'impedimento dell'associazione di un'attività figlio al relativo padre è utile quando si chiama un componente scritto da terze parti e in cui si utilizzano anche attività. Ad esempio, un componente di terze parti in cui si utilizza l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> per creare un oggetto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> può causare problemi nel codice se è in esecuzione prolungata o genera un'eccezione non gestita.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono confrontati gli effetti dell'utilizzo delle opzioni predefinite con gli effetti della mancata associazione di un'attività figlio al padre. Nell'esempio viene creato un oggetto <xref:System.Threading.Tasks.Task> tramite cui viene chiamata una libreria di terze parti in cui si utilizza anche un oggetto <xref:System.Threading.Tasks.Task>. Nella libreria di terze parti viene utilizzata l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> per creare l'oggetto <xref:System.Threading.Tasks.Task>. Nell'applicazione viene utilizzata l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> per creare l'attività padre. Questa opzione indica al runtime di rimuovere la specifica <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> nelle attività figlio.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Poiché un'attività padre non viene completata finché non lo sono anche tutte le attività figlio, un'attività figlio di lunga durata può ridurre notevolmente le prestazioni dell'applicazione in generale. In questo esempio, quando nell'applicazione vengono utilizzate le opzioni predefinite per creare l'attività padre, l'attività figlio deve essere completata prima di quella del padre. Quando nell'applicazione viene utilizzata l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>, l'elemento figlio non è associato al padre. Pertanto, tramite l'applicazione è possibile eseguire lavoro aggiuntivo al termine dell'attività padre e prima dell'attesa del completamento dell'attività figlio.  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione asincrona basata su attivitàTask-based Asynchronous Programming](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
