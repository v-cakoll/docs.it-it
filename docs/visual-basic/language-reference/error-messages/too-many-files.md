---
title: Troppi file.
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 1d7fc769a0a2d0f8474c0a72a5600b84c8396201
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310057"
---
# <a name="too-many-files"></a><span data-ttu-id="70d69-102">Troppi file.</span><span class="sxs-lookup"><span data-stu-id="70d69-102">Too many files</span></span>
<span data-ttu-id="70d69-103">Più file creati nella directory radice superiore a quello permesso del sistema operativo o sono stati aperti più file rispetto al numero specificato nella **file =** nel file CONFIG. File di SYS.</span><span class="sxs-lookup"><span data-stu-id="70d69-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="70d69-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="70d69-104">To correct this error</span></span>  
  
1. <span data-ttu-id="70d69-105">Se il programma è apertura, chiusura o il salvataggio dei file nella directory radice, modificare il programma in modo che utilizzi una sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="70d69-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="70d69-106">Aumentare il numero di file specificati nella **file =** nel file CONFIG. SYS file, quindi riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="70d69-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d69-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70d69-107">See also</span></span>

- [<span data-ttu-id="70d69-108">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="70d69-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
