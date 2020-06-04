---
title: Impossibile utilizzare '<expression>' come vincolo di tipo
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: e2ba411a5f0db21539a9cf99c7645b8c9309caab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409556"
---
# <a name="expression-cannot-be-used-as-a-type-constraint"></a><span data-ttu-id="a1070-102">Impossibile utilizzare '\<expression>' come vincolo di tipo</span><span class="sxs-lookup"><span data-stu-id="a1070-102">'\<expression>' cannot be used as a type constraint</span></span>
<span data-ttu-id="a1070-103">Un elenco di vincoli comprende un'espressione che non rappresenta un vincolo valido per un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="a1070-103">A constraint list includes an expression that does not represent a valid constraint on a type parameter.</span></span>  
  
 <span data-ttu-id="a1070-104">Un elenco di vincoli impone requisiti per l'argomento di tipo passato al parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="a1070-104">A constraint list imposes requirements on the type argument passed to the type parameter.</span></span> <span data-ttu-id="a1070-105">Si possono specificare i requisiti seguenti in qualsiasi combinazione:</span><span class="sxs-lookup"><span data-stu-id="a1070-105">You can specify the following requirements in any combination:</span></span>  
  
- <span data-ttu-id="a1070-106">L'argomento di tipo deve implementare una o più interfacce</span><span class="sxs-lookup"><span data-stu-id="a1070-106">The type argument must implement one or more interfaces</span></span>  
  
- <span data-ttu-id="a1070-107">L'argomento di tipo deve ereditare al massimo da una classe</span><span class="sxs-lookup"><span data-stu-id="a1070-107">The type argument must inherit from at most one class</span></span>  
  
- <span data-ttu-id="a1070-108">L'argomento di tipo deve esporre un costruttore senza parametri a cui il codice di creazione possa accedere (includere il vincolo `New` )</span><span class="sxs-lookup"><span data-stu-id="a1070-108">The type argument must expose a parameterless constructor that the creating code can access (include the `New` constraint)</span></span>  
  
 <span data-ttu-id="a1070-109">Se non si include alcuna classe o interfaccia specifica nell'elenco di vincoli, è possibile imporre un requisito più generale specificando una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1070-109">If you do not include any specific class or interface in the constraint list, you can impose a more general requirement by specifying one of the following:</span></span>  
  
- <span data-ttu-id="a1070-110">L'argomento di tipo deve essere un tipo valore (includere il vincolo `Structure` )</span><span class="sxs-lookup"><span data-stu-id="a1070-110">The type argument must be a value type (include the `Structure` constraint)</span></span>  
  
- <span data-ttu-id="a1070-111">L'argomento di tipo deve essere un tipo riferimento (includere il vincolo `Class` )</span><span class="sxs-lookup"><span data-stu-id="a1070-111">The type argument must be a reference type (include the `Class` constraint)</span></span>  
  
 <span data-ttu-id="a1070-112">Non è possibile specificare sia `Structure` che `Class` per lo stesso parametro di tipo e non è possibile specificare uno dei due vincoli più volte.</span><span class="sxs-lookup"><span data-stu-id="a1070-112">You cannot specify both `Structure` and `Class` for the same type parameter, and you cannot specify either one more than once.</span></span>  
  
 <span data-ttu-id="a1070-113">**ID errore:** BC32061</span><span class="sxs-lookup"><span data-stu-id="a1070-113">**Error ID:** BC32061</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a1070-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a1070-114">To correct this error</span></span>  
  
- <span data-ttu-id="a1070-115">Verificare che l'espressione e i suoi elementi siano digitati correttamente.</span><span class="sxs-lookup"><span data-stu-id="a1070-115">Verify that the expression and its elements are spelled correctly.</span></span>  
  
- <span data-ttu-id="a1070-116">Se l'espressione non soddisfa l'elenco di requisiti precedente, rimuoverla dall'elenco di vincoli.</span><span class="sxs-lookup"><span data-stu-id="a1070-116">If the expression does not qualify for the preceding list of requirements, remove it from the constraint list.</span></span>  
  
- <span data-ttu-id="a1070-117">Se l'espressione fa riferimento a un'interfaccia o a una classe, verificare che il compilatore possa accedere a quell'interfaccia o a quella classe.</span><span class="sxs-lookup"><span data-stu-id="a1070-117">If the expression refers to an interface or class, verify that the compiler has access to that interface or class.</span></span> <span data-ttu-id="a1070-118">Potrebbe essere necessario qualificarne il nome e anche aggiungere un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="a1070-118">You might need to qualify its name, and you might need to add a reference to your project.</span></span> <span data-ttu-id="a1070-119">Per ulteriori informazioni, vedere "riferimenti ai progetti" in [riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="a1070-119">For more information, see "References to Projects" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1070-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1070-120">See also</span></span>

- [<span data-ttu-id="a1070-121">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a1070-121">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="a1070-122">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="a1070-122">Value Types and Reference Types</span></span>](../../programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="a1070-123">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="a1070-123">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
