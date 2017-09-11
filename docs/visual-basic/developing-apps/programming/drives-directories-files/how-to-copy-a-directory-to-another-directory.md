---
title: 'Procedura: copiare una directory in un''altra directory di Visual Basic'
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
- I/O [Visual Basic], copying directories
- I/O [Visual Basic], copying folders
- folders [Visual Basic], copying
- directories [Visual Basic], copying
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
caps.latest.revision: 19
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
ms.openlocfilehash: 7bcc7f924d26247b0d0ab30a9ea0fc6d6333b652
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-a-directory-to-another-directory-in-visual-basic"></a><span data-ttu-id="9d7a2-102">Procedura: copiare una directory in un'altra directory di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d7a2-102">How to: Copy a Directory to Another Directory in Visual Basic</span></span>
<span data-ttu-id="9d7a2-103">Usare il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> per copiare una directory in un'altra directory.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-103">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> method to copy a directory to another directory.</span></span> <span data-ttu-id="9d7a2-104">Questo metodo consente di copiare il contenuto della directory nonché la directory stessa.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-104">This method copies the contents of the directory as well as the directory itself.</span></span> <span data-ttu-id="9d7a2-105">Se la directory di destinazione non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-105">If the target directory does not exist, it will be created.</span></span> <span data-ttu-id="9d7a2-106">Se è presente una directory con lo stesso nome nel percorso di destinazione e `overwrite` è impostato su `False`, il contenuto delle due directory viene unito.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-106">If a directory with the same name exists in the target location and `overwrite` is set to `False`, the contents of the two directories will be merged.</span></span> <span data-ttu-id="9d7a2-107">È possibile specificare un nuovo nome per la directory durante l'operazione.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-107">You can specify a new name for the directory during the operation.</span></span>  
  
 <span data-ttu-id="9d7a2-108">Quando si copiano file in una directory, è possibile che vengano generate eccezioni causate da un file specifico, ad esempio un file presente durante un'unione con `overwrite` impostato su `False`.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-108">When copying files within a directory, exceptions may be thrown that are caused by specific file, such as a file existing during a merge while `overwrite` is set to `False`.</span></span> <span data-ttu-id="9d7a2-109">Quando vengono generate, queste eccezioni vengono consolidate in un'unica eccezione, la cui proprietà `Data` contiene le voci in cui il percorso del file o della directory è la chiave e il messaggio di eccezione specifico è contenuto nel valore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-109">When such exceptions are thrown, they are consolidated into a single exception, whose `Data` property holds entries in which the file or directory path is the key and the specific exception message is contained in the corresponding value.</span></span>  
  
### <a name="to-copy-a-directory-to-another-directory"></a><span data-ttu-id="9d7a2-110">Per copiare una directory in un'altra directory</span><span class="sxs-lookup"><span data-stu-id="9d7a2-110">To copy a directory to another directory</span></span>  
  
-   <span data-ttu-id="9d7a2-111">Usare il metodo `CopyDirectory` specificando i nomi della directory di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-111">Use the `CopyDirectory` method, specifying source and destination directory names.</span></span> <span data-ttu-id="9d7a2-112">Nell'esempio di codice riportato di seguito la directory denominata `TestDirectory1` viene copiata in `TestDirectory2`, sovrascrivendo i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-112">The following example copies the directory named `TestDirectory1` into `TestDirectory2`, overwriting existing files.</span></span>  
  
     <span data-ttu-id="9d7a2-113">[!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-a-directory-to-another-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9d7a2-113">[!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-a-directory-to-another-directory_1.vb)]</span></span>  
  
     <span data-ttu-id="9d7a2-114">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-114">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="9d7a2-115">Nella casella di selezione dei frammenti di codice si trova in **File system - Elaborazione di unità, cartelle e file**.</span><span class="sxs-lookup"><span data-stu-id="9d7a2-115">In the code snippet picker, it is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="9d7a2-116">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-116">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9d7a2-117">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="9d7a2-117">Robust Programming</span></span>  
 <span data-ttu-id="9d7a2-118">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="9d7a2-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="9d7a2-119">Il nuovo nome specificato per la directory contiene il segno dei due punti (:) o una barra (\ o /) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-119">The new name specified for the directory contains a colon (:) or slash (\ or /) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-120">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-120">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-121">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-121">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-122">`destinationDirectoryName` è `Nothing` o una stringa vuota (<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="9d7a2-122">`destinationDirectoryName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="9d7a2-123">La directory di origine non esiste (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-123">The source directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-124">La directory di origine è una directory radice (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-124">The source directory is a root directory (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-125">Il percorso combinato punta a un file esistente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-125">The combined path points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-126">Il percorso di origine e il percorso di destinazione coincidono (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-126">The source path and target path are the same (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-127">`ShowUI` è impostato su `UIOption.AllDialogs` e l'utente annulla l'operazione oppure non è possibile copiare uno o più file nella directory (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-127">`ShowUI` is set to `UIOption.AllDialogs` and the user cancels the operation, or one or more files in the directory cannot be copied (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-128">L'operazione è ciclica (<xref:System.InvalidOperationException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-128">The operation is cyclic (<xref:System.InvalidOperationException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-129">Il percorso contiene i due punti (:) (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-129">The path contains a colon (:) (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-130">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-130">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-131">Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-131">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-132">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-132">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="9d7a2-133">Esiste un file di destinazione ma non è possibile accedervi (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="9d7a2-133">A destination file exists but cannot be accessed (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d7a2-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d7a2-134">See Also</span></span>  
 <span data-ttu-id="9d7a2-135"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A></span><span class="sxs-lookup"><span data-stu-id="9d7a2-135"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A></span></span>   
 <span data-ttu-id="9d7a2-136">[Procedura: Cercare sottodirectory con un modello specifico](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="9d7a2-136">[How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md) </span></span>  
 [<span data-ttu-id="9d7a2-137">Procedura: ottenere la raccolta di file di una directory</span><span class="sxs-lookup"><span data-stu-id="9d7a2-137">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

