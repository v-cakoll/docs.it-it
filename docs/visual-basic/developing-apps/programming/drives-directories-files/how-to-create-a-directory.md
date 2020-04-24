---
title: 'Procedura: creare una directory'
ms.date: 07/20/2015
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
ms.openlocfilehash: 3d838352a0a3dd69a1555dc34b8acba3afba278b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348804"
---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="ae9d0-102">Procedura: creare una directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae9d0-102">How to: Create a Directory in Visual Basic</span></span>

<span data-ttu-id="ae9d0-103">Usare il metodo `CreateDirectory` dell'oggetto `My.Computer.FileSystem` per la creazione di directory.</span><span class="sxs-lookup"><span data-stu-id="ae9d0-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="ae9d0-104">Se la directory esiste già, non verranno generate eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ae9d0-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="ae9d0-105">Per creare una directory</span><span class="sxs-lookup"><span data-stu-id="ae9d0-105">To create a directory</span></span>  
  
- <span data-ttu-id="ae9d0-106">Usare il metodo `CreateDirectory` specificando il percorso completo della posizione in cui deve essere creata la directory.</span><span class="sxs-lookup"><span data-stu-id="ae9d0-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="ae9d0-107">Nell'esempio riportato di seguito la directory `NewDirectory` viene creata in `C:\Documents and Settings\All Users\Documents`.</span><span class="sxs-lookup"><span data-stu-id="ae9d0-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ae9d0-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="ae9d0-108">Robust Programming</span></span>  

 <span data-ttu-id="ae9d0-109">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="ae9d0-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ae9d0-110">Il nome della directory non è valido.</span><span class="sxs-lookup"><span data-stu-id="ae9d0-110">The directory name is malformed.</span></span> <span data-ttu-id="ae9d0-111">Contiene ad esempio caratteri non validi o è costituito solo da uno spazio (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="ae9d0-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="ae9d0-112">La directory padre della directory da creare è di sola lettura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="ae9d0-112">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="ae9d0-113">Il nome della directory è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="ae9d0-113">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="ae9d0-114">Il nome della directory è troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="ae9d0-114">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="ae9d0-115">Il nome della directory è un carattere due punti ":" (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="ae9d0-115">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="ae9d0-116">L'utente non è autorizzato a creare la directory (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="ae9d0-116">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="ae9d0-117">L'utente non ha le autorizzazioni richieste in una situazione di attendibilità parziale (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="ae9d0-117">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9d0-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ae9d0-118">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>
- [<span data-ttu-id="ae9d0-119">Creazione, eliminazione e spostamento di file e directory</span><span class="sxs-lookup"><span data-stu-id="ae9d0-119">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
