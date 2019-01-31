---
title: "'<typename>' è un tipo delegato"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4278ea0fc6a8dc2c6a90b720d2da70b1c26f2a17
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283452"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="c732d-102">'\<nomeTipo >' è un tipo delegato</span><span class="sxs-lookup"><span data-stu-id="c732d-102">'\<typename>' is a delegate type</span></span>
<span data-ttu-id="c732d-103">'\<nomeTipo >' è un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="c732d-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="c732d-104">Creazione di delegati consente solo una singola espressione AddressOf come un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="c732d-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="c732d-105">Spesso un'espressione AddressOf può essere utilizzata invece una costruzione di delegato.</span><span class="sxs-lookup"><span data-stu-id="c732d-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="c732d-106">Oggetto `New` clausola che crea un'istanza di una classe delegata fornisce un elenco di argomenti non valido al costruttore di delegato.</span><span class="sxs-lookup"><span data-stu-id="c732d-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="c732d-107">È possibile fornire una sola `AddressOf` espressione quando si crea una nuova istanza di delegato.</span><span class="sxs-lookup"><span data-stu-id="c732d-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="c732d-108">Questo errore può verificarsi se non si passano argomenti al costruttore di delegato, se si passa più di un argomento, o se si passa un singolo argomento che non è valida `AddressOf` espressione.</span><span class="sxs-lookup"><span data-stu-id="c732d-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="c732d-109">**ID errore:** BC32008</span><span class="sxs-lookup"><span data-stu-id="c732d-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c732d-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c732d-110">To correct this error</span></span>  
  
-   <span data-ttu-id="c732d-111">Usare una sola `AddressOf` espressione nell'elenco di argomenti per la classe delegata nel `New` clausola.</span><span class="sxs-lookup"><span data-stu-id="c732d-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c732d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c732d-112">See also</span></span>
- [<span data-ttu-id="c732d-113">Operatore New</span><span class="sxs-lookup"><span data-stu-id="c732d-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="c732d-114">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="c732d-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="c732d-115">Delegati</span><span class="sxs-lookup"><span data-stu-id="c732d-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="c732d-116">Procedura: Richiamare un metodo delegato</span><span class="sxs-lookup"><span data-stu-id="c732d-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
