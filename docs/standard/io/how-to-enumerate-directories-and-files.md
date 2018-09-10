---
title: 'Procedura: enumerare directory e file'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3de83395df9e8c89a92e85b96ddd15e9f0be6ad5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44207694"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="a8a3e-102">Procedura: enumerare directory e file</span><span class="sxs-lookup"><span data-stu-id="a8a3e-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="a8a3e-103">È possibile enumerare directory e file usando i metodi che restituiscono una raccolta enumerabile di stringhe dei rispettivi nomi.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="a8a3e-104">È anche possibile usare metodi che restituiscono una raccolta enumerabile di oggetti <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> o <xref:System.IO.FileSystemInfo>.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="a8a3e-105">Le raccolte enumerabili offrono prestazioni migliori rispetto alle matrici quando si lavora con grandi raccolte di file e directory.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="a8a3e-106">È anche possibile usare raccolte enumerabili ottenute da questi metodi per fornire il parametro <xref:System.Collections.Generic.IEnumerable%601> per i costruttori di classi di raccolte, ad esempio la classe <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="a8a3e-107">Se si vuole ottenere solo i nomi di directory o file, usare i metodi di enumerazione della classe <xref:System.IO.Directory>.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="a8a3e-108">Se si vuole ottenere altre proprietà di directory o file, usare le classi <xref:System.IO.DirectoryInfo> e <xref:System.IO.FileSystemInfo>.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="a8a3e-109">La tabella seguente offre una guida ai metodi che restituiscono raccolte enumerabili.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="a8a3e-110">Per enumerare</span><span class="sxs-lookup"><span data-stu-id="a8a3e-110">To enumerate</span></span>|<span data-ttu-id="a8a3e-111">Raccolta enumerabile da restituire</span><span class="sxs-lookup"><span data-stu-id="a8a3e-111">Enumerable collection to return</span></span>|<span data-ttu-id="a8a3e-112">Metodo da usare</span><span class="sxs-lookup"><span data-stu-id="a8a3e-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="a8a3e-113">Directory</span><span class="sxs-lookup"><span data-stu-id="a8a3e-113">Directories</span></span>|<span data-ttu-id="a8a3e-114">Nomi di directory</span><span class="sxs-lookup"><span data-stu-id="a8a3e-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="a8a3e-115">Informazioni sulle directory (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="a8a3e-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a8a3e-116">File</span><span class="sxs-lookup"><span data-stu-id="a8a3e-116">Files</span></span>|<span data-ttu-id="a8a3e-117">Nomi file</span><span class="sxs-lookup"><span data-stu-id="a8a3e-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="a8a3e-118">Informazioni sui file (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="a8a3e-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a8a3e-119">Informazioni sui file system</span><span class="sxs-lookup"><span data-stu-id="a8a3e-119">File system information</span></span>|<span data-ttu-id="a8a3e-120">Voci di file system</span><span class="sxs-lookup"><span data-stu-id="a8a3e-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="a8a3e-121">Informazioni sui file system (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="a8a3e-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a8a3e-122">Anche se è possibile enumerare immediatamente tutti i file presenti nelle sottodirectory della directory padre usando l'opzione di ricerca <xref:System.IO.SearchOption.AllDirectories> fornita dall'enumerazione <xref:System.IO.SearchOption>, eccezioni di accesso non autorizzato (<xref:System.UnauthorizedAccessException>) possono fare sì che l'enumerazione non sia completa.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="a8a3e-123">Se queste eccezioni sono possibili, è possibile intercettarle e continuare enumerando prima di tutto le directory e quindi i file.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="a8a3e-124">Per enumerare nomi di directory</span><span class="sxs-lookup"><span data-stu-id="a8a3e-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="a8a3e-125">Usare il metodo <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> per ottenere un elenco dei nomi di directory di primo livello in un percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="a8a3e-126">Per enumerare nomi di file in una directory e in sottodirectory</span><span class="sxs-lookup"><span data-stu-id="a8a3e-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="a8a3e-127">Usare il metodo <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> per cercare in una directory e (facoltativamente) nelle relative sottodirectory e ottenere un elenco di nomi di file che corrispondono a un criterio di ricerca specificato.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="a8a3e-128">Per enumerare una raccolta di oggetti DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="a8a3e-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="a8a3e-129">Usare il metodo <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> per ottenere una raccolta di directory di primo livello.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="a8a3e-130">Per enumerare una raccolta di oggetti FileInfo in tutte le directory</span><span class="sxs-lookup"><span data-stu-id="a8a3e-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="a8a3e-131">Usare il metodo <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> per ottenere una raccolta di file che corrispondono a un criterio di ricerca specificato in tutte le directory.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="a8a3e-132">Questo esempio enumera prima di tutto le directory di primo livello per intercettare le possibili eccezioni di accesso non autorizzato e quindi enumera i file.</span><span class="sxs-lookup"><span data-stu-id="a8a3e-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a8a3e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8a3e-133">See also</span></span>

- [<span data-ttu-id="a8a3e-134">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="a8a3e-134">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
