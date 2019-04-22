---
title: "'<typename>' è un tipo delegato"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c308805f5e73d740ff18a40d95b9cc2576ac95fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841258"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="f7da9-102">'\<nomeTipo >' è un tipo delegato</span><span class="sxs-lookup"><span data-stu-id="f7da9-102">'\<typename>' is a delegate type</span></span>
<span data-ttu-id="f7da9-103">'\<nomeTipo >' è un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="f7da9-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="f7da9-104">Creazione di delegati consente solo una singola espressione AddressOf come un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7da9-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="f7da9-105">Spesso un'espressione AddressOf può essere utilizzata invece una costruzione di delegato.</span><span class="sxs-lookup"><span data-stu-id="f7da9-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="f7da9-106">Oggetto `New` clausola che crea un'istanza di una classe delegata fornisce un elenco di argomenti non valido al costruttore di delegato.</span><span class="sxs-lookup"><span data-stu-id="f7da9-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="f7da9-107">È possibile fornire una sola `AddressOf` espressione quando si crea una nuova istanza di delegato.</span><span class="sxs-lookup"><span data-stu-id="f7da9-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="f7da9-108">Questo errore può verificarsi se non si passano argomenti al costruttore di delegato, se si passa più di un argomento, o se si passa un singolo argomento che non è valida `AddressOf` espressione.</span><span class="sxs-lookup"><span data-stu-id="f7da9-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="f7da9-109">**ID errore:** BC32008</span><span class="sxs-lookup"><span data-stu-id="f7da9-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f7da9-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f7da9-110">To correct this error</span></span>  
  
-   <span data-ttu-id="f7da9-111">Usare una sola `AddressOf` espressione nell'elenco di argomenti per la classe delegata nel `New` clausola.</span><span class="sxs-lookup"><span data-stu-id="f7da9-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7da9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7da9-112">See also</span></span>

- [<span data-ttu-id="f7da9-113">Operatore New</span><span class="sxs-lookup"><span data-stu-id="f7da9-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="f7da9-114">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="f7da9-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="f7da9-115">Delegati</span><span class="sxs-lookup"><span data-stu-id="f7da9-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="f7da9-116">Procedura: Richiamare un metodo delegato</span><span class="sxs-lookup"><span data-stu-id="f7da9-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
