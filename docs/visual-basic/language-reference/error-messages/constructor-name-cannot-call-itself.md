---
title: Costruttore &#39; &lt;nome&gt; &#39; non può chiamare se stesso
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 069de813a0426230e19cddf14c3b83d40a602a41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588996"
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a><span data-ttu-id="aad3e-102">Costruttore &#39; &lt;nome&gt; &#39; non può chiamare se stesso</span><span class="sxs-lookup"><span data-stu-id="aad3e-102">Constructor &#39;&lt;name&gt;&#39; cannot call itself</span></span>
<span data-ttu-id="aad3e-103">Oggetto `Sub New` routine in una classe o struttura chiama se stessa.</span><span class="sxs-lookup"><span data-stu-id="aad3e-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="aad3e-104">Lo scopo di un costruttore è inizializzare un'istanza di una classe o struttura quando viene inizialmente creato.</span><span class="sxs-lookup"><span data-stu-id="aad3e-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="aad3e-105">Una classe o struttura può contenere più costruttori, purché dispongano di elenchi di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="aad3e-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="aad3e-106">Un costruttore è autorizzato a chiamare un altro costruttore per eseguire le funzionalità oltre a proprio.</span><span class="sxs-lookup"><span data-stu-id="aad3e-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="aad3e-107">Ma non ha significato per un costruttore da chiamare se stesso e in realtà il risultato sarà una ricorsione infinita se è consentito.</span><span class="sxs-lookup"><span data-stu-id="aad3e-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="aad3e-108">**ID errore:** BC30298</span><span class="sxs-lookup"><span data-stu-id="aad3e-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="aad3e-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="aad3e-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="aad3e-110">Controllare l'elenco di parametri del costruttore da chiamare.</span><span class="sxs-lookup"><span data-stu-id="aad3e-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="aad3e-111">Deve essere diversa da quella del costruttore della chiamata.</span><span class="sxs-lookup"><span data-stu-id="aad3e-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="aad3e-112">Se non si intende chiamare un costruttore diverso, rimuovere il `Sub New` chiamare completamente.</span><span class="sxs-lookup"><span data-stu-id="aad3e-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad3e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aad3e-113">See Also</span></span>  
 [<span data-ttu-id="aad3e-114">Durata degli oggetti: come creare e distruggere oggetti</span><span class="sxs-lookup"><span data-stu-id="aad3e-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
