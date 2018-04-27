---
title: Troppe applicazioni client DLL
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 78b3291531c2097fb4124486f6fbac40e2d13b8e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="54ed0-102">Troppe applicazioni client DLL</span><span class="sxs-lookup"><span data-stu-id="54ed0-102">Too many DLL application clients</span></span>
<span data-ttu-id="54ed0-103">La libreria di collegamento dinamico (DLL) per Visual Basic supporta solo l'accesso a un numero limitato di host applicazioni.</span><span class="sxs-lookup"><span data-stu-id="54ed0-103">The dynamic-link library (DLL) for Visual Basic can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="54ed0-104">L'applicazione e altre applicazioni che sono host di Visual Basic (alcune delle quali sono accessibili dall'applicazione) tutte siano provando ad accedere alla DLL di Visual Basic nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="54ed0-104">Your application and other applications that are Visual Basic hosts (some of which may be accessed by your application) are all attempting to access the Visual Basic DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="54ed0-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="54ed0-105">To correct this error</span></span>  
  
-   <span data-ttu-id="54ed0-106">Ridurre il numero di applicazioni aperte che accedono a Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="54ed0-106">Reduce the number of open applications accessing Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ed0-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54ed0-107">See Also</span></span>  
 [<span data-ttu-id="54ed0-108">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="54ed0-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
