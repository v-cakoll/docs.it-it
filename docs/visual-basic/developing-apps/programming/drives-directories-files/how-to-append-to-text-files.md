---
title: 'Procedura: aggiungere testo a file di testo in Visual Basic'
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
- I/O [Visual Basic], appending to files
- I/O [Visual Basic], My.Computer.FileSystem.WriteAllText method
- I/O [Visual Basic], WriteAllText method
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
caps.latest.revision: 13
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
ms.openlocfilehash: 3425c82ed73e4a6fbded187b9333f4083111e78f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-append-to-text-files-in-visual-basic"></a><span data-ttu-id="4a8ab-102">Procedura: aggiungere testo a file di testo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a8ab-102">How to: Append to Text Files in Visual Basic</span></span>
<span data-ttu-id="4a8ab-103">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> può essere usato per aggiungere testo a un file di testo specificando che il parametro `append` è impostato su `True`.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to append to a text file by specifying that the `append` parameter is set to `True`.</span></span>  
  
### <a name="to-append-to-a-text-file"></a><span data-ttu-id="4a8ab-104">Per aggiungere testo a file di testo</span><span class="sxs-lookup"><span data-stu-id="4a8ab-104">To append to a text file</span></span>  
  
-   <span data-ttu-id="4a8ab-105">Usare il metodo `WriteAllText` specificando il file di destinazione e la stringa da aggiungere e impostando il parametro `append` su `True`.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-105">Use the `WriteAllText` method, specifying the target file and string to be appended and setting the `append` parameter to `True`.</span></span>  
  
     <span data-ttu-id="4a8ab-106">Nell'esempio riportato di seguito la stringa `"This is a test string."` viene scritta nel file denominato `Testfile.txt`.</span><span class="sxs-lookup"><span data-stu-id="4a8ab-106">This example writes the string `"This is a test string."` to the file named `Testfile.txt`.</span></span>  
  
     <span data-ttu-id="4a8ab-107">[!code-vb[VbFileIOWrite#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-append-to-text-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4a8ab-107">[!code-vb[VbFileIOWrite#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-append-to-text-files_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4a8ab-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="4a8ab-108">Robust Programming</span></span>  
 <span data-ttu-id="4a8ab-109">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="4a8ab-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="4a8ab-110">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="4a8ab-110">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="4a8ab-111">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="4a8ab-111">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="4a8ab-112">`File` punta a un percorso che non esiste (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="4a8ab-112">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="4a8ab-113">Il file è in uso in un altro processo oppure si verifica un errore di I/O (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4a8ab-113">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4a8ab-114">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="4a8ab-114">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="4a8ab-115">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="4a8ab-115">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="4a8ab-116">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="4a8ab-116">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8ab-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a8ab-117">See Also</span></span>  
 <span data-ttu-id="4a8ab-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A></span><span class="sxs-lookup"><span data-stu-id="4a8ab-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A></span></span>   
 <span data-ttu-id="4a8ab-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="4a8ab-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 [<span data-ttu-id="4a8ab-120">Scrittura su file</span><span class="sxs-lookup"><span data-stu-id="4a8ab-120">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)

