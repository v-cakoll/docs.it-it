---
title: "Procedura: Evitare l'associazione di un'attività figlio alla relativa attività padre"
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 654bfec4e8ba163c9dc9adf470c45401c0babd8b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a>Procedura: Evitare l'associazione di un'attività figlio alla relativa attività padre
In questo documento viene illustrato come impedire a un'attività figlio di essere associata all'attività padre. L'impedimento dell'associazione di un'attività figlio al relativo padre è utile quando si chiama un componente scritto da terze parti e in cui si utilizzano anche attività. Ad esempio, un componente di terze parti in cui si utilizza l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> per creare un oggetto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> può causare problemi nel codice se è in esecuzione prolungata o genera un'eccezione non gestita.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono confrontati gli effetti dell'utilizzo delle opzioni predefinite con gli effetti della mancata associazione di un'attività figlio al padre. Nell'esempio viene creato un oggetto <xref:System.Threading.Tasks.Task> tramite cui viene chiamata una libreria di terze parti in cui si utilizza anche un oggetto <xref:System.Threading.Tasks.Task>. Nella libreria di terze parti viene utilizzata l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> per creare l'oggetto <xref:System.Threading.Tasks.Task>. Nell'applicazione viene utilizzata l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> per creare l'attività padre. Questa opzione indica al runtime di rimuovere la specifica <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> nelle attività figlio.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Poiché un'attività padre non viene completata finché non lo sono anche tutte le attività figlio, un'attività figlio di lunga durata può ridurre notevolmente le prestazioni dell'applicazione in generale. In questo esempio, quando nell'applicazione vengono utilizzate le opzioni predefinite per creare l'attività padre, l'attività figlio deve essere completata prima di quella del padre. Quando nell'applicazione viene utilizzata l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>, l'elemento figlio non è associato al padre. Pertanto, tramite l'applicazione è possibile eseguire lavoro aggiuntivo al termine dell'attività padre e prima dell'attesa del completamento dell'attività figlio.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `DenyChildAttach.cs` (`DenyChildAttach.vb` per Visual Basic) e quindi eseguire il comando riportato di seguito in una finestra del prompt dei comandi di Visual Studio.  
  
 Visual C#  
  
 **csc.exe DenyChildAttach.cs**  
  
 Visual Basic  
  
 **vbc.exe DenyChildAttach.vb**  
  
## <a name="robust-programming"></a>Programmazione efficiente  
  
## <a name="see-also"></a>Vedere anche  
 [Programmazione asincrona basata su attività](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
