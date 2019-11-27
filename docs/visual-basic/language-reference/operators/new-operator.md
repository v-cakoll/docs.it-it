---
title: Operatore New
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
ms.openlocfilehash: 27b5b4516ef729045036c36fedc24b6c576a4f61
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348310"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="a8e82-102">Operatore New (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8e82-102">New Operator (Visual Basic)</span></span>

<span data-ttu-id="a8e82-103">Introduce una clausola `New` per creare una nuova istanza dell'oggetto, specifica un vincolo del costruttore in un parametro di tipo o identifica una routine `Sub` come costruttore di classe.</span><span class="sxs-lookup"><span data-stu-id="a8e82-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8e82-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a8e82-104">Remarks</span></span>

<span data-ttu-id="a8e82-105">In una dichiarazione o un'istruzione di assegnazione, una clausola `New` deve specificare una classe definita dalla quale è possibile creare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="a8e82-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="a8e82-106">Questo significa che la classe deve esporre uno o più costruttori a cui il codice chiamante può accedere.</span><span class="sxs-lookup"><span data-stu-id="a8e82-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>

<span data-ttu-id="a8e82-107">È possibile utilizzare una clausola `New` in un'istruzione di dichiarazione o un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="a8e82-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="a8e82-108">Quando l'istruzione viene eseguita, viene chiamato il costruttore appropriato della classe specificata, passando gli argomenti specificati.</span><span class="sxs-lookup"><span data-stu-id="a8e82-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="a8e82-109">Nell'esempio seguente viene illustrato questo problema creando istanze di una classe `Customer` con due costruttori, uno che non accetta parametri e uno che accetta un parametro di stringa:</span><span class="sxs-lookup"><span data-stu-id="a8e82-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter:</span></span>

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

<span data-ttu-id="a8e82-110">Poiché le matrici sono classi, `New` possibile creare una nuova istanza di matrice, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a8e82-110">Since arrays are classes, `New` can create a new array instance, as shown in the following example:</span></span>

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

<span data-ttu-id="a8e82-111">Il Common Language Runtime (CLR) genera un errore di <xref:System.OutOfMemoryException> se la memoria disponibile non è sufficiente per creare la nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="a8e82-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>

> [!NOTE]
> <span data-ttu-id="a8e82-112">La parola chiave `New` viene utilizzata anche negli elenchi di parametri di tipo per specificare che il tipo fornito deve esporre un costruttore senza parametri accessibile.</span><span class="sxs-lookup"><span data-stu-id="a8e82-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="a8e82-113">Per ulteriori informazioni sui parametri e i vincoli di tipo, vedere [Type list](../statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="a8e82-113">For more information about type parameters and constraints, see [Type List](../statements/type-list.md).</span></span>

<span data-ttu-id="a8e82-114">Per creare una routine del costruttore per una classe, impostare il nome di una routine `Sub` sulla parola chiave `New`.</span><span class="sxs-lookup"><span data-stu-id="a8e82-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="a8e82-115">Per altre informazioni, vedere [durata degli oggetti: come creare ed eliminare definitivamente oggetti](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="a8e82-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

<span data-ttu-id="a8e82-116">È possibile usare la parola chiave `New` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8e82-116">The `New` keyword can be used in these contexts:</span></span>

- [<span data-ttu-id="a8e82-117">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="a8e82-117">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="a8e82-118">Of</span><span class="sxs-lookup"><span data-stu-id="a8e82-118">Of</span></span>](../statements/of-clause.md)
- [<span data-ttu-id="a8e82-119">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="a8e82-119">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="a8e82-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8e82-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="a8e82-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a8e82-121">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="a8e82-122">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="a8e82-122">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="a8e82-123">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8e82-123">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="a8e82-124">Durata degli oggetti: come creare e distruggere oggetti</span><span class="sxs-lookup"><span data-stu-id="a8e82-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
