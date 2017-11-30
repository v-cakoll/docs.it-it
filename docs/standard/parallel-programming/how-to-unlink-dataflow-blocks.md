---
title: 'Procedura: scollegare i blocchi di flussi di dati'
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
helpviewer_keywords:
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41f1b83fab6ff44e69ac2f010f70e6e254341f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-unlink-dataflow-blocks"></a><span data-ttu-id="e43c1-102">Procedura: scollegare i blocchi di flussi di dati</span><span class="sxs-lookup"><span data-stu-id="e43c1-102">How to: Unlink Dataflow Blocks</span></span>
<span data-ttu-id="e43c1-103">In questo documento viene descritto come scollegare un blocco di flussi di dati di destinazione dalla relativa origine.</span><span class="sxs-lookup"><span data-stu-id="e43c1-103">This document describes how to unlink a target dataflow block from its source.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="e43c1-104">La libreria del flusso di dati TPL (spazio dei nomi <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) non viene distribuita con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e43c1-104">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="e43c1-105">Per installare il <xref:System.Threading.Tasks.Dataflow> dello spazio dei nomi, Apri il progetto in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], scegliere **Gestisci pacchetti NuGet** dal menu progetto e cercare online il `Microsoft.Tpl.Dataflow` pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e43c1-105">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e43c1-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e43c1-106">Example</span></span>  
 <span data-ttu-id="e43c1-107">Nell'esempio seguente vengono creati tre oggetti <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, tramite ognuno dei quali viene chiamato il metodo `TrySolution` per calcolare un valore.</span><span class="sxs-lookup"><span data-stu-id="e43c1-107">The following example creates three <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objects, each of which calls the `TrySolution` method to compute a value.</span></span> <span data-ttu-id="e43c1-108">Per questo esempio è necessario solo il risultato della prima chiamata a `TrySolution` per il completamento.</span><span class="sxs-lookup"><span data-stu-id="e43c1-108">This example requires only the result from the first call to `TrySolution` to finish.</span></span>  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 <span data-ttu-id="e43c1-109">Per ricevere il valore dal primo oggetto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> completato, nell'esempio viene definito il metodo `ReceiveFromAny(T)`.</span><span class="sxs-lookup"><span data-stu-id="e43c1-109">To receive the value from the first <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object that finishes, this example defines the `ReceiveFromAny(T)` method.</span></span> <span data-ttu-id="e43c1-110">Il metodo `ReceiveFromAny(T)` accetta una matrice di oggetti <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> e tramite esso viene collegato ognuno di questi oggetti a un oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="e43c1-110">The `ReceiveFromAny(T)` method accepts an array of <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objects and links each of these objects to a <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="e43c1-111">Quando si utilizza il metodo <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> per collegare un blocco di flussi di dati di origine a un blocco di destinazione, tramite l'origine i messaggi vengono propagati nella destinazione quando i dati diventano disponibili.</span><span class="sxs-lookup"><span data-stu-id="e43c1-111">When you use the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method to link a source dataflow block to a target block, the source propagates messages to the target as data becomes available.</span></span> <span data-ttu-id="e43c1-112">Poiché la classe <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> accetta solo il primo messaggio offerto, tramite il metodo `ReceiveFromAny(T)` viene generato il relativo risultato chiamando il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>.</span><span class="sxs-lookup"><span data-stu-id="e43c1-112">Because the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> class accepts only the first message that it is offered, the `ReceiveFromAny(T)` method produces its result by calling the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method.</span></span> <span data-ttu-id="e43c1-113">In questo modo viene generato il primo messaggio offerto all'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="e43c1-113">This produces the first message that is offered to the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="e43c1-114">Il metodo <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> dispone di una versione sottoposta a overload che accetta un parametro <xref:System.Boolean>, `unlinkAfterOne` che, quando viene impostato su `True`, indica al blocco di origine di scollegarsi dalla destinazione dopo la ricezione di un messaggio dall'origine da parte della destinazione.</span><span class="sxs-lookup"><span data-stu-id="e43c1-114">The <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method has an overloaded version that takes a <xref:System.Boolean> parameter, `unlinkAfterOne` that, when it is set to `True`, instructs the source block to unlink from the target after the target receives one message from the source.</span></span> <span data-ttu-id="e43c1-115">È importante per l'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> scollegarsi dalle relative origini perché la relazione tra la matrice delle origini e l'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> non è più richiesta dopo la ricezione di un messaggio da parte dell'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="e43c1-115">It is important for the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object to unlink from its sources because the relationship between the array of sources and the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object is no longer required after the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object receives a message.</span></span>  
  
 <span data-ttu-id="e43c1-116">Per abilitare il completamento delle chiamate rimanenti a `TrySolution` dopo che tramite una di esse viene calcolato un valore, il metodo `TrySolution` accetta un oggetto <xref:System.Threading.CancellationToken> che viene annullato dopo che la chiamata a `ReceiveFromAny(T)` ha restituito un valore.</span><span class="sxs-lookup"><span data-stu-id="e43c1-116">To enable the remaining calls to `TrySolution` to end after one of them computes a value, the `TrySolution` method takes a <xref:System.Threading.CancellationToken> object that is canceled after the call to `ReceiveFromAny(T)` returns.</span></span> <span data-ttu-id="e43c1-117">Tramite il metodo <xref:System.Threading.SpinWait.SpinUntil%2A> viene restituito un valore quando questo oggetto <xref:System.Threading.CancellationToken> viene annullato.</span><span class="sxs-lookup"><span data-stu-id="e43c1-117">The <xref:System.Threading.SpinWait.SpinUntil%2A> method returns when this <xref:System.Threading.CancellationToken> object is canceled.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e43c1-118">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e43c1-118">Compiling the Code</span></span>  
 <span data-ttu-id="e43c1-119">Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), quindi eseguire il comando riportato di seguito in una finestra del prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e43c1-119">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="e43c1-120">**csc.exe /r:System.Threading.Tasks.Dataflow.dll dataflowreceiveany. cs**</span><span class="sxs-lookup"><span data-stu-id="e43c1-120">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="e43c1-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll dataflowreceiveany. vb**</span><span class="sxs-lookup"><span data-stu-id="e43c1-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e43c1-122">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e43c1-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43c1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e43c1-123">See Also</span></span>  
 [<span data-ttu-id="e43c1-124">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="e43c1-124">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
