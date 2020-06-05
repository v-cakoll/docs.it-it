---
title: Il costruttore '<name>' non può chiamare se stesso
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 6abb6dde624e129b52fefecf8c51e6cde2567ae1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409803"
---
# <a name="constructor-name-cannot-call-itself"></a><span data-ttu-id="4a96c-102">Il costruttore '\<name>' non può chiamare se stesso</span><span class="sxs-lookup"><span data-stu-id="4a96c-102">Constructor '\<name>' cannot call itself</span></span>
<span data-ttu-id="4a96c-103">Una `Sub New` routine in una classe o in una struttura chiama se stessa.</span><span class="sxs-lookup"><span data-stu-id="4a96c-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="4a96c-104">Lo scopo di un costruttore è di inizializzare un'istanza di una classe o una struttura quando viene creata per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="4a96c-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="4a96c-105">Una classe o una struttura può avere più costruttori, purché tutti abbiano elenchi di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="4a96c-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="4a96c-106">Un costruttore è autorizzato a chiamare un altro costruttore per eseguirne la funzionalità oltre a se stesso.</span><span class="sxs-lookup"><span data-stu-id="4a96c-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="4a96c-107">Tuttavia, non è significativo per un costruttore chiamare se stesso e in realtà comporterebbe una ricorsione infinita se consentito.</span><span class="sxs-lookup"><span data-stu-id="4a96c-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="4a96c-108">**ID errore:** BC30298</span><span class="sxs-lookup"><span data-stu-id="4a96c-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4a96c-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4a96c-109">To correct this error</span></span>  
  
1. <span data-ttu-id="4a96c-110">Controllare l'elenco di parametri del costruttore chiamato.</span><span class="sxs-lookup"><span data-stu-id="4a96c-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="4a96c-111">Deve essere diverso da quello del costruttore che effettua la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a96c-111">It should be different from that of the constructor making the call.</span></span>  
  
2. <span data-ttu-id="4a96c-112">Se non si intende chiamare un costruttore diverso, rimuovere `Sub New` completamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a96c-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a96c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a96c-113">See also</span></span>

- [<span data-ttu-id="4a96c-114">Durata degli oggetti: come creare e distruggere oggetti</span><span class="sxs-lookup"><span data-stu-id="4a96c-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
