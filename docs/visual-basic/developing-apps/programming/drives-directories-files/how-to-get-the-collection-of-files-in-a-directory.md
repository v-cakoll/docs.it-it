---
title: 'Procedura: Ottenere la raccolta di file di una directory'
ms.date: 07/20/2015
helpviewer_keywords:
- folders, working with
- files [Visual Basic], accessing
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
ms.openlocfilehash: 055151d4b3e3aba6be9b9b03ac9abffc6eb7b734
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401615"
---
# <a name="how-to-get-the-collection-of-files-in-a-directory-in-visual-basic"></a><span data-ttu-id="b9241-102">Procedura: ottenere la raccolta di file di una directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9241-102">How to: Get the Collection of Files in a Directory in Visual Basic</span></span>

<span data-ttu-id="b9241-103">Gli overload del metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType> restituiscono una raccolta di stringhe di sola lettura che rappresenta i nomi dei file contenuti in una directory:</span><span class="sxs-lookup"><span data-stu-id="b9241-103">The overloads of the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType> method return a read-only collection of strings representing the names of the files within a directory:</span></span>  
  
- <span data-ttu-id="b9241-104">Usare l'overload <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> per eseguire una ricerca di file semplice in una directory specificata senza cercare nelle sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="b9241-104">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> overload for a simple file search in a specified directory, without searching subdirectories.</span></span>  
  
- <span data-ttu-id="b9241-105">Usare l'overload <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> per specificare opzioni aggiuntive per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b9241-105">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> overload to specify additional options for your search.</span></span> <span data-ttu-id="b9241-106">È possibile usare il parametro `wildCards` per specificare un criterio di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b9241-106">You can use the `wildCards` parameter to specify a search pattern.</span></span> <span data-ttu-id="b9241-107">Per includere le sottodirectory nella ricerca, impostare il parametro `searchType` su <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b9241-107">To include subdirectories in the search, set the `searchType` parameter to <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="b9241-108">Se non vengono trovati file corrispondenti al criterio specificato, verrà restituita una raccolta vuota.</span><span class="sxs-lookup"><span data-stu-id="b9241-108">An empty collection is returned if no files matching the specified pattern are found.</span></span>  
  
### <a name="to-list-files-in-a-directory"></a><span data-ttu-id="b9241-109">Per elencare i file in una directory</span><span class="sxs-lookup"><span data-stu-id="b9241-109">To list files in a directory</span></span>  
  
- <span data-ttu-id="b9241-110">Usare uno degli overload del metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType>, fornendo il nome e il percorso della directory in cui cercare nel parametro `directory`.</span><span class="sxs-lookup"><span data-stu-id="b9241-110">Use one of the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType> method overloads, supplying the name and path of the directory to search in the `directory` parameter.</span></span> <span data-ttu-id="b9241-111">L'esempio seguente restituisce tutti i file della directory e li aggiunge a `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="b9241-111">The following example returns all files in the directory and adds them to `ListBox1`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#32)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b9241-112">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="b9241-112">Robust Programming</span></span>  

 <span data-ttu-id="b9241-113">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="b9241-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="b9241-114">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b9241-114">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="b9241-115">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="b9241-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="b9241-116">`directory` non esiste (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="b9241-116">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="b9241-117">`directory` punta a un file esistente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b9241-117">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="b9241-118">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="b9241-118">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="b9241-119">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="b9241-119">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="b9241-120">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="b9241-120">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="b9241-121">L'utente non dispone delle autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="b9241-121">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9241-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9241-122">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>
- [<span data-ttu-id="b9241-123">Procedura: Trovare file con un criterio specifico</span><span class="sxs-lookup"><span data-stu-id="b9241-123">How to: Find Files with a Specific Pattern</span></span>](how-to-find-files-with-a-specific-pattern.md)
- [<span data-ttu-id="b9241-124">Procedura: Trovare sottodirectory con un criterio specifico</span><span class="sxs-lookup"><span data-stu-id="b9241-124">How to: Find Subdirectories with a Specific Pattern</span></span>](how-to-find-subdirectories-with-a-specific-pattern.md)
