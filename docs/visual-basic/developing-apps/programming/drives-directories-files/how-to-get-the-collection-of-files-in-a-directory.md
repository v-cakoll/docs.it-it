---
title: 'Procedura: ottenere la raccolta di file di una directory in Visual Basic'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- folders, working with
- files, accessing
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 023fb90622b45fe0067cd146f62bc3edb326b5ef
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-get-the-collection-of-files-in-a-directory-in-visual-basic"></a><span data-ttu-id="5c491-102">Procedura: ottenere la raccolta di file di una directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c491-102">How to: Get the Collection of Files in a Directory in Visual Basic</span></span>
<span data-ttu-id="5c491-103">Gli overload del metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> restituiscono una raccolta di stringhe di sola lettura che rappresenta i nomi dei file contenuti in una directory:</span><span class="sxs-lookup"><span data-stu-id="5c491-103">The overloads of the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> method return a read-only collection of strings representing the names of the files within a directory:</span></span>  
  
-   <span data-ttu-id="5c491-104">Usare l'overload <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> per eseguire una ricerca di file semplice in una directory specificata senza cercare nelle sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="5c491-104">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> overload for a simple file search in a specified directory, without searching subdirectories.</span></span>  
  
-   <span data-ttu-id="5c491-105">Usare l'overload <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> per specificare opzioni aggiuntive per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5c491-105">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> overload to specify additional options for your search.</span></span> <span data-ttu-id="5c491-106">È possibile usare il parametro `wildCards` per specificare un criterio di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5c491-106">You can use the `wildCards` parameter to specify a search pattern.</span></span> <span data-ttu-id="5c491-107">Per includere le sottodirectory nella ricerca, impostare il parametro `searchType` su <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5c491-107">To include subdirectories in the search, set the `searchType` parameter to <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="5c491-108">Se non vengono trovati file corrispondenti al criterio specificato, verrà restituita una raccolta vuota.</span><span class="sxs-lookup"><span data-stu-id="5c491-108">An empty collection is returned if no files matching the specified pattern are found.</span></span>  
  
### <a name="to-list-files-in-a-directory"></a><span data-ttu-id="5c491-109">Per elencare i file in una directory</span><span class="sxs-lookup"><span data-stu-id="5c491-109">To list files in a directory</span></span>  
  
-   <span data-ttu-id="5c491-110">Usare uno degli overload del metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName>, fornendo il nome e il percorso della directory in cui cercare nel parametro `directory`.</span><span class="sxs-lookup"><span data-stu-id="5c491-110">Use one of the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> method overloads, supplying the name and path of the directory to search in the `directory` parameter.</span></span> <span data-ttu-id="5c491-111">L'esempio seguente restituisce tutti i file della directory e li aggiunge a `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="5c491-111">The following example returns all files in the directory and adds them to `ListBox1`.</span></span>  
  
     <span data-ttu-id="5c491-112">[!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5c491-112">[!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5c491-113">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="5c491-113">Robust Programming</span></span>  
 <span data-ttu-id="5c491-114">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="5c491-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="5c491-115">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="5c491-115">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="5c491-116">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="5c491-116">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="5c491-117">`directory` non esiste (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="5c491-117">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="5c491-118">`directory` punta a un file esistente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="5c491-118">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="5c491-119">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="5c491-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="5c491-120">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="5c491-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="5c491-121">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="5c491-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="5c491-122">L'utente non dispone delle autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="5c491-122">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c491-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c491-123">See Also</span></span>  
 <span data-ttu-id="5c491-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A></span><span class="sxs-lookup"><span data-stu-id="5c491-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A></span></span>   
 <span data-ttu-id="5c491-125">[How to: Find Files with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)  (Procedura: Trovare file con un modello specifico)</span><span class="sxs-lookup"><span data-stu-id="5c491-125">[How to: Find Files with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md) </span></span>  
 [<span data-ttu-id="5c491-126">Procedura: cercare sottodirectory con un modello specifico</span><span class="sxs-lookup"><span data-stu-id="5c491-126">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)

