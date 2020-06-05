---
title: L'istruzione 'Class' deve terminare con un 'End Class' corrispondente
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 01c231f577d21028e9ef92f37c7ac5f7f1fe2aa3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415388"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="da055-102">L'istruzione 'Class' deve terminare con un 'End Class' corrispondente</span><span class="sxs-lookup"><span data-stu-id="da055-102">'Class' statement must end with a matching 'End Class'</span></span>
<span data-ttu-id="da055-103">`Class`viene usato per avviare un `Class` blocco, quindi può essere visualizzato solo all'inizio del blocco, con un'istruzione corrispondente che `End Class` termina il blocco.</span><span class="sxs-lookup"><span data-stu-id="da055-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="da055-104">È presente un'istruzione ridondante `Class` oppure il blocco non è stato terminato `Class` con `End Class` .</span><span class="sxs-lookup"><span data-stu-id="da055-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="da055-105">**ID errore:** BC30481</span><span class="sxs-lookup"><span data-stu-id="da055-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="da055-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="da055-106">To correct this error</span></span>  
  
- <span data-ttu-id="da055-107">Individuare e rimuovere l'istruzione `Class` non necessaria.</span><span class="sxs-lookup"><span data-stu-id="da055-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
- <span data-ttu-id="da055-108">Terminare il `Class` blocco con un oggetto corrispondente `End Class` .</span><span class="sxs-lookup"><span data-stu-id="da055-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da055-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da055-109">See also</span></span>

- [<span data-ttu-id="da055-110">\<keyword>Istruzione End</span><span class="sxs-lookup"><span data-stu-id="da055-110">End \<keyword> Statement</span></span>](../statements/end-keyword-statement.md)
- [<span data-ttu-id="da055-111">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="da055-111">Class Statement</span></span>](../statements/class-statement.md)
