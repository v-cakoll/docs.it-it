---
title: Una chiamata a una proprietà o a un metodo non può includere un riferimento a un oggetto privato, né come argomento né come valore restituito
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 5f0740af49bb369be87a1a33973b67f59acf3ab6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700832"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a><span data-ttu-id="02d37-102">Una chiamata a una proprietà o a un metodo non può includere un riferimento a un oggetto privato, né come argomento né come valore restituito</span><span class="sxs-lookup"><span data-stu-id="02d37-102">A property or method call cannot include a reference to a private object, either as an argument or as a return value</span></span>
<span data-ttu-id="02d37-103">Di seguito sono riportate le cause possibili dell'errore:</span><span class="sxs-lookup"><span data-stu-id="02d37-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="02d37-104">Un client ha richiamato una proprietà o un metodo di un componente out-of-process e ha tentato di passare un riferimento a un oggetto privato come uno degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="02d37-104">A client invoked a property or method of an out-of-process component and attempted to pass a reference to a private object as one of the arguments.</span></span>  
  
-   <span data-ttu-id="02d37-105">Un componente out-of-process ha richiamato un metodo di richiamata sul relativo client e ha tentato di passare un riferimento a un oggetto privato.</span><span class="sxs-lookup"><span data-stu-id="02d37-105">An out-of-process component invoked a call-back method on its client and attempted to pass a reference to a private object.</span></span>  
  
-   <span data-ttu-id="02d37-106">Un componente out-of-process ha tentato di passare un riferimento a un oggetto privato come argomento dell'evento che stava generando.</span><span class="sxs-lookup"><span data-stu-id="02d37-106">An out-of-process component attempted to pass a reference to a private object as an argument of an event it was raising.</span></span>  
  
-   <span data-ttu-id="02d37-107">Un client ha tentato di assegnare un riferimento a un oggetto privato a un argomento `ByRef` dell'evento che stava gestendo.</span><span class="sxs-lookup"><span data-stu-id="02d37-107">A client attempted to assign a private object reference to a `ByRef` argument of an event it was handling.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="02d37-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="02d37-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="02d37-109">Rimuovere il riferimento.</span><span class="sxs-lookup"><span data-stu-id="02d37-109">Remove the reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d37-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02d37-110">See also</span></span>
- [<span data-ttu-id="02d37-111">Private</span><span class="sxs-lookup"><span data-stu-id="02d37-111">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
