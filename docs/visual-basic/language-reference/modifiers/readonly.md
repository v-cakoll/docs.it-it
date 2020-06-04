---
title: ReadOnly
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
ms.openlocfilehash: 405297a25d4b948a6920bd989c7826e8b6f66bb4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398207"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="8a920-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a920-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="8a920-103">Specifica che una variabile o una proprietà può essere letta ma non scritta.</span><span class="sxs-lookup"><span data-stu-id="8a920-103">Specifies that a variable or property can be read but not written.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a920-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="8a920-104">Remarks</span></span>

## <a name="rules"></a><span data-ttu-id="8a920-105">Regole</span><span class="sxs-lookup"><span data-stu-id="8a920-105">Rules</span></span>

- <span data-ttu-id="8a920-106">\*\*Contesto della dichiarazione. \*\*</span><span class="sxs-lookup"><span data-stu-id="8a920-106">**Declaration Context.**</span></span> <span data-ttu-id="8a920-107">Si può usare `ReadOnly` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="8a920-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="8a920-108">Ciò significa che il contesto di dichiarazione per un `ReadOnly` elemento deve essere una classe, una struttura o un modulo e non può essere un file di origine, uno spazio dei nomi o una procedura.</span><span class="sxs-lookup"><span data-stu-id="8a920-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="8a920-109">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="8a920-109">**Combined Modifiers.**</span></span> <span data-ttu-id="8a920-110">Non è possibile specificare `ReadOnly` insieme `Static` a nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="8a920-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>

- <span data-ttu-id="8a920-111">**Assegnazione di un valore.**</span><span class="sxs-lookup"><span data-stu-id="8a920-111">**Assigning a Value.**</span></span> <span data-ttu-id="8a920-112">Il codice che utilizza una `ReadOnly` proprietà non può impostarne il valore.</span><span class="sxs-lookup"><span data-stu-id="8a920-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="8a920-113">Il codice che ha accesso all'archiviazione sottostante può tuttavia assegnare o modificare il valore in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="8a920-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>

     <span data-ttu-id="8a920-114">È possibile assegnare un valore a una `ReadOnly` variabile solo nella relativa dichiarazione o nel costruttore di una classe o struttura in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="8a920-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>

## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="8a920-115">Quando usare una variabile di sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a920-115">When to Use a ReadOnly Variable</span></span>

<span data-ttu-id="8a920-116">In alcune situazioni non è possibile utilizzare un' [istruzione Const](../statements/const-statement.md) per dichiarare e assegnare un valore costante.</span><span class="sxs-lookup"><span data-stu-id="8a920-116">There are situations in which you cannot use a [Const Statement](../statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="8a920-117">Ad esempio, l' `Const` istruzione potrebbe non accettare il tipo di dati che si desidera assegnare oppure potrebbe non essere possibile calcolare il valore in fase di compilazione con un'espressione costante.</span><span class="sxs-lookup"><span data-stu-id="8a920-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="8a920-118">Il valore potrebbe non essere ancora noto in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="8a920-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="8a920-119">In questi casi, è possibile usare una `ReadOnly` variabile per mantenere un valore costante.</span><span class="sxs-lookup"><span data-stu-id="8a920-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a920-120">Se il tipo di dati della variabile è un tipo di riferimento, ad esempio una matrice o un'istanza di classe, i relativi membri possono essere modificati anche se la variabile stessa è `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="8a920-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="8a920-121">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8a920-121">The following example illustrates this.</span></span>

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

<span data-ttu-id="8a920-122">Quando viene inizializzato, la matrice a cui fa riferimento `characterArray()` include "x", "y" e "z".</span><span class="sxs-lookup"><span data-stu-id="8a920-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="8a920-123">Poiché la variabile `characterArray` è `ReadOnly` , non è possibile modificarne il valore dopo l'inizializzazione, ovvero non è possibile assegnarvi una nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="8a920-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="8a920-124">Tuttavia, è possibile modificare i valori di uno o più membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="8a920-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="8a920-125">In seguito a una chiamata alla routine `ChangeArrayElement` , la matrice a cui fa riferimento `characterArray()` include "x", "M" e "z".</span><span class="sxs-lookup"><span data-stu-id="8a920-125">Following a call to the procedure `ChangeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>

<span data-ttu-id="8a920-126">Si noti che questo comportamento è simile alla dichiarazione di un parametro di routine come [ByVal](byval.md), che impedisce alla routine di modificare l'argomento chiamante stesso ma ne consente la modifica dei membri.</span><span class="sxs-lookup"><span data-stu-id="8a920-126">Note that this is similar to declaring a procedure parameter to be [ByVal](byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>

## <a name="example"></a><span data-ttu-id="8a920-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a920-127">Example</span></span>

<span data-ttu-id="8a920-128">Nell'esempio seguente viene definita una `ReadOnly` proprietà per la data di assunzione di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="8a920-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="8a920-129">La classe archivia il valore della proprietà internamente come `Private` variabile e solo il codice all'interno della classe può modificare tale valore.</span><span class="sxs-lookup"><span data-stu-id="8a920-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="8a920-130">Tuttavia, la proprietà è `Public` e qualsiasi codice in grado di accedere alla classe può leggere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8a920-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

<span data-ttu-id="8a920-131">Il modificatore `ReadOnly` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a920-131">The `ReadOnly` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="8a920-132">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="8a920-132">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="8a920-133">Property Statement</span><span class="sxs-lookup"><span data-stu-id="8a920-133">Property Statement</span></span>](../statements/property-statement.md)

## <a name="see-also"></a><span data-ttu-id="8a920-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a920-134">See also</span></span>

- [<span data-ttu-id="8a920-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="8a920-135">WriteOnly</span></span>](writeonly.md)
- [<span data-ttu-id="8a920-136">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8a920-136">Keywords</span></span>](../keywords/index.md)
