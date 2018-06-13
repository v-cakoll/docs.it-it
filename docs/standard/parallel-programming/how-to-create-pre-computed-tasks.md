---
title: 'Procedura: Creare attività precalcolate'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5d688041c6a8947b4a30f067d969cb6cb3bbf0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583903"
---
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="af56a-102">Procedura: Creare attività precalcolate</span><span class="sxs-lookup"><span data-stu-id="af56a-102">How to: Create Pre-Computed Tasks</span></span>
<span data-ttu-id="af56a-103">In questo documento viene descritto come utilizzare il metodo <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> per recuperare i risultati di operazioni di download asincrone contenute in una cache.</span><span class="sxs-lookup"><span data-stu-id="af56a-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="af56a-104">Tramite il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> viene restituito un oggetto <xref:System.Threading.Tasks.Task%601> finito contenente il valore fornito come relativa proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>.</span><span class="sxs-lookup"><span data-stu-id="af56a-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="af56a-105">Questo metodo è utile quando si esegue un'operazione asincrona che restituisce un oggetto <xref:System.Threading.Tasks.Task%601> e il risultato di tale oggetto <xref:System.Threading.Tasks.Task%601> è già calcolato.</span><span class="sxs-lookup"><span data-stu-id="af56a-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af56a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="af56a-106">Example</span></span>  
 <span data-ttu-id="af56a-107">Nell'esempio seguente vengono scaricate stringhe dal Web.</span><span class="sxs-lookup"><span data-stu-id="af56a-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="af56a-108">Viene definito il metodo `DownloadStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="af56a-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="af56a-109">Tramite questo metodo vengono scaricate stringhe dal Web in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="af56a-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="af56a-110">In questo esempio viene inoltre utilizzato un oggetto <xref:System.Collections.Concurrent.ConcurrentDictionary%602> per memorizzare nella cache i risultati di operazioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="af56a-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="af56a-111">Se l'indirizzo di input viene mantenuto in questa cache, in `DownloadStringAsync` viene utilizzato il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> per produrre un oggetto <xref:System.Threading.Tasks.Task%601> con il contenuto in corrispondenza dell'indirizzo in questione.</span><span class="sxs-lookup"><span data-stu-id="af56a-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="af56a-112">In caso contrario, tramite `DownloadStringAsync` viene scaricato il file dal Web e viene aggiunto il risultato alla cache.</span><span class="sxs-lookup"><span data-stu-id="af56a-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="af56a-113">In questo esempio viene calcolato il tempo necessario per scaricare più stringhe due volte.</span><span class="sxs-lookup"><span data-stu-id="af56a-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="af56a-114">Per il secondo set di operazioni di download deve essere impiegato meno tempo del primo poiché i risultati sono contenuti nella cache.</span><span class="sxs-lookup"><span data-stu-id="af56a-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="af56a-115">Il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> consente al metodo `DownloadStringAsync` di creare oggetti di <xref:System.Threading.Tasks.Task%601> contenenti questi risultati precalcolati.</span><span class="sxs-lookup"><span data-stu-id="af56a-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="af56a-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="af56a-116">Compiling the Code</span></span>  
 <span data-ttu-id="af56a-117">Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `CachedDownloads.cs` (`CachedDownloads.vb` per Visual Basic) e quindi eseguire il comando riportato di seguito in una finestra del prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="af56a-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `CachedDownloads.cs` (`CachedDownloads.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="af56a-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="af56a-118">Visual C#</span></span>  
  
 <span data-ttu-id="af56a-119">**csc.exe CachedDownloads.cs**</span><span class="sxs-lookup"><span data-stu-id="af56a-119">**csc.exe CachedDownloads.cs**</span></span>  
  
 <span data-ttu-id="af56a-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="af56a-120">Visual Basic</span></span>  
  
 <span data-ttu-id="af56a-121">**vbc.exe CachedDownloads.vb**</span><span class="sxs-lookup"><span data-stu-id="af56a-121">**vbc.exe CachedDownloads.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="af56a-122">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="af56a-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af56a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af56a-123">See Also</span></span>  
 [<span data-ttu-id="af56a-124">Programmazione asincrona basata su attività</span><span class="sxs-lookup"><span data-stu-id="af56a-124">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
