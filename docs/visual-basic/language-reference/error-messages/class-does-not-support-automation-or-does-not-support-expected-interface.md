---
title: La classe non supporta l'automazione o l'interfaccia prevista
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6528ceabeb7fb7a1cdc0beff2fd362632a0a0c9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="62ace-102">La classe non supporta l'automazione o l'interfaccia prevista</span><span class="sxs-lookup"><span data-stu-id="62ace-102">Class does not support Automation or does not support expected interface</span></span>
<span data-ttu-id="62ace-103">La classe specificata nella funzione `GetObject` o `CreateObject` non ha esposto un'interfaccia di programmabilità oppure è stato modificato un progetto da .dll a .exe o viceversa.</span><span class="sxs-lookup"><span data-stu-id="62ace-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="62ace-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="62ace-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="62ace-105">Consultare la documentazione dell'applicazione che ha creato l'oggetto per verificare l'eventuale presenza di limitazioni sull'uso dell'automazione.</span><span class="sxs-lookup"><span data-stu-id="62ace-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2.  <span data-ttu-id="62ace-106">Se è stato modificato un progetto da .dll a .exe o viceversa, è necessario annullare manualmente la registrazione del precedente .dll o .exe.</span><span class="sxs-lookup"><span data-stu-id="62ace-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ace-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62ace-107">See Also</span></span>  
 [<span data-ttu-id="62ace-108">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="62ace-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="62ace-109">Comunicazioni con Microsoft</span><span class="sxs-lookup"><span data-stu-id="62ace-109">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
