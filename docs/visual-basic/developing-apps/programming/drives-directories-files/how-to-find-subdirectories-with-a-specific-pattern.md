---
title: 'Procedura: cercare sottodirectory con un modello specifico in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- pattern matching
- folders, finding
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0c4549f417e86e82897ca32d8d7cf22aaf462c90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-subdirectories-with-a-specific-pattern-in-visual-basic"></a><span data-ttu-id="38a3b-102">Procedura: cercare sottodirectory con un modello specifico in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="38a3b-102">How to: Find Subdirectories with a Specific Pattern in Visual Basic</span></span>
<span data-ttu-id="38a3b-103">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> restituisce una raccolta di stringhe di sola lettura che rappresentano i nomi di percorso per le sottodirectory di una directory.</span><span class="sxs-lookup"><span data-stu-id="38a3b-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> method returns a read-only collection of strings representing the path names for the subdirectories in a directory.</span></span> <span data-ttu-id="38a3b-104">È possibile usare il parametro `wildCards` per specificare un criterio specifico.</span><span class="sxs-lookup"><span data-stu-id="38a3b-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span> <span data-ttu-id="38a3b-105">Se si vogliono includere i contenuti delle sottodirectory nella ricerca, impostare il parametro `searchType` su `SearchOption.SearchAllSubDirectories`.</span><span class="sxs-lookup"><span data-stu-id="38a3b-105">If you would like to include the contents of subdirectories in the search, set the `searchType` parameter to `SearchOption.SearchAllSubDirectories`.</span></span>  
  
 <span data-ttu-id="38a3b-106">Se non vengono trovate directory corrispondenti al criterio specificato, verrà restituita una raccolta vuota.</span><span class="sxs-lookup"><span data-stu-id="38a3b-106">An empty collection is returned if no directories matching the specified pattern are found.</span></span>  
  
### <a name="to-find-subdirectories-with-a-specific-pattern"></a><span data-ttu-id="38a3b-107">Per trovare sottodirectory con un criterio specifico</span><span class="sxs-lookup"><span data-stu-id="38a3b-107">To find subdirectories with a specific pattern</span></span>  
  
-   <span data-ttu-id="38a3b-108">Usare il metodo `GetDirectories`, specificando il nome e percorso della directory che si vuole cercare.</span><span class="sxs-lookup"><span data-stu-id="38a3b-108">Use the `GetDirectories` method, supplying the name and path of the directory you want to search.</span></span> <span data-ttu-id="38a3b-109">L'esempio seguente restituisce tutte le directory nella struttura di directory che contengono la parola "Logs" nel nome e li aggiunge a `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="38a3b-109">The following example returns all the directories in the directory structure that contain the word "Logs" in their name, and adds them to `ListBox1`.</span></span>  
  
     [!code-vb[VbVbcnFileAccess#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-subdirectories-with-a-specific-pattern_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="38a3b-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="38a3b-110">Robust Programming</span></span>  
 <span data-ttu-id="38a3b-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="38a3b-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="38a3b-112">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="38a3b-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="38a3b-113">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="38a3b-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="38a3b-114">Uno o più caratteri jolly specificati è `Nothing`, una stringa vuota o contiene solo spazi (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="38a3b-114">One or more of the specified wildcard characters is `Nothing`, an empty string, or contains only spaces (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="38a3b-115">`directory` non esiste (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="38a3b-115">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="38a3b-116">`directory` punta a un file esistente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="38a3b-116">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="38a3b-117">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="38a3b-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="38a3b-118">Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="38a3b-118">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="38a3b-119">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="38a3b-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="38a3b-120">L'utente non dispone delle autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="38a3b-120">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a3b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38a3b-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>  
 [<span data-ttu-id="38a3b-122">Procedura: trovare file con un modello specifico</span><span class="sxs-lookup"><span data-stu-id="38a3b-122">How to: Find Files with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)
