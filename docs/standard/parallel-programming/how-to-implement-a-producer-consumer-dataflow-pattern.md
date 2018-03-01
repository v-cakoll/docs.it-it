---
title: 'Procedura: implementare un modello di flusso di dati producer-consumer'
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3758ec77a722a66c6faa287d299e5e9c38858be5
ms.sourcegitcommit: 6a9030eb5bd0f00e1d144f81958adb195cfb1f6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a><span data-ttu-id="69255-102">Procedura: implementare un modello di flusso di dati producer-consumer</span><span class="sxs-lookup"><span data-stu-id="69255-102">How to: Implement a Producer-Consumer Dataflow Pattern</span></span>
<span data-ttu-id="69255-103">In questo documento viene descritto come usare la libreria del flusso di dati TPL per implementare un modello producer-consumer.</span><span class="sxs-lookup"><span data-stu-id="69255-103">This document describes how to use the TPL Dataflow Library to implement a producer-consumer pattern.</span></span> <span data-ttu-id="69255-104">In questo modello, il *producer* invia messaggi a un blocco di messaggi e il *consumer* legge i messaggi dal blocco.</span><span class="sxs-lookup"><span data-stu-id="69255-104">In this pattern, the *producer* sends messages to a message block, and the *consumer* reads messages from that block.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="example"></a><span data-ttu-id="69255-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="69255-105">Example</span></span>  
 <span data-ttu-id="69255-106">Nell'esempio seguente viene illustrato un modello di base producer-consumer in cui viene utilizzato il flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="69255-106">The following example demonstrates a basic producer- consumer model that uses dataflow.</span></span> <span data-ttu-id="69255-107">Tramite il metodo `Produce` vengono scritte matrici contenenti byte casuali di dati in un oggetto <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> e tramite il metodo `Consume` vengono letti i byte da un oggetto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69255-107">The `Produce` method writes arrays that contain random bytes of data to a <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> object and the `Consume` method reads bytes from a <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="69255-108">Agendo sulle interfacce <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> e <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, anziché sui relativi tipi derivati, è possibile scrivere codice riutilizzabile che può agire su diversi tipi di blocchi di flussi di dati.</span><span class="sxs-lookup"><span data-stu-id="69255-108">By acting on the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> and <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> interfaces, instead of their derived types, you can write reusable code that can act on a variety of dataflow block types.</span></span> <span data-ttu-id="69255-109">Nell'esempio viene utilizzata la classe <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="69255-109">This example uses the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class.</span></span> <span data-ttu-id="69255-110">Poiché la classe <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> viene utilizzata sia come blocco di origine sia come blocco di destinazione, il producer e il consumer possono utilizzare un oggetto condiviso per il trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="69255-110">Because the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class acts as both a source block and as a target block, the producer and the consumer can use a shared object to transfer data.</span></span>  
  
 <span data-ttu-id="69255-111">Tramite il metodo `Produce` viene chiamato il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> in un ciclo per scrivere i dati in modo sincrono nel blocco di destinazione.</span><span class="sxs-lookup"><span data-stu-id="69255-111">The `Produce` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method in a loop to synchronously write data to the target block.</span></span> <span data-ttu-id="69255-112">Dopo che tramite il metodo `Produce` vengono scritti tutti i dati nel blocco di destinazione, viene chiamato il metodo <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> per indicare che nel blocco non saranno mai presenti dati aggiuntivi disponibili.</span><span class="sxs-lookup"><span data-stu-id="69255-112">After the `Produce` method writes all data to the target block, it calls the <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> method to indicate that the block will never have additional data available.</span></span> <span data-ttu-id="69255-113">Il metodo `Consume` usa gli operatori [async](~/docs/csharp/language-reference/keywords/async.md) e [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) e [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) per calcolare in modo asincrono il numero totale di byte ricevuti dall'oggetto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="69255-113">The `Consume` method uses the [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) operators ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) to asynchronously compute the total number of bytes that are received from the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> object.</span></span> <span data-ttu-id="69255-114">Per agire in modo asincrono, tramite il metodo `Consume` viene chiamato il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> per ricevere una notifica quando nel blocco di origine vi sono dati disponibili e quando non vi saranno mai dati aggiuntivi disponibili.</span><span class="sxs-lookup"><span data-stu-id="69255-114">To act asynchronously, the `Consume` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> method to receive a notification when the source block has data available and when the source block will never have additional data available.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="69255-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="69255-115">Compiling the Code</span></span>  
 <span data-ttu-id="69255-116">Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), quindi eseguire il comando riportato di seguito in una finestra del prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="69255-116">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="69255-117">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**</span><span class="sxs-lookup"><span data-stu-id="69255-117">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="69255-118">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**</span><span class="sxs-lookup"><span data-stu-id="69255-118">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="69255-119">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="69255-119">Robust Programming</span></span>  
 <span data-ttu-id="69255-120">In questo esempio viene utilizzato solo un consumer per elaborare i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="69255-120">This example uses just one consumer to process the source data.</span></span> <span data-ttu-id="69255-121">Se si dispone di più consumer nell'applicazione, utilizzare il metodo <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> per leggere i dati dal blocco di origine, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="69255-121">If you have multiple consumers in your application, use the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method to read data from the source block, as shown in the following example.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 <span data-ttu-id="69255-122">Tramite il metodo <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> viene restituito `False` quando non vi sono dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="69255-122">The <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method returns `False` when no data is available.</span></span> <span data-ttu-id="69255-123">Quando più consumer devono accedere al blocco di origine contemporaneamente, questo meccanismo garantisce che i dati sono sempre disponibili dopo la chiamata a <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="69255-123">When multiple consumers must access the source block concurrently, this mechanism guarantees that data is still available after the call to <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69255-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69255-124">See Also</span></span>  
 [<span data-ttu-id="69255-125">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="69255-125">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
