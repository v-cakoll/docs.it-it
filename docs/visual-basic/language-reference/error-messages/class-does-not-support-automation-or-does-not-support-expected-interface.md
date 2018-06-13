---
title: La classe non supporta l'automazione o l'interfaccia prevista
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: 860c472794495ef2be37aea7c7d8305c237dfd13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585674"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="69682-102">La classe non supporta l'automazione o l'interfaccia prevista</span><span class="sxs-lookup"><span data-stu-id="69682-102">Class does not support Automation or does not support expected interface</span></span>
<span data-ttu-id="69682-103">La classe specificata nella funzione `GetObject` o `CreateObject` non ha esposto un'interfaccia di programmabilità oppure è stato modificato un progetto da .dll a .exe o viceversa.</span><span class="sxs-lookup"><span data-stu-id="69682-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="69682-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="69682-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="69682-105">Consultare la documentazione dell'applicazione che ha creato l'oggetto per verificare l'eventuale presenza di limitazioni sull'uso dell'automazione.</span><span class="sxs-lookup"><span data-stu-id="69682-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2.  <span data-ttu-id="69682-106">Se è stato modificato un progetto da .dll a .exe o viceversa, è necessario annullare manualmente la registrazione del precedente .dll o .exe.</span><span class="sxs-lookup"><span data-stu-id="69682-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69682-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69682-107">See Also</span></span>  
 [<span data-ttu-id="69682-108">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="69682-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 <span data-ttu-id="69682-109">[Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="69682-109">[Talk to Us](/visualstudio/ide/talk-to-us)</span></span>
