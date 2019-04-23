---
title: Numero o nome file errato
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 2e5d4a3ddd66df85dc4758e22b36ac1ed495659a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322160"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="f7e88-102">Numero o nome file errato</span><span class="sxs-lookup"><span data-stu-id="f7e88-102">Bad file name or number</span></span>
<span data-ttu-id="f7e88-103">Si è verificato un errore durante il tentativo di accedere al file specificato.</span><span class="sxs-lookup"><span data-stu-id="f7e88-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="f7e88-104">Tra le possibili cause di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="f7e88-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="f7e88-105">Un'istruzione fa riferimento a un file con un nome file o un numero che non è stato specificato nel `FileOpen` istruzione o che è stato specificato un `FileOpen` istruzione ma è stata successivamente chiusi.</span><span class="sxs-lookup"><span data-stu-id="f7e88-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="f7e88-106">Un'istruzione fa riferimento a un file con un numero compreso nell'intervallo dei numeri di file.</span><span class="sxs-lookup"><span data-stu-id="f7e88-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="f7e88-107">Un'istruzione fa riferimento a un nome file o un numero non valido.</span><span class="sxs-lookup"><span data-stu-id="f7e88-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f7e88-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f7e88-108">To correct this error</span></span>  
  
1. <span data-ttu-id="f7e88-109">Assicurarsi che il nome del file è specificato un `FileOpen` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f7e88-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="f7e88-110">Si noti che se è stata richiamata la `FileClose` istruzione senza argomenti, si potrebbero avere inavvertitamente chiusi tutti i file aperti.</span><span class="sxs-lookup"><span data-stu-id="f7e88-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="f7e88-111">Il codice durante la generazione di numeri di file modo algoritmico, verificare che i numeri siano validi.</span><span class="sxs-lookup"><span data-stu-id="f7e88-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="f7e88-112">Controllare i nomi di file per assicurarsi che siano conformi alle convenzioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f7e88-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e88-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7e88-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="f7e88-114">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7e88-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
