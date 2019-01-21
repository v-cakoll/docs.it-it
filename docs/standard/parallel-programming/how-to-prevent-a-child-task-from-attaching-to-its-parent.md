---
title: "Procedura: evitare l'associazione di un'attività figlio alla relativa attività padre"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7506a57e29b7942bd06141baa2d2b048ed998214
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221531"
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a><span data-ttu-id="c0807-102">Procedura: evitare l'associazione di un'attività figlio alla relativa attività padre</span><span class="sxs-lookup"><span data-stu-id="c0807-102">How to: Prevent a Child Task from Attaching to its Parent</span></span>
<span data-ttu-id="c0807-103">In questo documento viene illustrato come impedire a un'attività figlio di essere associata all'attività padre.</span><span class="sxs-lookup"><span data-stu-id="c0807-103">This document demonstrates how to prevent a child task from attaching to the parent task.</span></span> <span data-ttu-id="c0807-104">L'impedimento dell'associazione di un'attività figlio al relativo padre è utile quando si chiama un componente scritto da terze parti e in cui si utilizzano anche attività.</span><span class="sxs-lookup"><span data-stu-id="c0807-104">Preventing a child task from attaching to its parent is useful when you call a component that is written by a third party and that also uses tasks.</span></span> <span data-ttu-id="c0807-105">Ad esempio, un componente di terze parti in cui si utilizza l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> per creare un oggetto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> può causare problemi nel codice se è in esecuzione prolungata o genera un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="c0807-105">For example, a third-party component that uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> option to create a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object can cause problems in your code if it is long-running or throws an unhandled exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0807-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0807-106">Example</span></span>  
 <span data-ttu-id="c0807-107">Nell'esempio seguente vengono confrontati gli effetti dell'utilizzo delle opzioni predefinite con gli effetti della mancata associazione di un'attività figlio al padre.</span><span class="sxs-lookup"><span data-stu-id="c0807-107">The following example compares the effects of using the default options to the effects of preventing a child task from attaching to the parent.</span></span> <span data-ttu-id="c0807-108">Nell'esempio viene creato un oggetto <xref:System.Threading.Tasks.Task> tramite cui viene chiamata una libreria di terze parti in cui si utilizza anche un oggetto <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="c0807-108">The example creates a <xref:System.Threading.Tasks.Task> object that calls into a third-party library that also uses a <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="c0807-109">Nella libreria di terze parti viene utilizzata l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> per creare l'oggetto <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="c0807-109">The third-party library uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> option to create the <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="c0807-110">Nell'applicazione viene utilizzata l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> per creare l'attività padre.</span><span class="sxs-lookup"><span data-stu-id="c0807-110">The application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option to create the parent task.</span></span> <span data-ttu-id="c0807-111">Questa opzione indica al runtime di rimuovere la specifica <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> nelle attività figlio.</span><span class="sxs-lookup"><span data-stu-id="c0807-111">This option instructs the runtime to remove the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> specification in child tasks.</span></span>  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 <span data-ttu-id="c0807-112">Poiché un'attività padre non viene completata finché non lo sono anche tutte le attività figlio, un'attività figlio di lunga durata può ridurre notevolmente le prestazioni dell'applicazione in generale.</span><span class="sxs-lookup"><span data-stu-id="c0807-112">Because a parent task does not finish until all child tasks finish, a long-running child task can cause the overall application to perform poorly.</span></span> <span data-ttu-id="c0807-113">In questo esempio, quando nell'applicazione vengono utilizzate le opzioni predefinite per creare l'attività padre, l'attività figlio deve essere completata prima di quella del padre.</span><span class="sxs-lookup"><span data-stu-id="c0807-113">In this example, when the application uses the default options to create the parent task, the child task must finish before the parent task finishes.</span></span> <span data-ttu-id="c0807-114">Quando nell'applicazione viene utilizzata l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>, l'elemento figlio non è associato al padre.</span><span class="sxs-lookup"><span data-stu-id="c0807-114">When the application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option, the child is not attached to the parent.</span></span> <span data-ttu-id="c0807-115">Pertanto, tramite l'applicazione è possibile eseguire lavoro aggiuntivo al termine dell'attività padre e prima dell'attesa del completamento dell'attività figlio.</span><span class="sxs-lookup"><span data-stu-id="c0807-115">Therefore, the application can perform additional work after the parent task finishes and before it must wait for the child task to finish.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c0807-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c0807-116">Compiling the Code</span></span>  
 <span data-ttu-id="c0807-117">Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `DenyChildAttach.cs` (`DenyChildAttach.vb` per Visual Basic) e quindi eseguire il comando riportato di seguito in una finestra del prompt dei comandi per gli sviluppatori per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c0807-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DenyChildAttach.cs` (`DenyChildAttach.vb` for Visual Basic), and then run the following command in a Developer Command Prompt for Visual Studio window.</span></span>  
  
 <span data-ttu-id="c0807-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="c0807-118">Visual C#</span></span>  
  
 <span data-ttu-id="c0807-119">**csc.exe DenyChildAttach.cs**</span><span class="sxs-lookup"><span data-stu-id="c0807-119">**csc.exe DenyChildAttach.cs**</span></span>  
  
 <span data-ttu-id="c0807-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c0807-120">Visual Basic</span></span>  
  
 <span data-ttu-id="c0807-121">**vbc.exe DenyChildAttach.vb**</span><span class="sxs-lookup"><span data-stu-id="c0807-121">**vbc.exe DenyChildAttach.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c0807-122">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="c0807-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0807-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0807-123">See also</span></span>

- [<span data-ttu-id="c0807-124">Programmazione asincrona basata su attività</span><span class="sxs-lookup"><span data-stu-id="c0807-124">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
