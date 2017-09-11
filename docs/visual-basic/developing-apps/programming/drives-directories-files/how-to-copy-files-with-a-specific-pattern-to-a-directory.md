---
title: 'Procedura: copiare file con un criterio specifico in una directory in Visual Basic'
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
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files, copying
- CopyFile method, copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 812fd59769da386f8d0b81eb80a4cd93c9764534
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a><span data-ttu-id="83b60-102">Procedura: copiare file con un criterio specifico in una directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83b60-102">How to: Copy Files with a Specific Pattern to a Directory in Visual Basic</span></span>
<span data-ttu-id="83b60-103">Il metodo <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> restituisce una raccolta di stringhe di sola lettura che rappresentano i nomi di percorso per i file.</span><span class="sxs-lookup"><span data-stu-id="83b60-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="83b60-104">È possibile usare il parametro `wildCards` per specificare un criterio specifico.</span><span class="sxs-lookup"><span data-stu-id="83b60-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span>  
  
 <span data-ttu-id="83b60-105">Se non vengono individuati file corrispondenti, viene restituita una raccolta vuota.</span><span class="sxs-lookup"><span data-stu-id="83b60-105">An empty collection is returned if no matching files are found.</span></span>  
  
 <span data-ttu-id="83b60-106">È possibile usare il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> per copiare i file in una directory.</span><span class="sxs-lookup"><span data-stu-id="83b60-106">You can use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> method to copy the files to a directory.</span></span>  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a><span data-ttu-id="83b60-107">Per copiare file con un criterio specifico in una directory</span><span class="sxs-lookup"><span data-stu-id="83b60-107">To copy files with a specific pattern to a directory</span></span>  
  
1.  <span data-ttu-id="83b60-108">Usare il metodo `GetFiles` per restituire l'elenco dei file.</span><span class="sxs-lookup"><span data-stu-id="83b60-108">Use the `GetFiles` method to return the list of files.</span></span> <span data-ttu-id="83b60-109">In questo esempio vengono restituiti tutti i file RTF nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="83b60-109">This example returns all .rtf files in the specified directory.</span></span>  
  
     <span data-ttu-id="83b60-110">[!code-vb[VbFileIOMisc#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="83b60-110">[!code-vb[VbFileIOMisc#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_1.vb)]</span></span>  
  
2.  <span data-ttu-id="83b60-111">Usare il metodo `CopyFile` per copiare i file.</span><span class="sxs-lookup"><span data-stu-id="83b60-111">Use the `CopyFile` method to copy the files.</span></span> <span data-ttu-id="83b60-112">In questo esempio i file vengono copiati nella directory denominata `testdirectory`.</span><span class="sxs-lookup"><span data-stu-id="83b60-112">This example copies the files to the directory named `testdirectory`.</span></span>  
  
     <span data-ttu-id="83b60-113">[!code-vb[VbVbcnMyFileSystem#88](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="83b60-113">[!code-vb[VbVbcnMyFileSystem#88](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_2.vb)]</span></span>  
  
3.  <span data-ttu-id="83b60-114">Chiudere l'istruzione `For` con un'istruzione `Next` .</span><span class="sxs-lookup"><span data-stu-id="83b60-114">Close the `For` statement with a `Next` statement.</span></span>  
  
     <span data-ttu-id="83b60-115">[!code-vb[VbVbcnMyFileSystem#89](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="83b60-115">[!code-vb[VbVbcnMyFileSystem#89](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="83b60-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="83b60-116">Example</span></span>  
 <span data-ttu-id="83b60-117">Nell'esempio seguente, che presenta i frammenti di codice precedenti in forma completa, tutti i file RTF nella directory specificata vengono copiati nella directory denominata `testdirectory`.</span><span class="sxs-lookup"><span data-stu-id="83b60-117">The following example, which presents the above snippets in complete form, copies all .rtf files in the specified directory to the directory named `testdirectory`.</span></span>  
  
 <span data-ttu-id="83b60-118">[!code-vb[VbFileIOMisc#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="83b60-118">[!code-vb[VbFileIOMisc#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_4.vb)]</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="83b60-119">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="83b60-119">.NET Framework Security</span></span>  
 <span data-ttu-id="83b60-120">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="83b60-120">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="83b60-121">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="83b60-121">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="83b60-122">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="83b60-122">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="83b60-123">La directory non esiste (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="83b60-123">The directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="83b60-124">La directory punta a un file esistente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="83b60-124">The directory points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="83b60-125">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="83b60-125">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="83b60-126">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="83b60-126">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="83b60-127">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="83b60-127">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span> <span data-ttu-id="83b60-128">L'utente non dispone delle autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="83b60-128">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b60-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83b60-129">See Also</span></span>  
 <span data-ttu-id="83b60-130"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A></span><span class="sxs-lookup"><span data-stu-id="83b60-130"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A></span></span>   
 <span data-ttu-id="83b60-131"><xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A></span><span class="sxs-lookup"><span data-stu-id="83b60-131"><xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A></span></span>   
 <span data-ttu-id="83b60-132">[Procedura: Cercare sottodirectory con un modello specifico](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="83b60-132">[How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md) </span></span>  
 <span data-ttu-id="83b60-133">[Risoluzione dei problemi: lettura e scrittura nei file di testo](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="83b60-133">[Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md) </span></span>  
 [<span data-ttu-id="83b60-134">Procedura: ottenere la raccolta di file di una directory</span><span class="sxs-lookup"><span data-stu-id="83b60-134">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

