---
title: '&#39; &lt;typename&gt;&#39; è un tipo delegato'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9428f0ac321b90e36d4d987381ed69b6c968894c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="edd51-102">&#39; &lt;typename&gt;&#39; è un tipo delegato</span><span class="sxs-lookup"><span data-stu-id="edd51-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="edd51-103">'\<nomeTipo >' è un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="edd51-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="edd51-104">Creazione di delegati consente solo una singola espressione AddressOf come un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="edd51-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="edd51-105">Spesso è possibile utilizzare un'espressione AddressOf anziché una costruzione di delegati.</span><span class="sxs-lookup"><span data-stu-id="edd51-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="edd51-106">Oggetto `New` clausola che crea un'istanza di una classe delegata fornisce un elenco di argomenti non valido al costruttore di delegato.</span><span class="sxs-lookup"><span data-stu-id="edd51-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="edd51-107">È possibile fornire una sola `AddressOf` espressione durante la creazione di una nuova istanza di delegato.</span><span class="sxs-lookup"><span data-stu-id="edd51-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="edd51-108">Questo errore può verificarsi se non si passano argomenti al costruttore di delegato, se si passano più argomenti, o se si passa un singolo argomento che non è un valido `AddressOf` espressione.</span><span class="sxs-lookup"><span data-stu-id="edd51-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="edd51-109">**ID errore:** BC32008</span><span class="sxs-lookup"><span data-stu-id="edd51-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="edd51-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="edd51-110">To correct this error</span></span>  
  
-   <span data-ttu-id="edd51-111">Usare un singolo `AddressOf` espressione nell'elenco di argomenti per la classe delegata nel `New` clausola.</span><span class="sxs-lookup"><span data-stu-id="edd51-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edd51-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edd51-112">See Also</span></span>  
 [<span data-ttu-id="edd51-113">Operatore New</span><span class="sxs-lookup"><span data-stu-id="edd51-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="edd51-114">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="edd51-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="edd51-115">Delegati</span><span class="sxs-lookup"><span data-stu-id="edd51-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="edd51-116">Procedura: Richiamare un metodo delegato</span><span class="sxs-lookup"><span data-stu-id="edd51-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
