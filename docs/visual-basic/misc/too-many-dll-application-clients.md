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
ms.openlocfilehash: d4b9278134e937ac8bf4626237954432d727ac0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="ee6cd-102">Troppe applicazioni client DLL</span><span class="sxs-lookup"><span data-stu-id="ee6cd-102">Too many DLL application clients</span></span>
<span data-ttu-id="ee6cd-103">La libreria di collegamento dinamico (DLL) per [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supporta solo l'accesso a un numero limitato di applicazioni host.</span><span class="sxs-lookup"><span data-stu-id="ee6cd-103">The dynamic-link library (DLL) for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="ee6cd-104">L'applicazione e altre applicazioni che sono host di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] (alcune delle quali sono accessibili dall'applicazione) stanno tentando di accedere contemporaneamente alla DLL [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee6cd-104">Your application and other applications that are [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] hosts (some of which may be accessed by your application) are all attempting to access the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ee6cd-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ee6cd-105">To correct this error</span></span>  
  
-   <span data-ttu-id="ee6cd-106">Ridurre il numero di applicazioni aperte che accedono a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee6cd-106">Reduce the number of open applications accessing [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee6cd-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee6cd-107">See Also</span></span>  
 [<span data-ttu-id="ee6cd-108">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="ee6cd-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
