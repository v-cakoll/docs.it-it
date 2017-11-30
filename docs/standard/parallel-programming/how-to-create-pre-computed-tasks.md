---
title: "Procedura: Creare attività precalcolate"
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
helpviewer_keywords: tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4596b28afe48aad4a84a7dd72b4a1d44a9ada8a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="cd7a2-102">Procedura: Creare attività precalcolate</span><span class="sxs-lookup"><span data-stu-id="cd7a2-102">How to: Create Pre-Computed Tasks</span></span>
<span data-ttu-id="cd7a2-103">In questo documento viene descritto come utilizzare il metodo <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> per recuperare i risultati di operazioni di download asincrone contenute in una cache.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="cd7a2-104">Tramite il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> viene restituito un oggetto <xref:System.Threading.Tasks.Task%601> finito contenente il valore fornito come relativa proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="cd7a2-105">Questo metodo è utile quando si esegue un'operazione asincrona che restituisce un oggetto <xref:System.Threading.Tasks.Task%601> e il risultato di tale oggetto <xref:System.Threading.Tasks.Task%601> è già calcolato.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd7a2-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd7a2-106">Example</span></span>  
 <span data-ttu-id="cd7a2-107">Nell'esempio seguente vengono scaricate stringhe dal Web.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="cd7a2-108">Viene definito il metodo `DownloadStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="cd7a2-109">Tramite questo metodo vengono scaricate stringhe dal Web in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="cd7a2-110">In questo esempio viene inoltre utilizzato un oggetto <xref:System.Collections.Concurrent.ConcurrentDictionary%602> per memorizzare nella cache i risultati di operazioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="cd7a2-111">Se l'indirizzo di input viene mantenuto in questa cache, in `DownloadStringAsync` viene utilizzato il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> per produrre un oggetto <xref:System.Threading.Tasks.Task%601> con il contenuto in corrispondenza dell'indirizzo in questione.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="cd7a2-112">In caso contrario, tramite `DownloadStringAsync` viene scaricato il file dal Web e viene aggiunto il risultato alla cache.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="cd7a2-113">In questo esempio viene calcolato il tempo necessario per scaricare più stringhe due volte.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="cd7a2-114">Per il secondo set di operazioni di download deve essere impiegato meno tempo del primo poiché i risultati sono contenuti nella cache.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="cd7a2-115">Il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> consente al metodo `DownloadStringAsync` di creare oggetti di <xref:System.Threading.Tasks.Task%601> contenenti questi risultati precalcolati.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cd7a2-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="cd7a2-116">Compiling the Code</span></span>  
 <span data-ttu-id="cd7a2-117">Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `CachedDownloads.cs` (`CachedDownloads.vb` per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), quindi eseguire il comando riportato di seguito in una finestra del prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cd7a2-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `CachedDownloads.cs` (`CachedDownloads.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="cd7a2-118">**csc.exe cacheddownloads. cs**</span><span class="sxs-lookup"><span data-stu-id="cd7a2-118">**csc.exe CachedDownloads.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="cd7a2-119">**vbc.exe cacheddownloads. vb**</span><span class="sxs-lookup"><span data-stu-id="cd7a2-119">**vbc.exe CachedDownloads.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cd7a2-120">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="cd7a2-120">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7a2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd7a2-121">See Also</span></span>  
 [<span data-ttu-id="cd7a2-122">Programmazione asincrona basata su attività</span><span class="sxs-lookup"><span data-stu-id="cd7a2-122">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
