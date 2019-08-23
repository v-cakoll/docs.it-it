---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 01c441576cb4247933c053f2043296733f99fdeb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965417"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="bf49e-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf49e-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="bf49e-103">Specifica che una variabile o una proprietà può essere letta ma non scritta.</span><span class="sxs-lookup"><span data-stu-id="bf49e-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf49e-104">Note</span><span class="sxs-lookup"><span data-stu-id="bf49e-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="bf49e-105">Regole</span><span class="sxs-lookup"><span data-stu-id="bf49e-105">Rules</span></span>  
  
- <span data-ttu-id="bf49e-106">**Contesto di dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="bf49e-106">**Declaration Context.**</span></span> <span data-ttu-id="bf49e-107">Si può usare `ReadOnly` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="bf49e-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="bf49e-108">Ciò significa che il contesto di Dichiarazione `ReadOnly` per un elemento deve essere una classe, una struttura o un modulo e non può essere un file di origine, uno spazio dei nomi o una procedura.</span><span class="sxs-lookup"><span data-stu-id="bf49e-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="bf49e-109">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="bf49e-109">**Combined Modifiers.**</span></span> <span data-ttu-id="bf49e-110">Non è possibile `ReadOnly` specificare `Static` insieme a nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="bf49e-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="bf49e-111">**Assegnazione di un valore.**</span><span class="sxs-lookup"><span data-stu-id="bf49e-111">**Assigning a Value.**</span></span> <span data-ttu-id="bf49e-112">Il codice che utilizza `ReadOnly` una proprietà non può impostarne il valore.</span><span class="sxs-lookup"><span data-stu-id="bf49e-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="bf49e-113">Il codice che ha accesso all'archiviazione sottostante può tuttavia assegnare o modificare il valore in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="bf49e-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="bf49e-114">È possibile assegnare un valore a una `ReadOnly` variabile solo nella relativa dichiarazione o nel costruttore di una classe o struttura in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="bf49e-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="bf49e-115">Quando usare una variabile di sola lettura</span><span class="sxs-lookup"><span data-stu-id="bf49e-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="bf49e-116">In alcune situazioni non è possibile utilizzare un' [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante.</span><span class="sxs-lookup"><span data-stu-id="bf49e-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="bf49e-117">Ad esempio, l' `Const` istruzione potrebbe non accettare il tipo di dati che si desidera assegnare oppure potrebbe non essere possibile calcolare il valore in fase di compilazione con un'espressione costante.</span><span class="sxs-lookup"><span data-stu-id="bf49e-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="bf49e-118">Il valore potrebbe non essere ancora noto in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bf49e-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="bf49e-119">In questi casi, è possibile usare una `ReadOnly` variabile per mantenere un valore costante.</span><span class="sxs-lookup"><span data-stu-id="bf49e-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bf49e-120">Se il tipo di dati della variabile è un tipo di riferimento, ad esempio una matrice o un'istanza di classe, i relativi membri possono essere modificati anche se la `ReadOnly`variabile stessa è.</span><span class="sxs-lookup"><span data-stu-id="bf49e-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="bf49e-121">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bf49e-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="bf49e-122">Quando viene inizializzato, la matrice a `characterArray()` cui fa riferimento include "x", "y" e "z".</span><span class="sxs-lookup"><span data-stu-id="bf49e-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="bf49e-123">Poiché la variabile `characterArray` è `ReadOnly`, non è possibile modificarne il valore dopo l'inizializzazione, ovvero non è possibile assegnarvi una nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="bf49e-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="bf49e-124">Tuttavia, è possibile modificare i valori di uno o più membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="bf49e-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="bf49e-125">In seguito a una chiamata alla `changeArrayElement`routine, la matrice `characterArray()` a cui fa riferimento include "x", "M" e "z".</span><span class="sxs-lookup"><span data-stu-id="bf49e-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="bf49e-126">Si noti che questo comportamento è simile alla dichiarazione di un parametro di routine come [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), che impedisce alla routine di modificare l'argomento chiamante stesso ma ne consente la modifica dei membri.</span><span class="sxs-lookup"><span data-stu-id="bf49e-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf49e-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf49e-127">Example</span></span>  
 <span data-ttu-id="bf49e-128">Nell'esempio seguente viene definita `ReadOnly` una proprietà per la data di assunzione di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="bf49e-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="bf49e-129">La classe archivia il valore della proprietà internamente `Private` come variabile e solo il codice all'interno della classe può modificare tale valore.</span><span class="sxs-lookup"><span data-stu-id="bf49e-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="bf49e-130">Tuttavia, la proprietà è `Public`e qualsiasi codice in grado di accedere alla classe può leggere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="bf49e-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 <span data-ttu-id="bf49e-131">Il modificatore `ReadOnly` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf49e-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="bf49e-132">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="bf49e-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="bf49e-133">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="bf49e-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bf49e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf49e-134">See also</span></span>

- [<span data-ttu-id="bf49e-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="bf49e-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="bf49e-136">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="bf49e-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
