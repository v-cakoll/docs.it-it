---
title: Numero o nome file errato
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 11e866d9a8da7ad1ecc5f788fc31f6ac96d32f2c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409829"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="2a6fc-102">Numero o nome file errato</span><span class="sxs-lookup"><span data-stu-id="2a6fc-102">Bad file name or number</span></span>
<span data-ttu-id="2a6fc-103">Si è verificato un errore durante il tentativo di accedere al file specificato.</span><span class="sxs-lookup"><span data-stu-id="2a6fc-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="2a6fc-104">Tra le possibili cause di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="2a6fc-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="2a6fc-105">Un'istruzione fa riferimento a un file con un nome o un numero di file non specificato nell' `FileOpen` istruzione o che è stato specificato in un' `FileOpen` istruzione ma che è stato successivamente chiuso.</span><span class="sxs-lookup"><span data-stu-id="2a6fc-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
- <span data-ttu-id="2a6fc-106">Un'istruzione fa riferimento a un file con un numero non compreso nell'intervallo di numeri di file.</span><span class="sxs-lookup"><span data-stu-id="2a6fc-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
- <span data-ttu-id="2a6fc-107">Un'istruzione fa riferimento a un nome o a un numero di file non valido.</span><span class="sxs-lookup"><span data-stu-id="2a6fc-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2a6fc-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2a6fc-108">To correct this error</span></span>  
  
1. <span data-ttu-id="2a6fc-109">Verificare che il nome del file sia specificato in un' `FileOpen` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2a6fc-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="2a6fc-110">Si noti che se è stata richiamata l' `FileClose` istruzione senza argomenti, è possibile che tutti i file aperti siano stati chiusi inavvertitamente.</span><span class="sxs-lookup"><span data-stu-id="2a6fc-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="2a6fc-111">Se il codice genera numeri di file algoritmicamente, verificare che i numeri siano validi.</span><span class="sxs-lookup"><span data-stu-id="2a6fc-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="2a6fc-112">Controllare i nomi dei file per assicurarsi che siano conformi alle convenzioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2a6fc-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6fc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a6fc-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="2a6fc-114">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a6fc-114">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
