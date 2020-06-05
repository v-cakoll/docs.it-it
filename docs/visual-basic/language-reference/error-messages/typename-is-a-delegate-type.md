---
title: "'<typename>' è un tipo delegato"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 7056bbf2b4de26feba3bfbe0e02b3239311271c9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382172"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="bb172-102">'\<typename>' è un tipo delegato</span><span class="sxs-lookup"><span data-stu-id="bb172-102">'\<typename>' is a delegate type</span></span>
<span data-ttu-id="bb172-103">' \<typename> ' è un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="bb172-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="bb172-104">La costruzione del delegato consente solo una singola espressione AddressOf come elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="bb172-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="bb172-105">Spesso è possibile usare un'espressione AddressOf anziché una costruzione di delegati.</span><span class="sxs-lookup"><span data-stu-id="bb172-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="bb172-106">Una `New` clausola che crea un'istanza di una classe Delegate fornisce un elenco di argomenti non valido al costruttore del delegato.</span><span class="sxs-lookup"><span data-stu-id="bb172-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="bb172-107">È possibile specificare una sola `AddressOf` espressione quando si crea una nuova istanza del delegato.</span><span class="sxs-lookup"><span data-stu-id="bb172-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="bb172-108">Questo errore può verificarsi se non si passano argomenti al costruttore del delegato, se si passa più di un argomento o se si passa un solo argomento che non è un' `AddressOf` espressione valida.</span><span class="sxs-lookup"><span data-stu-id="bb172-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="bb172-109">**ID errore:** BC32008</span><span class="sxs-lookup"><span data-stu-id="bb172-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bb172-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="bb172-110">To correct this error</span></span>  
  
- <span data-ttu-id="bb172-111">Usare una singola `AddressOf` espressione nell'elenco di argomenti per la classe delegata nella `New` clausola.</span><span class="sxs-lookup"><span data-stu-id="bb172-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb172-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb172-112">See also</span></span>

- [<span data-ttu-id="bb172-113">Operatore New</span><span class="sxs-lookup"><span data-stu-id="bb172-113">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="bb172-114">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="bb172-114">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="bb172-115">Delegati</span><span class="sxs-lookup"><span data-stu-id="bb172-115">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="bb172-116">Procedura: richiamare un metodo delegato</span><span class="sxs-lookup"><span data-stu-id="bb172-116">How to: Invoke a Delegate Method</span></span>](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
