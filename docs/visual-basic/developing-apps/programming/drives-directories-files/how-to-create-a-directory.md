---
title: 'Procedura: creare una directory in Visual Basic'
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
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
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
ms.openlocfilehash: 1a45a785916b480dcee6e36fd295390266eaa0a0
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="7ec31-102">Procedura: creare una directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ec31-102">How to: Create a Directory in Visual Basic</span></span>
<span data-ttu-id="7ec31-103">Usare il metodo `CreateDirectory` dell'oggetto `My.Computer.FileSystem` per la creazione di directory.</span><span class="sxs-lookup"><span data-stu-id="7ec31-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="7ec31-104">Se la directory esiste già, non verranno generate eccezioni.</span><span class="sxs-lookup"><span data-stu-id="7ec31-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="7ec31-105">Per creare una directory</span><span class="sxs-lookup"><span data-stu-id="7ec31-105">To create a directory</span></span>  
  
-   <span data-ttu-id="7ec31-106">Usare il metodo `CreateDirectory` specificando il percorso completo della posizione in cui deve essere creata la directory.</span><span class="sxs-lookup"><span data-stu-id="7ec31-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="7ec31-107">Nell'esempio riportato di seguito la directory `NewDirectory` viene creata in `C:\Documents and Settings\All Users\Documents`.</span><span class="sxs-lookup"><span data-stu-id="7ec31-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     <span data-ttu-id="7ec31-108">[!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7ec31-108">[!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7ec31-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="7ec31-109">Robust Programming</span></span>  
 <span data-ttu-id="7ec31-110">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="7ec31-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="7ec31-111">Il nome della directory non è valido.</span><span class="sxs-lookup"><span data-stu-id="7ec31-111">The directory name is malformed.</span></span> <span data-ttu-id="7ec31-112">Contiene ad esempio caratteri non validi o è costituito solo da uno spazio (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="7ec31-112">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="7ec31-113">La directory padre della directory da creare è di sola lettura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="7ec31-113">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="7ec31-114">Il nome della directory è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="7ec31-114">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="7ec31-115">Il nome della directory è troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="7ec31-115">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="7ec31-116">Il nome della directory è un carattere due punti ":" (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="7ec31-116">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="7ec31-117">L'utente non è autorizzato a creare la directory (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="7ec31-117">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="7ec31-118">L'utente non ha le autorizzazioni richieste in una situazione di attendibilità parziale (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="7ec31-118">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec31-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ec31-119">See Also</span></span>  
 <span data-ttu-id="7ec31-120"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A></span><span class="sxs-lookup"><span data-stu-id="7ec31-120"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A></span></span>   
 [<span data-ttu-id="7ec31-121">Creazione, eliminazione e spostamento di file e directory</span><span class="sxs-lookup"><span data-stu-id="7ec31-121">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)

