---
title: 'Procedura: specificare il grado di parallelismo in un blocco di flussi di dati'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b597cf93cdf249936a34b2c07b38d000c96333f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45667872"
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a><span data-ttu-id="f3cc4-102">Procedura: specificare il grado di parallelismo in un blocco di flussi di dati</span><span class="sxs-lookup"><span data-stu-id="f3cc4-102">How to: Specify the Degree of Parallelism in a Dataflow Block</span></span>
<span data-ttu-id="f3cc4-103">In questo documento viene descritto come impostare la proprietà <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> per consentire a un blocco di flussi di dati di esecuzione di elaborare più messaggi alla volta.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-103">This document describes how to set the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> property to enable an execution dataflow block to process more than one message at a time.</span></span> <span data-ttu-id="f3cc4-104">Questa operazione è utile quando è presente un blocco di flussi di dati in cui viene eseguito un calcolo di lunga durata ed è possibile trarre vantaggio dall'elaborazione di messaggi in parallelo.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-104">Doing this is useful when you have a dataflow block that performs a long-running computation and can benefit from processing messages in parallel.</span></span> <span data-ttu-id="f3cc4-105">Nell'esempio viene usata la classe <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> per eseguire più operazioni di flussi di dati contemporaneamente; tuttavia, è possibile specificare il massimo grado di parallelismo in uno dei tipi di blocchi di esecuzione predefiniti forniti dalla libreria del flusso di dati TPL, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-105">This example uses the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> class to perform multiple dataflow operations concurrently; however, you can specify the maximum degree of parallelism in any of the predefined execution block types that the TPL Dataflow Library provides, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a><span data-ttu-id="f3cc4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3cc4-106">Example</span></span>  
 <span data-ttu-id="f3cc4-107">Nell'esempio seguente vengono eseguiti due calcoli del flusso di dati e viene stampato il tempo trascorso richiesto per ogni calcolo.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-107">The following example performs two dataflow computations and prints the elapsed time that is required for each computation.</span></span> <span data-ttu-id="f3cc4-108">Nel primo calcolo viene specificato un grado massimo di parallelismo pari a 1, vale a dire l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-108">The first computation specifies a maximum degree of parallelism of 1, which is the default.</span></span> <span data-ttu-id="f3cc4-109">Un grado massimo di parallelismo pari a 1 determina un'elaborazione seriale dei messaggi da parte del blocco di flussi di dati.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-109">A maximum degree of parallelism of 1 causes the dataflow block to process messages serially.</span></span> <span data-ttu-id="f3cc4-110">Il secondo calcolo è simile al primo, con la differenza che specifica un massimo grado di parallelismo uguale al numero di processori disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-110">The second computation resembles the first, except that it specifies a maximum degree of parallelism that is equal to the number of available processors.</span></span> <span data-ttu-id="f3cc4-111">Ciò consente al blocco di flusso di dati di eseguire più operazioni in parallelo.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-111">This enables the dataflow block to perform multiple operations in parallel.</span></span>  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3cc4-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f3cc4-112">Compiling the Code</span></span>  
 <span data-ttu-id="f3cc4-113">Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `DataflowDegreeOfParallelism.cs` (`DataflowDegreeOfParallelism.vb` per Visual Basic) e quindi eseguire il comando riportato di seguito in una finestra del prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-113">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowDegreeOfParallelism.cs` (`DataflowDegreeOfParallelism.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="f3cc4-114">Visual C#</span><span class="sxs-lookup"><span data-stu-id="f3cc4-114">Visual C#</span></span>  
  
 <span data-ttu-id="f3cc4-115">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**</span><span class="sxs-lookup"><span data-stu-id="f3cc4-115">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**</span></span>  
  
 <span data-ttu-id="f3cc4-116">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3cc4-116">Visual Basic</span></span>  
  
 <span data-ttu-id="f3cc4-117">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**</span><span class="sxs-lookup"><span data-stu-id="f3cc4-117">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f3cc4-118">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="f3cc4-118">Robust Programming</span></span>  
 <span data-ttu-id="f3cc4-119">Per impostazione predefinita, tramite ogni blocco di flussi di dati predefinito i messaggi vengono propagati all'esterno nell'ordine in cui vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-119">By default, each predefined dataflow block propagates out messages in the order in which the messages are received.</span></span>  <span data-ttu-id="f3cc4-120">Anche se vengono elaborati più messaggi contemporaneamente quando si specifica un grado massimo di parallelismo maggiore di 1, questi vengono comunque propagati all'esterno nell'ordine in cui vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-120">Although multiple messages are processed simultaneously when you specify a maximum degree of parallelism that is greater than 1, they are still propagated out in the order in which they are received.</span></span>  
  
 <span data-ttu-id="f3cc4-121">Poiché la proprietà <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> rappresenta il grado massimo di parallelismo, il blocco di flussi di dati può essere eseguito con un grado di parallelismo minore rispetto a quello specificato.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-121">Because the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> property represents the maximum degree of parallelism, the dataflow block might execute with a lesser degree of parallelism than you specify.</span></span> <span data-ttu-id="f3cc4-122">Con il blocco di flussi di dati è possibile usare un minore grado di parallelismo per soddisfare i relativi requisiti funzionali o per tener conto della mancanza di risorse di sistema disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-122">The dataflow block can use a lesser degree of parallelism to meet its functional requirements or to account for a lack of available system resources.</span></span> <span data-ttu-id="f3cc4-123">Da parte di un blocco di flussi di dati non viene mai scelto un parallelismo maggiore di quello specificato.</span><span class="sxs-lookup"><span data-stu-id="f3cc4-123">A dataflow block never chooses a greater degree of parallelism than you specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3cc4-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3cc4-124">See also</span></span>

- [<span data-ttu-id="f3cc4-125">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="f3cc4-125">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
