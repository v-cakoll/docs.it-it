---
title: Il costruttore '<name>' non può chiamare se stesso
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: ef20f74055a07071ef9634973c6852ac58c3143c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824720"
---
# <a name="constructor-name-cannot-call-itself"></a><span data-ttu-id="cd6da-102">Costruttore '\<nome >' non può chiamare se stesso</span><span class="sxs-lookup"><span data-stu-id="cd6da-102">Constructor '\<name>' cannot call itself</span></span>
<span data-ttu-id="cd6da-103">Oggetto `Sub New` routine in una classe o struttura chiama se stessa.</span><span class="sxs-lookup"><span data-stu-id="cd6da-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="cd6da-104">È lo scopo di un costruttore per inizializzare un'istanza di una classe o struttura quando viene inizialmente creato.</span><span class="sxs-lookup"><span data-stu-id="cd6da-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="cd6da-105">Una classe o struttura può avere diversi costruttori, purché dispongano di elenchi di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="cd6da-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="cd6da-106">Un costruttore è autorizzato a chiamare un altro costruttore per eseguire le funzionalità oltre a un proprio.</span><span class="sxs-lookup"><span data-stu-id="cd6da-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="cd6da-107">Ma non ha significato per un costruttore di chiamare se stesso e di fatto il risultato sarà una ricorsione infinita se è consentito.</span><span class="sxs-lookup"><span data-stu-id="cd6da-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="cd6da-108">**ID errore:** BC30298</span><span class="sxs-lookup"><span data-stu-id="cd6da-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cd6da-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="cd6da-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="cd6da-110">Controllare l'elenco di parametri del costruttore viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="cd6da-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="cd6da-111">Deve essere diverso da quello del costruttore effettua la chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd6da-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="cd6da-112">Se non si intende chiamare un costruttore diverso, rimuovere il `Sub New` chiamare interamente.</span><span class="sxs-lookup"><span data-stu-id="cd6da-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd6da-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd6da-113">See also</span></span>

- [<span data-ttu-id="cd6da-114">Durata degli oggetti: Come gli oggetti vengono creati ed eliminati</span><span class="sxs-lookup"><span data-stu-id="cd6da-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
