---
title: 'Procedura: Copiare file con un criterio specifico in una directory'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
ms.openlocfilehash: 7e263e2c9035db54dbb58c6c78c0647d5442504e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401706"
---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a><span data-ttu-id="262f4-102">Procedura: copiare file con un criterio specifico in una directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="262f4-102">How to: Copy Files with a Specific Pattern to a Directory in Visual Basic</span></span>

<span data-ttu-id="262f4-103">Il metodo <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> restituisce una raccolta di stringhe di sola lettura che rappresentano i nomi di percorso per i file.</span><span class="sxs-lookup"><span data-stu-id="262f4-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="262f4-104">È possibile usare il parametro `wildCards` per specificare un criterio specifico.</span><span class="sxs-lookup"><span data-stu-id="262f4-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span>  
  
 <span data-ttu-id="262f4-105">Se non vengono individuati file corrispondenti, viene restituita una raccolta vuota.</span><span class="sxs-lookup"><span data-stu-id="262f4-105">An empty collection is returned if no matching files are found.</span></span>  
  
 <span data-ttu-id="262f4-106">È possibile usare il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> per copiare i file in una directory.</span><span class="sxs-lookup"><span data-stu-id="262f4-106">You can use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> method to copy the files to a directory.</span></span>  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a><span data-ttu-id="262f4-107">Per copiare file con un criterio specifico in una directory</span><span class="sxs-lookup"><span data-stu-id="262f4-107">To copy files with a specific pattern to a directory</span></span>  
  
1. <span data-ttu-id="262f4-108">Usare il metodo `GetFiles` per restituire l'elenco dei file.</span><span class="sxs-lookup"><span data-stu-id="262f4-108">Use the `GetFiles` method to return the list of files.</span></span> <span data-ttu-id="262f4-109">In questo esempio vengono restituiti tutti i file RTF nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="262f4-109">This example returns all .rtf files in the specified directory.</span></span>  
  
     [!code-vb[VbFileIOMisc#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#36)]  
  
2. <span data-ttu-id="262f4-110">Usare il metodo `CopyFile` per copiare i file.</span><span class="sxs-lookup"><span data-stu-id="262f4-110">Use the `CopyFile` method to copy the files.</span></span> <span data-ttu-id="262f4-111">In questo esempio i file vengono copiati nella directory denominata `testdirectory`.</span><span class="sxs-lookup"><span data-stu-id="262f4-111">This example copies the files to the directory named `testdirectory`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#88)]  
  
3. <span data-ttu-id="262f4-112">Chiudere l'istruzione `For` con un'istruzione `Next` .</span><span class="sxs-lookup"><span data-stu-id="262f4-112">Close the `For` statement with a `Next` statement.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#89)]  
  
## <a name="example"></a><span data-ttu-id="262f4-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="262f4-113">Example</span></span>  

 <span data-ttu-id="262f4-114">Nell'esempio seguente, che presenta i frammenti di codice precedenti in forma completa, tutti i file RTF nella directory specificata vengono copiati nella directory denominata `testdirectory`.</span><span class="sxs-lookup"><span data-stu-id="262f4-114">The following example, which presents the above snippets in complete form, copies all .rtf files in the specified directory to the directory named `testdirectory`.</span></span>  
  
 [!code-vb[VbFileIOMisc#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#37)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="262f4-115">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="262f4-115">.NET Framework Security</span></span>  

 <span data-ttu-id="262f4-116">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="262f4-116">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="262f4-117">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="262f4-117">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="262f4-118">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="262f4-118">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="262f4-119">La directory non esiste (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="262f4-119">The directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="262f4-120">La directory punta a un file esistente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="262f4-120">The directory points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="262f4-121">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="262f4-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="262f4-122">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="262f4-122">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="262f4-123">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="262f4-123">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span> <span data-ttu-id="262f4-124">L'utente non dispone delle autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="262f4-124">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="262f4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="262f4-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [<span data-ttu-id="262f4-126">Procedura: Trovare sottodirectory con un criterio specifico</span><span class="sxs-lookup"><span data-stu-id="262f4-126">How to: Find Subdirectories with a Specific Pattern</span></span>](how-to-find-subdirectories-with-a-specific-pattern.md)
- [<span data-ttu-id="262f4-127">Risoluzione dei problemi: Lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="262f4-127">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="262f4-128">Procedura: Ottenere la raccolta di file di una directory</span><span class="sxs-lookup"><span data-stu-id="262f4-128">How to: Get the Collection of Files in a Directory</span></span>](how-to-get-the-collection-of-files-in-a-directory.md)
