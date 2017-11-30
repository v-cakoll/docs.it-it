---
title: File mappati alla memoria
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
- memory-mapped files
- inter-process communiation
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
caps.latest.revision: "24"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2602d431aada7b3e0ee226eed319903492022ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="memory-mapped-files"></a><span data-ttu-id="e4a17-102">File mappati alla memoria</span><span class="sxs-lookup"><span data-stu-id="e4a17-102">Memory-Mapped Files</span></span>
<span data-ttu-id="e4a17-103">Un file mappato alla memoria include il contenuto di un file nella memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="e4a17-103">A memory-mapped file contains the contents of a file in virtual memory.</span></span> <span data-ttu-id="e4a17-104">Questo mapping tra uno spazio di memoria e di file consente a un'applicazione, con più processi modificare il file da leggere e scrivere direttamente alla memoria.</span><span class="sxs-lookup"><span data-stu-id="e4a17-104">This mapping between a file and memory space enables an application, including multiple processes, to modify the file by reading and writing directly to the memory.</span></span> <span data-ttu-id="e4a17-105">A partire dal [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile utilizzare codice gestito per accedere ai file mappati alla memoria nello stesso modo che le funzioni Windows native accedere ai file mappati alla memoria, come descritto in [gestione di file Win32](http://go.microsoft.com/fwlink/?linkid=180801).</span><span class="sxs-lookup"><span data-stu-id="e4a17-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use managed code to access memory-mapped files in the same way that native Windows functions access memory-mapped files, as described in [Managing Memory-Mapped Files in Win32](http://go.microsoft.com/fwlink/?linkid=180801).</span></span>  
  
 <span data-ttu-id="e4a17-106">Esistono due tipi di file mappati alla memoria:</span><span class="sxs-lookup"><span data-stu-id="e4a17-106">There are two types of memory-mapped files:</span></span>  
  
-   <span data-ttu-id="e4a17-107">File mappato alla memoria persistenti</span><span class="sxs-lookup"><span data-stu-id="e4a17-107">Persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="e4a17-108">File persistenti sono file mappato alla memoria associati a un file di origine in un disco.</span><span class="sxs-lookup"><span data-stu-id="e4a17-108">Persisted files are memory-mapped files that are associated with a source file on a disk.</span></span> <span data-ttu-id="e4a17-109">Quando l'ultimo processo ha completato l'utilizzo con il file, i dati vengono salvati nel file di origine sul disco.</span><span class="sxs-lookup"><span data-stu-id="e4a17-109">When the last process has finished working with the file, the data is saved to the source file on the disk.</span></span> <span data-ttu-id="e4a17-110">Questi file mappato alla memoria sono adatti per l'utilizzo di file di origine molto elevata.</span><span class="sxs-lookup"><span data-stu-id="e4a17-110">These memory-mapped files are suitable for working with extremely large source files.</span></span>  
  
-   <span data-ttu-id="e4a17-111">File mappato alla memoria non persistenti</span><span class="sxs-lookup"><span data-stu-id="e4a17-111">Non-persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="e4a17-112">File persistenti non sono file mappati alla memoria non sono associati a un file su disco.</span><span class="sxs-lookup"><span data-stu-id="e4a17-112">Non-persisted files are memory-mapped files that are not associated with a file on a disk.</span></span> <span data-ttu-id="e4a17-113">Quando l'ultimo processo ha completato l'utilizzo con il file, i dati vengono persi e il file viene recuperato da garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e4a17-113">When the last process has finished working with the file, the data is lost and the file is reclaimed by garbage collection.</span></span> <span data-ttu-id="e4a17-114">Questi file sono adatti per la creazione di memoria condivisa per le comunicazioni interprocesso (IPC).</span><span class="sxs-lookup"><span data-stu-id="e4a17-114">These files are suitable for creating shared memory for inter-process communications (IPC).</span></span>  
  
## <a name="processes-views-and-managing-memory"></a><span data-ttu-id="e4a17-115">Processi, viste e gestione della memoria</span><span class="sxs-lookup"><span data-stu-id="e4a17-115">Processes, Views, and Managing Memory</span></span>  
 <span data-ttu-id="e4a17-116">File mappato alla memoria possono essere condivisi tra più processi.</span><span class="sxs-lookup"><span data-stu-id="e4a17-116">Memory-mapped files can be shared across multiple processes.</span></span> <span data-ttu-id="e4a17-117">Processi possono eseguire il mapping allo stesso file mappato alla memoria utilizzando un nome comune che viene assegnato dal processo di cui è stato creato.</span><span class="sxs-lookup"><span data-stu-id="e4a17-117">Processes can map to the same memory-mapped file by using a common name that is assigned by the process that created the file.</span></span>  
  
 <span data-ttu-id="e4a17-118">Per utilizzare un file mappato alla memoria, è necessario creare una visualizzazione dell'intero file mappato alla memoria o una parte di esso.</span><span class="sxs-lookup"><span data-stu-id="e4a17-118">To work with a memory-mapped file, you must create a view of the entire memory-mapped file or a part of it.</span></span> <span data-ttu-id="e4a17-119">È inoltre possibile creare più visualizzazioni alla stessa parte del file mappato alla memoria, in modo da creare memoria simultanea.</span><span class="sxs-lookup"><span data-stu-id="e4a17-119">You can also create multiple views to the same part of the memory-mapped file, thereby creating concurrent memory.</span></span> <span data-ttu-id="e4a17-120">Per le due viste rimangano simultanee, devono essere creati dallo stesso file mappato alla memoria.</span><span class="sxs-lookup"><span data-stu-id="e4a17-120">For two views to remain concurrent, they have to be created from the same memory-mapped file.</span></span>  
  
 <span data-ttu-id="e4a17-121">Visualizzazioni multiple potrebbero inoltre essere necessarie se il file è maggiore della dimensione dello spazio di memoria logica dell'applicazione disponibile per il mapping (2 GB in un computer a 32 bit) di memoria.</span><span class="sxs-lookup"><span data-stu-id="e4a17-121">Multiple views may also be necessary if the file is greater than the size of the application’s logical memory space available for memory mapping (2 GB on a 32-bit computer).</span></span>  
  
 <span data-ttu-id="e4a17-122">Esistono due tipi di visualizzazioni: visualizzazione di accesso e visualizzazione di accesso casuale di flusso.</span><span class="sxs-lookup"><span data-stu-id="e4a17-122">There are two types of views: stream access view and random access view.</span></span> <span data-ttu-id="e4a17-123">Utilizzare le visualizzazioni di accesso di flusso per l'accesso sequenziale in un file. Questa è consigliata per i file non persistenti e IPC.</span><span class="sxs-lookup"><span data-stu-id="e4a17-123">Use stream access views for sequential access to a file; this is recommended for non-persisted files and IPC.</span></span> <span data-ttu-id="e4a17-124">Le visualizzazioni ad accesso casuale sono preferibili per l'utilizzo dei file persistenti.</span><span class="sxs-lookup"><span data-stu-id="e4a17-124">Random access views are preferred for working with persisted files.</span></span>  
  
 <span data-ttu-id="e4a17-125">File mappati alla memoria sono accessibili tramite il gestore di memoria del sistema operativo, in modo che il file viene automaticamente partizionato in un numero di pagine e accedere in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e4a17-125">Memory-mapped files are accessed through the operating system’s memory manager, so the file is automatically partitioned into a number of pages and accessed as needed.</span></span> <span data-ttu-id="e4a17-126">Non è necessario gestire personalmente la gestione della memoria.</span><span class="sxs-lookup"><span data-stu-id="e4a17-126">You do not have to handle the memory management yourself.</span></span>  
  
 <span data-ttu-id="e4a17-127">La figura seguente mostra come più processi possono avere più e sovrapposti viste nello stesso file mappato alla memoria nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="e4a17-127">The following illustration shows how multiple processes can have multiple and overlapping views to the same memory-mapped file at the same time.</span></span>  
  
 <span data-ttu-id="e4a17-128">![Mostra visualizzazioni a una memoria &#45; il file mappato. ] (../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")</span><span class="sxs-lookup"><span data-stu-id="e4a17-128">![Shows views to a memory&#45;mapped file.](../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")</span></span>  
<span data-ttu-id="e4a17-129">Più e sovrapposte viste in un file mappato alla memoria</span><span class="sxs-lookup"><span data-stu-id="e4a17-129">Multiple and overlapped views to a memory-mapped file</span></span>  
  
## <a name="programming-with-memory-mapped-files"></a><span data-ttu-id="e4a17-130">Programmazione con i file mappati alla memoria</span><span class="sxs-lookup"><span data-stu-id="e4a17-130">Programming with Memory-Mapped Files</span></span>  
 <span data-ttu-id="e4a17-131">Nella tabella seguente viene fornita una Guida per l'utilizzo di oggetti del file mappato alla memoria e i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="e4a17-131">The following table provides a guide for using memory-mapped file objects and their members.</span></span>  
  
|<span data-ttu-id="e4a17-132">Attività</span><span class="sxs-lookup"><span data-stu-id="e4a17-132">Task</span></span>|<span data-ttu-id="e4a17-133">Metodi o proprietà da utilizzare</span><span class="sxs-lookup"><span data-stu-id="e4a17-133">Methods or properties to use</span></span>|  
|----------|----------------------------------|  
|<span data-ttu-id="e4a17-134">Per ottenere un <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> oggetto che rappresenta un file mappato alla memoria persistente da un file su disco.</span><span class="sxs-lookup"><span data-stu-id="e4a17-134">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a persisted memory-mapped file from a file on disk.</span></span>|<span data-ttu-id="e4a17-135">Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="e4a17-136">Per ottenere un <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> oggetto che rappresenta un file mappato alla memoria non persistente (non associato a un file su disco).</span><span class="sxs-lookup"><span data-stu-id="e4a17-136">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a non-persisted memory-mapped file (not associated with a file on disk).</span></span>|<span data-ttu-id="e4a17-137">Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> method.</span></span><br /><br /> <span data-ttu-id="e4a17-138">-oppure-</span><span class="sxs-lookup"><span data-stu-id="e4a17-138">- or -</span></span><br /><br /> <span data-ttu-id="e4a17-139">Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="e4a17-140">Per ottenere un <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> oggetto di un file mappato alla memoria esistente (persistente o non persistente).</span><span class="sxs-lookup"><span data-stu-id="e4a17-140">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object of an existing memory-mapped file (either persisted or non-persisted).</span></span>|<span data-ttu-id="e4a17-141">Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="e4a17-142">Per ottenere un <xref:System.IO.UnmanagedMemoryStream> oggetto per una visualizzazione in sequenza a cui si accede al file mappato alla memoria.</span><span class="sxs-lookup"><span data-stu-id="e4a17-142">To obtain a <xref:System.IO.UnmanagedMemoryStream> object for a sequentially accessed view to the memory-mapped file.</span></span>|<span data-ttu-id="e4a17-143">Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="e4a17-144">Per ottenere un <xref:System.IO.UnmanagedMemoryAccessor> dell'oggetto per una visualizzazione ad accesso casuale mappato alla memoria dannoso.</span><span class="sxs-lookup"><span data-stu-id="e4a17-144">To obtain a <xref:System.IO.UnmanagedMemoryAccessor> object for a random access view to a memory-mapped fie.</span></span>|<span data-ttu-id="e4a17-145">Metodo <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="e4a17-146">Per ottenere un <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> oggetto da usare con codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="e4a17-146">To obtain a <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> object to use with unmanaged code.</span></span>|<span data-ttu-id="e4a17-147">Proprietà <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="e4a17-148">-oppure-</span><span class="sxs-lookup"><span data-stu-id="e4a17-148">- or -</span></span><br /><br /> <span data-ttu-id="e4a17-149">Proprietà <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="e4a17-150">-oppure-</span><span class="sxs-lookup"><span data-stu-id="e4a17-150">- or -</span></span><br /><br /> <span data-ttu-id="e4a17-151">Proprietà <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4a17-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="e4a17-152">Per ritardare l'allocazione della memoria fino a una vista viene creata (solo file di non persistente).</span><span class="sxs-lookup"><span data-stu-id="e4a17-152">To delay allocating memory until a view is created (non-persisted files only).</span></span><br /><br /> <span data-ttu-id="e4a17-153">(Per determinare le dimensioni della pagina corrente del sistema, utilizzare il <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> proprietà.)</span><span class="sxs-lookup"><span data-stu-id="e4a17-153">(To determine the current system page size, use the <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> property.)</span></span>|<span data-ttu-id="e4a17-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>metodo con il <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> valore.</span><span class="sxs-lookup"><span data-stu-id="e4a17-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> method with the <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> value.</span></span><br /><br /> <span data-ttu-id="e4a17-155">-oppure-</span><span class="sxs-lookup"><span data-stu-id="e4a17-155">- or -</span></span><br /><br /> <span data-ttu-id="e4a17-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>metodi che presentano un <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumerazione come parametro.</span><span class="sxs-lookup"><span data-stu-id="e4a17-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods that have a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumeration as a parameter.</span></span>|  
  
### <a name="security"></a><span data-ttu-id="e4a17-157">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4a17-157">Security</span></span>  
 <span data-ttu-id="e4a17-158">È possibile applicare i diritti di accesso quando si crea un file mappato alla memoria, utilizzando i metodi seguenti che accettano un <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumerazione come parametro:</span><span class="sxs-lookup"><span data-stu-id="e4a17-158">You can apply access rights when you create a memory-mapped file, by using the following methods that take a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumeration as a parameter:</span></span>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="e4a17-159">È possibile specificare i diritti di accesso per l'apertura di un file mappato alla memoria esistente utilizzando il <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> metodi che accettano un <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> come parametro.</span><span class="sxs-lookup"><span data-stu-id="e4a17-159">You can specify access rights for opening an existing memory-mapped file by using the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> methods that take an <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> as a parameter.</span></span>  
  
 <span data-ttu-id="e4a17-160">Inoltre, è possibile includere un <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> oggetto che contiene le regole di accesso predefinito.</span><span class="sxs-lookup"><span data-stu-id="e4a17-160">In addition, you can include a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> object that contains predefined access rules.</span></span>  
  
 <span data-ttu-id="e4a17-161">Per applicare le regole di accesso nuove o modificate in un file mappato alla memoria, utilizzare il <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e4a17-161">To apply new or changed access rules to a memory-mapped file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> method.</span></span> <span data-ttu-id="e4a17-162">Per recuperare l'accesso o controllare le regole da un file esistente, utilizzare il <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e4a17-162">To retrieve access or audit rules from an existing file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e4a17-163">Esempi</span><span class="sxs-lookup"><span data-stu-id="e4a17-163">Examples</span></span>  
  
### <a name="persisted-memory-mapped-files"></a><span data-ttu-id="e4a17-164">File mappato alla memoria persistenti</span><span class="sxs-lookup"><span data-stu-id="e4a17-164">Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="e4a17-165">Il <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> metodi creano un file mappato alla memoria da un file esistente sul disco.</span><span class="sxs-lookup"><span data-stu-id="e4a17-165">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> methods create a memory-mapped file from an existing file on disk.</span></span>  
  
 <span data-ttu-id="e4a17-166">Nell'esempio seguente viene creata una visualizzazione mappato alla memoria di una parte di un file molto grande e modifica di una parte di esso.</span><span class="sxs-lookup"><span data-stu-id="e4a17-166">The following example creates a memory-mapped view of a part of an extremely large file and manipulates a portion of it.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 <span data-ttu-id="e4a17-167">Nell'esempio seguente viene aperto lo stesso file mappato alla memoria per un altro processo.</span><span class="sxs-lookup"><span data-stu-id="e4a17-167">The following example opens the same memory-mapped file for another process.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a><span data-ttu-id="e4a17-168">File mappato alla memoria non persistenti</span><span class="sxs-lookup"><span data-stu-id="e4a17-168">Non-Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="e4a17-169">Il <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> e <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> metodi consentono di creare un file mappato alla memoria non è mappato a un file esistente sul disco.</span><span class="sxs-lookup"><span data-stu-id="e4a17-169">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> and <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods create a memory-mapped file that is not mapped to an existing file on disk.</span></span>  
  
 <span data-ttu-id="e4a17-170">Nell'esempio seguente è costituito da tre processi separati (applicazioni console) che scrivono i valori booleani in un file mappato alla memoria.</span><span class="sxs-lookup"><span data-stu-id="e4a17-170">The following example consists of three separate processes (console applications) that write Boolean values to a memory-mapped file.</span></span> <span data-ttu-id="e4a17-171">Si verifica la sequenza di azioni seguente:</span><span class="sxs-lookup"><span data-stu-id="e4a17-171">The following sequence of actions occur:</span></span>  
  
1.  <span data-ttu-id="e4a17-172">`Process A`Crea il file mappato alla memoria e scrive un valore.</span><span class="sxs-lookup"><span data-stu-id="e4a17-172">`Process A` creates the memory-mapped file and writes a value to it.</span></span>  
  
2.  <span data-ttu-id="e4a17-173">`Process B`Apre il file mappato alla memoria e scrive un valore.</span><span class="sxs-lookup"><span data-stu-id="e4a17-173">`Process B` opens the memory-mapped file and writes a value to it.</span></span>  
  
3.  <span data-ttu-id="e4a17-174">`Process C`Apre il file mappato alla memoria e scrive un valore.</span><span class="sxs-lookup"><span data-stu-id="e4a17-174">`Process C` opens the memory-mapped file and writes a value to it.</span></span>  
  
4.  <span data-ttu-id="e4a17-175">`Process A`legge e visualizza i valori del file mappato alla memoria.</span><span class="sxs-lookup"><span data-stu-id="e4a17-175">`Process A` reads and displays the values from the memory-mapped file.</span></span>  
  
5.  <span data-ttu-id="e4a17-176">Dopo aver `Process A` è terminato con il file mappato alla memoria, il file viene immediatamente recuperato tramite garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e4a17-176">After `Process A` is finished with the memory-mapped file, the file is immediately reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="e4a17-177">Per eseguire questo esempio, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4a17-177">To run this example, do the following:</span></span>  
  
1.  <span data-ttu-id="e4a17-178">Compilare le applicazioni e aprire tre finestre prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e4a17-178">Compile the applications and open three Command Prompt windows.</span></span>  
  
2.  <span data-ttu-id="e4a17-179">Nella prima finestra prompt dei comandi, eseguire `Process A`.</span><span class="sxs-lookup"><span data-stu-id="e4a17-179">In the first Command Prompt window, run `Process A`.</span></span>  
  
3.  <span data-ttu-id="e4a17-180">Nella seconda finestra prompt dei comandi, eseguire `Process B`.</span><span class="sxs-lookup"><span data-stu-id="e4a17-180">In the second Command Prompt window, run `Process B`.</span></span>  
  
4.  <span data-ttu-id="e4a17-181">Tornare alla `Process A` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="e4a17-181">Return to `Process A` and press ENTER.</span></span>  
  
5.  <span data-ttu-id="e4a17-182">Nella terza finestra prompt dei comandi, eseguire `Process C`.</span><span class="sxs-lookup"><span data-stu-id="e4a17-182">In the third Command Prompt window, run `Process C`.</span></span>  
  
6.  <span data-ttu-id="e4a17-183">Tornare alla `Process A` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="e4a17-183">Return to `Process A` and press ENTER.</span></span>  
  
 <span data-ttu-id="e4a17-184">L'output di `Process A` è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e4a17-184">The output of `Process A` is as follows:</span></span>  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 <span data-ttu-id="e4a17-185">**Processo**</span><span class="sxs-lookup"><span data-stu-id="e4a17-185">**Process A**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 <span data-ttu-id="e4a17-186">**Processo B**</span><span class="sxs-lookup"><span data-stu-id="e4a17-186">**Process B**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 <span data-ttu-id="e4a17-187">**Processo C**</span><span class="sxs-lookup"><span data-stu-id="e4a17-187">**Process C**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e4a17-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4a17-188">See Also</span></span>  
 [<span data-ttu-id="e4a17-189">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="e4a17-189">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
