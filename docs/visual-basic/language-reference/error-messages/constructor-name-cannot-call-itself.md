---
title: Costruttore &#39; &lt;nome&gt;&#39; non può chiamare se stesso
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2361d6f4d710e17a4f4e29ac03bfde523191fa83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a><span data-ttu-id="ea7c8-102">Costruttore &#39; &lt;nome&gt;&#39; non può chiamare se stesso</span><span class="sxs-lookup"><span data-stu-id="ea7c8-102">Constructor &#39;&lt;name&gt;&#39; cannot call itself</span></span>
<span data-ttu-id="ea7c8-103">Oggetto `Sub New` routine in una classe o struttura chiama se stessa.</span><span class="sxs-lookup"><span data-stu-id="ea7c8-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="ea7c8-104">Lo scopo di un costruttore è inizializzare un'istanza di una classe o struttura quando viene inizialmente creato.</span><span class="sxs-lookup"><span data-stu-id="ea7c8-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="ea7c8-105">Una classe o struttura può contenere più costruttori, purché dispongano di elenchi di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="ea7c8-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="ea7c8-106">Un costruttore è autorizzato a chiamare un altro costruttore per eseguire le funzionalità oltre a proprio.</span><span class="sxs-lookup"><span data-stu-id="ea7c8-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="ea7c8-107">Ma non ha significato per un costruttore da chiamare se stesso e in realtà il risultato sarà una ricorsione infinita se è consentito.</span><span class="sxs-lookup"><span data-stu-id="ea7c8-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="ea7c8-108">**ID errore:** BC30298</span><span class="sxs-lookup"><span data-stu-id="ea7c8-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea7c8-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ea7c8-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="ea7c8-110">Controllare l'elenco di parametri del costruttore da chiamare.</span><span class="sxs-lookup"><span data-stu-id="ea7c8-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="ea7c8-111">Deve essere diversa da quella del costruttore della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ea7c8-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="ea7c8-112">Se non si intende chiamare un costruttore diverso, rimuovere il `Sub New` chiamare completamente.</span><span class="sxs-lookup"><span data-stu-id="ea7c8-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea7c8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea7c8-113">See Also</span></span>  
 [<span data-ttu-id="ea7c8-114">Durata degli oggetti: come creare e distruggere oggetti</span><span class="sxs-lookup"><span data-stu-id="ea7c8-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
