---
title: Una chiamata a una proprietà o a un metodo non può includere un riferimento a un oggetto privato, né come argomento né come valore restituito
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cce2bc67beb7e4ac0664b5b7240f5eb3ea0204f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a><span data-ttu-id="86889-102">Una chiamata a una proprietà o a un metodo non può includere un riferimento a un oggetto privato, né come argomento né come valore restituito</span><span class="sxs-lookup"><span data-stu-id="86889-102">A property or method call cannot include a reference to a private object, either as an argument or as a return value</span></span>
<span data-ttu-id="86889-103">Di seguito sono riportate le cause possibili dell'errore:</span><span class="sxs-lookup"><span data-stu-id="86889-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="86889-104">Un client ha richiamato una proprietà o un metodo di un componente out-of-process e ha tentato di passare un riferimento a un oggetto privato come uno degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="86889-104">A client invoked a property or method of an out-of-process component and attempted to pass a reference to a private object as one of the arguments.</span></span>  
  
-   <span data-ttu-id="86889-105">Un componente out-of-process ha richiamato un metodo di richiamata sul relativo client e ha tentato di passare un riferimento a un oggetto privato.</span><span class="sxs-lookup"><span data-stu-id="86889-105">An out-of-process component invoked a call-back method on its client and attempted to pass a reference to a private object.</span></span>  
  
-   <span data-ttu-id="86889-106">Un componente out-of-process ha tentato di passare un riferimento a un oggetto privato come argomento dell'evento che stava generando.</span><span class="sxs-lookup"><span data-stu-id="86889-106">An out-of-process component attempted to pass a reference to a private object as an argument of an event it was raising.</span></span>  
  
-   <span data-ttu-id="86889-107">Un client ha tentato di assegnare un riferimento a un oggetto privato a un argomento `ByRef` dell'evento che stava gestendo.</span><span class="sxs-lookup"><span data-stu-id="86889-107">A client attempted to assign a private object reference to a `ByRef` argument of an event it was handling.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="86889-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="86889-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="86889-109">Rimuovere il riferimento.</span><span class="sxs-lookup"><span data-stu-id="86889-109">Remove the reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86889-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86889-110">See Also</span></span>  
 [<span data-ttu-id="86889-111">Private</span><span class="sxs-lookup"><span data-stu-id="86889-111">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
