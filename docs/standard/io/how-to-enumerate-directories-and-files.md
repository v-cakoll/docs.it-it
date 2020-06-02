---
title: 'Procedura: enumerare directory e file'
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
ms.openlocfilehash: bcb10426175c1f2cabeec6d8d4f8d2ed74e5e3b4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291877"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="61be7-102">Procedura: enumerare directory e file</span><span class="sxs-lookup"><span data-stu-id="61be7-102">How to: Enumerate directories and files</span></span>
<span data-ttu-id="61be7-103">Le raccolte enumerabili offrono prestazioni migliori rispetto alle matrici quando si lavora con grandi raccolte di file e directory.</span><span class="sxs-lookup"><span data-stu-id="61be7-103">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span> <span data-ttu-id="61be7-104">Per enumerare directory e file, usare metodi che restituiscono una raccolta enumerabile di nomi di directory o file o dei rispettivi oggetti <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> o <xref:System.IO.FileSystemInfo>.</span><span class="sxs-lookup"><span data-stu-id="61be7-104">To enumerate directories and files, use methods that return an enumerable collection of directory or file names, or their <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span>  
  
<span data-ttu-id="61be7-105">Se si vogliono cercare e restituire solo i nomi di directory o file, usare i metodi di enumerazione della classe <xref:System.IO.Directory>.</span><span class="sxs-lookup"><span data-stu-id="61be7-105">If you want to search and return only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="61be7-106">Se si vogliono cercare e restituire altre proprietà di directory o file, usare le classi <xref:System.IO.DirectoryInfo> e <xref:System.IO.FileSystemInfo>.</span><span class="sxs-lookup"><span data-stu-id="61be7-106">If you want to search and return other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
<span data-ttu-id="61be7-107">È possibile usare raccolte enumerabili ottenute da questi metodi come parametro <xref:System.Collections.Generic.IEnumerable%601> per i costruttori di classi di raccolte, come <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="61be7-107">You can use enumerable collections from these methods as the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes like <xref:System.Collections.Generic.List%601>.</span></span>  
  
<span data-ttu-id="61be7-108">La tabella seguente riepiloga i metodi che restituiscono raccolte enumerabili di file e directory:</span><span class="sxs-lookup"><span data-stu-id="61be7-108">The following table summarizes the methods that return enumerable collections of files and directories:</span></span>  
  
|<span data-ttu-id="61be7-109">Per cercare e restituire</span><span class="sxs-lookup"><span data-stu-id="61be7-109">To search and return</span></span>|<span data-ttu-id="61be7-110">Usare il metodo</span><span class="sxs-lookup"><span data-stu-id="61be7-110">Use method</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="61be7-111">Nomi di directory</span><span class="sxs-lookup"><span data-stu-id="61be7-111">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="61be7-112">Informazioni sulle directory (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="61be7-112">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="61be7-113">Nomi file</span><span class="sxs-lookup"><span data-stu-id="61be7-113">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="61be7-114">Informazioni sui file (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="61be7-114">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="61be7-115">Nomi di voci del file system</span><span class="sxs-lookup"><span data-stu-id="61be7-115">File system entry names</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="61be7-116">Informazioni sulle voci di file system (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="61be7-116">File system entry information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="61be7-117">Nomi di file e directory</span><span class="sxs-lookup"><span data-stu-id="61be7-117">Directory and file names</span></span> |<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  

> [!NOTE]
> <span data-ttu-id="61be7-118">Anche se è possibile enumerare immediatamente tutti i file presenti nelle sottodirectory della directory padre usando l'opzione <xref:System.IO.SearchOption.AllDirectories> dell'enumerazione <xref:System.IO.SearchOption> facoltativa, errori <xref:System.UnauthorizedAccessException> possono rendere incompleta l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="61be7-118">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> option of the optional <xref:System.IO.SearchOption> enumeration, <xref:System.UnauthorizedAccessException> errors may make the enumeration incomplete.</span></span> <span data-ttu-id="61be7-119">È possibile intercettare queste eccezioni enumerando prima di tutto le directory e quindi i file.</span><span class="sxs-lookup"><span data-stu-id="61be7-119">You can catch these exceptions by first enumerating directories and then enumerating files.</span></span>  
  
## <a name="examples-use-the-directory-class"></a><span data-ttu-id="61be7-120">Esempi: usare la classe Directory</span><span class="sxs-lookup"><span data-stu-id="61be7-120">Examples: Use the Directory class</span></span>  
  
<span data-ttu-id="61be7-121">L'esempio seguente usa il metodo <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> per ottenere un elenco dei nomi delle directory di primo livello in un percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="61be7-121">The following example uses the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to get a list of the top-level directory names in a specified path.</span></span>  

[!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
[!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  

<span data-ttu-id="61be7-122">L'esempio seguente usa il metodo <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> per enumerare in modo ricorsivo tutti i nomi file in una directory e nelle relative sottodirectory che soddisfano un criterio specifico.</span><span class="sxs-lookup"><span data-stu-id="61be7-122">The following example uses the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to recursively enumerate all file names in a directory and subdirectories that match a certain pattern.</span></span> <span data-ttu-id="61be7-123">L'esempio legge quindi ogni riga di ogni file e visualizza le righe che contengono una stringa specificata, con i nomi file e i percorsi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="61be7-123">It then reads each line of each file and displays the lines that contain a specified string, with their filenames and paths.</span></span>

[!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
[!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
## <a name="examples-use-the-directoryinfo-class"></a><span data-ttu-id="61be7-124">Esempi: usare la classe DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="61be7-124">Examples: Use the DirectoryInfo class</span></span>  
  
<span data-ttu-id="61be7-125">L'esempio seguente usa il metodo <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> per elencare una raccolta di directory di primo livello la cui proprietà <xref:System.IO.FileSystemInfo.CreationTimeUtc> è precedente a un valore <xref:System.DateTime> specifico.</span><span class="sxs-lookup"><span data-stu-id="61be7-125">The following example uses the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to list a collection of top-level directories whose <xref:System.IO.FileSystemInfo.CreationTimeUtc> is earlier than a certain <xref:System.DateTime> value.</span></span>  

[!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs)]
[!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb)]  
  
<span data-ttu-id="61be7-126">L'esempio seguente usa il metodo <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> per elencare tutti i file la cui proprietà <xref:System.IO.FileInfo.Length> supera i 10 MB.</span><span class="sxs-lookup"><span data-stu-id="61be7-126">The following example uses the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to list all files whose <xref:System.IO.FileInfo.Length> exceeds 10MB.</span></span> <span data-ttu-id="61be7-127">Questo esempio enumera prima di tutto le directory di primo livello per intercettare possibili eccezioni di accesso non autorizzato e quindi enumera i file.</span><span class="sxs-lookup"><span data-stu-id="61be7-127">This example first enumerates the top-level directories, to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  

[!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
[!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="61be7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61be7-128">See also</span></span>

- [<span data-ttu-id="61be7-129">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="61be7-129">File and stream I/O</span></span>](index.md)
