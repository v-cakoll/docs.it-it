---
title: Troppe applicazioni client DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
ms.openlocfilehash: e20f780e2029b382fa90473e1b762fc76604df98
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58051026"
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="77825-102">Troppe applicazioni client DLL</span><span class="sxs-lookup"><span data-stu-id="77825-102">Too many DLL application clients</span></span>
<span data-ttu-id="77825-103">La libreria di collegamento dinamico (DLL) per Visual Basic supporta solo l'accesso a un numero limitato di applicazioni host.</span><span class="sxs-lookup"><span data-stu-id="77825-103">The dynamic-link library (DLL) for Visual Basic can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="77825-104">L'applicazione e altre applicazioni che sono host di Visual Basic (alcuni dei quali è accessibile dall'applicazione) tutto siano provando ad accedere alla DLL di Visual Basic nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="77825-104">Your application and other applications that are Visual Basic hosts (some of which may be accessed by your application) are all attempting to access the Visual Basic DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="77825-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="77825-105">To correct this error</span></span>  
  
-   <span data-ttu-id="77825-106">Ridurre il numero di applicazioni aperte che accedono a Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77825-106">Reduce the number of open applications accessing Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77825-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77825-107">See also</span></span>

- [<span data-ttu-id="77825-108">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="77825-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
