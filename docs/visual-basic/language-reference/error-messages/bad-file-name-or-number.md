---
title: Numero o nome file errato
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3d7c8bae3df0e75a1c4f9afacdff681a553503d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="b2bb7-102">Numero o nome file errato</span><span class="sxs-lookup"><span data-stu-id="b2bb7-102">Bad file name or number</span></span>
<span data-ttu-id="b2bb7-103">Si è verificato un errore durante il tentativo di accedere al file specificato.</span><span class="sxs-lookup"><span data-stu-id="b2bb7-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="b2bb7-104">Le cause possibili di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="b2bb7-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="b2bb7-105">Un'istruzione fa riferimento a un file con un nome file o un numero non è stato specificato nel `FileOpen` istruzione o che è stato specificato un `FileOpen` istruzione ma successivamente è chiuso.</span><span class="sxs-lookup"><span data-stu-id="b2bb7-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="b2bb7-106">Un'istruzione fa riferimento a un file con un numero che è compreso nell'intervallo dei numeri di file.</span><span class="sxs-lookup"><span data-stu-id="b2bb7-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="b2bb7-107">Un'istruzione fa riferimento a un nome file o un numero che non è valido.</span><span class="sxs-lookup"><span data-stu-id="b2bb7-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b2bb7-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b2bb7-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="b2bb7-109">Verificare che il nome del file è specificato un `FileOpen` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b2bb7-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="b2bb7-110">Si noti che se è stato richiamato il `FileClose` istruzione senza argomenti, sono stati inavvertitamente chiusi tutti i file aperti.</span><span class="sxs-lookup"><span data-stu-id="b2bb7-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2.  <span data-ttu-id="b2bb7-111">Il codice durante la generazione di numeri di file modo algoritmico, verificare che i numeri siano validi.</span><span class="sxs-lookup"><span data-stu-id="b2bb7-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3.  <span data-ttu-id="b2bb7-112">Controllare i nomi di file per assicurarsi che siano conformi alle convenzioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b2bb7-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bb7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2bb7-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [<span data-ttu-id="b2bb7-114">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2bb7-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
