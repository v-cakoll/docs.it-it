---
title: Troppi file.
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 38d39ad20f350137d714ae5d09db5d2204b83621
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362800"
---
# <a name="too-many-files"></a><span data-ttu-id="d572f-102">Troppi file.</span><span class="sxs-lookup"><span data-stu-id="d572f-102">Too many files</span></span>
<span data-ttu-id="d572f-103">Sono stati creati più file nella directory radice rispetto a quelli consentiti dal sistema operativo oppure sono stati aperti più file rispetto al numero specificato nell'impostazione **files =** della configurazione. File SYS.</span><span class="sxs-lookup"><span data-stu-id="d572f-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d572f-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d572f-104">To correct this error</span></span>  
  
1. <span data-ttu-id="d572f-105">Se il programma sta aprendo, chiudendo o salvando i file nella directory radice, modificare il programma in modo che usi una sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="d572f-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="d572f-106">Aumentare il numero di file specificati nell'impostazione **file =** nella configurazione. SYS e riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="d572f-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d572f-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d572f-107">See also</span></span>

- [<span data-ttu-id="d572f-108">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="d572f-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
