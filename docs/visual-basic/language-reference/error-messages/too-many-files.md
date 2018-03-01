---
title: Troppi file.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 506f0735956267d51b575cd26b628605e9db38cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-files"></a><span data-ttu-id="85f8a-102">Troppi file.</span><span class="sxs-lookup"><span data-stu-id="85f8a-102">Too many files</span></span>
<span data-ttu-id="85f8a-103">Più file sono stati creati nella directory radice di permesso dal sistema operativo o sono stati aperti più file rispetto al numero specificato nel **file =** nel file CONFIG. File SYS.</span><span class="sxs-lookup"><span data-stu-id="85f8a-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="85f8a-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="85f8a-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="85f8a-105">Se il programma è apertura, chiusura o salvataggio di file nella directory radice, modificare il programma in modo che utilizzi una sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="85f8a-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2.  <span data-ttu-id="85f8a-106">Aumentare il numero di file specificato per il **file =** nel file CONFIG. SYS file e riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="85f8a-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f8a-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85f8a-107">See Also</span></span>  
 [<span data-ttu-id="85f8a-108">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="85f8a-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
