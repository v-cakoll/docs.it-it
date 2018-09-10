---
title: 'Procedura: scollegare i blocchi di flussi di dati'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc0f266169a2d82bb76355febd58b2268907fe97
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44251560"
---
# <a name="how-to-unlink-dataflow-blocks"></a><span data-ttu-id="ab272-102">Procedura: scollegare i blocchi di flussi di dati</span><span class="sxs-lookup"><span data-stu-id="ab272-102">How to: Unlink Dataflow Blocks</span></span>
<span data-ttu-id="ab272-103">In questo documento viene descritto come scollegare un blocco di flussi di dati di destinazione dalla relativa origine.</span><span class="sxs-lookup"><span data-stu-id="ab272-103">This document describes how to unlink a target dataflow block from its source.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a><span data-ttu-id="ab272-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab272-104">Example</span></span>  
 <span data-ttu-id="ab272-105">Nell'esempio seguente vengono creati tre oggetti <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, tramite ognuno dei quali viene chiamato il metodo `TrySolution` per calcolare un valore.</span><span class="sxs-lookup"><span data-stu-id="ab272-105">The following example creates three <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objects, each of which calls the `TrySolution` method to compute a value.</span></span> <span data-ttu-id="ab272-106">Per questo esempio è necessario solo il risultato della prima chiamata a `TrySolution` per il completamento.</span><span class="sxs-lookup"><span data-stu-id="ab272-106">This example requires only the result from the first call to `TrySolution` to finish.</span></span>  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 <span data-ttu-id="ab272-107">Per ricevere il valore dal primo oggetto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> completato, nell'esempio viene definito il metodo `ReceiveFromAny(T)`.</span><span class="sxs-lookup"><span data-stu-id="ab272-107">To receive the value from the first <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object that finishes, this example defines the `ReceiveFromAny(T)` method.</span></span> <span data-ttu-id="ab272-108">Il metodo `ReceiveFromAny(T)` accetta una matrice di oggetti <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> e tramite esso viene collegato ognuno di questi oggetti a un oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="ab272-108">The `ReceiveFromAny(T)` method accepts an array of <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objects and links each of these objects to a <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="ab272-109">Quando si utilizza il metodo <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> per collegare un blocco di flussi di dati di origine a un blocco di destinazione, tramite l'origine i messaggi vengono propagati nella destinazione quando i dati diventano disponibili.</span><span class="sxs-lookup"><span data-stu-id="ab272-109">When you use the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method to link a source dataflow block to a target block, the source propagates messages to the target as data becomes available.</span></span> <span data-ttu-id="ab272-110">Poiché la classe <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> accetta solo il primo messaggio offerto, tramite il metodo `ReceiveFromAny(T)` viene generato il relativo risultato chiamando il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>.</span><span class="sxs-lookup"><span data-stu-id="ab272-110">Because the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> class accepts only the first message that it is offered, the `ReceiveFromAny(T)` method produces its result by calling the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method.</span></span> <span data-ttu-id="ab272-111">In questo modo viene generato il primo messaggio offerto all'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="ab272-111">This produces the first message that is offered to the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="ab272-112">Il metodo <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> ha una versione sottoposta a overload che accetta un oggetto <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions> con una proprietà <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.MaxMessages> che, quando viene impostata su `1`, indica al blocco di origine di scollegarsi dalla destinazione dopo la ricezione di un messaggio dall'origine da parte della destinazione.</span><span class="sxs-lookup"><span data-stu-id="ab272-112">The <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method has an overloaded version that takes an <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions> object with a <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.MaxMessages> property that, when it is set to `1`, instructs the source block to unlink from the target after the target receives one message from the source.</span></span> <span data-ttu-id="ab272-113">È importante per l'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> scollegarsi dalle relative origini perché la relazione tra la matrice delle origini e l'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> non è più richiesta dopo la ricezione di un messaggio da parte dell'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="ab272-113">It is important for the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object to unlink from its sources because the relationship between the array of sources and the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object is no longer required after the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object receives a message.</span></span>  
  
 <span data-ttu-id="ab272-114">Per abilitare il completamento delle chiamate rimanenti a `TrySolution` dopo che tramite una di esse viene calcolato un valore, il metodo `TrySolution` accetta un oggetto <xref:System.Threading.CancellationToken> che viene annullato dopo che la chiamata a `ReceiveFromAny(T)` ha restituito un valore.</span><span class="sxs-lookup"><span data-stu-id="ab272-114">To enable the remaining calls to `TrySolution` to end after one of them computes a value, the `TrySolution` method takes a <xref:System.Threading.CancellationToken> object that is canceled after the call to `ReceiveFromAny(T)` returns.</span></span> <span data-ttu-id="ab272-115">Tramite il metodo <xref:System.Threading.SpinWait.SpinUntil%2A> viene restituito un valore quando questo oggetto <xref:System.Threading.CancellationToken> viene annullato.</span><span class="sxs-lookup"><span data-stu-id="ab272-115">The <xref:System.Threading.SpinWait.SpinUntil%2A> method returns when this <xref:System.Threading.CancellationToken> object is canceled.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab272-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ab272-116">Compiling the Code</span></span>  
 <span data-ttu-id="ab272-117">Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` per Visual Basic) e quindi eseguire il comando riportato di seguito in una finestra del prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ab272-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="ab272-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="ab272-118">Visual C#</span></span>  
  
 <span data-ttu-id="ab272-119">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span><span class="sxs-lookup"><span data-stu-id="ab272-119">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span></span>  
  
 <span data-ttu-id="ab272-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab272-120">Visual Basic</span></span>  
  
 <span data-ttu-id="ab272-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span><span class="sxs-lookup"><span data-stu-id="ab272-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span></span>  

## <a name="see-also"></a><span data-ttu-id="ab272-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab272-122">See also</span></span>

- [<span data-ttu-id="ab272-123">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="ab272-123">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
