---
title: Operatore New (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 630b0c48def77449f426b287a26f95af7cfb930e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936630"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="ec34b-102">Operatore New (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec34b-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="ec34b-103">Introduce un `New` clausola per creare una nuova istanza dell'oggetto, specifica un vincolo di costruttore su un parametro di tipo oppure identifica un `Sub` procedure come un costruttore di classe.</span><span class="sxs-lookup"><span data-stu-id="ec34b-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec34b-104">Note</span><span class="sxs-lookup"><span data-stu-id="ec34b-104">Remarks</span></span>  
 <span data-ttu-id="ec34b-105">In una dichiarazione o istruzione di assegnazione, un `New` clausola deve specificare una classe definita da cui è possibile creare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="ec34b-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="ec34b-106">Ciò significa che la classe deve esporre uno o più costruttori che il codice chiamante può accedere.</span><span class="sxs-lookup"><span data-stu-id="ec34b-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="ec34b-107">È possibile usare un `New` clausola in un'istruzione di dichiarazione o un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="ec34b-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="ec34b-108">Quando viene eseguita l'istruzione, chiama il costruttore appropriato della classe specificata, vengono passati gli argomenti forniti.</span><span class="sxs-lookup"><span data-stu-id="ec34b-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="ec34b-109">Nell'esempio seguente viene illustrata questa mediante la creazione di istanze di un `Customer` classe che dispone di due costruttori, uno che non accetta parametri e uno che accetta un parametro di stringa.</span><span class="sxs-lookup"><span data-stu-id="ec34b-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 <span data-ttu-id="ec34b-110">Poiché le matrici sono classi, `New` può creare una nuova istanza di matrice, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="ec34b-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 <span data-ttu-id="ec34b-111">Common language runtime (CLR) genera un <xref:System.OutOfMemoryException> errore se è disponibile memoria sufficiente per creare la nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="ec34b-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec34b-112">Il `New` (parola chiave) viene inoltre utilizzato in elenchi di parametri di tipo per specificare che il tipo fornito deve esporre un costruttore senza parametri accessibile.</span><span class="sxs-lookup"><span data-stu-id="ec34b-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="ec34b-113">Per altre informazioni sui parametri di tipo e sui vincoli, vedere [elenco di tipi](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="ec34b-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="ec34b-114">Per creare una routine di costruttore per una classe, impostare il nome di un `Sub` procedura per la `New` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="ec34b-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="ec34b-115">Per altre informazioni, vedere [durata degli oggetti: Come gli oggetti vengono creati e distrutti](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="ec34b-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="ec34b-116">È possibile usare la parola chiave `New` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec34b-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ec34b-117">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="ec34b-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="ec34b-118">Of</span><span class="sxs-lookup"><span data-stu-id="ec34b-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="ec34b-119">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="ec34b-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ec34b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec34b-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="ec34b-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ec34b-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="ec34b-122">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="ec34b-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="ec34b-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec34b-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="ec34b-124">Durata degli oggetti: Come gli oggetti vengono creati ed eliminati</span><span class="sxs-lookup"><span data-stu-id="ec34b-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
