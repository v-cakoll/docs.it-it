---
title: "&quot;&lt;typename&gt;&quot; è un tipo delegato | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
dev_langs:
- VB
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 55532e269a7d6756157d324a2db14320df5d3f55
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="d724b-102">'&lt;typename&gt;' è un tipo delegato</span><span class="sxs-lookup"><span data-stu-id="d724b-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="d724b-103">'\<typename >' è un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="d724b-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="d724b-104">Creazione di delegati consente solo una singola espressione AddressOf come un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="d724b-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="d724b-105">Spesso è possibile utilizzare un'espressione AddressOf anziché una costruzione di delegati.</span><span class="sxs-lookup"><span data-stu-id="d724b-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="d724b-106">Oggetto `New` clausola che crea un'istanza di una classe delegata fornisce un elenco di argomenti non valido al costruttore di delegato.</span><span class="sxs-lookup"><span data-stu-id="d724b-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="d724b-107">È possibile fornire una sola `AddressOf` espressione quando si crea una nuova istanza di delegato.</span><span class="sxs-lookup"><span data-stu-id="d724b-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="d724b-108">Questo errore può verificarsi se non si passano argomenti al costruttore di delegato, se si passano più argomenti, o se si passa un singolo argomento che non è valido `AddressOf` espressione.</span><span class="sxs-lookup"><span data-stu-id="d724b-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="d724b-109">**ID errore:** BC32008</span><span class="sxs-lookup"><span data-stu-id="d724b-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d724b-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d724b-110">To correct this error</span></span>  
  
-   <span data-ttu-id="d724b-111">Utilizzare una sola `AddressOf` espressione nell'elenco di argomenti per la classe delegata nella `New` clausola.</span><span class="sxs-lookup"><span data-stu-id="d724b-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d724b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d724b-112">See Also</span></span>  
 <span data-ttu-id="d724b-113">[Operatore new](../../../visual-basic/language-reference/operators/new-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d724b-113">[New Operator](../../../visual-basic/language-reference/operators/new-operator.md) </span></span>  
<span data-ttu-id="d724b-114"> [AddressOf (operatore)](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d724b-114"> [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="d724b-115"> [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="d724b-115"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="d724b-116"> [Procedura: Richiamare un metodo delegato](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span><span class="sxs-lookup"><span data-stu-id="d724b-116"> [How to: Invoke a Delegate Method](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span></span>
