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
ms.openlocfilehash: 6e361cbe89f4c51f28199b008de817c2d48ef326
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825391"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="270c2-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="270c2-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="270c2-103">Specifica che una variabile o una proprietà può essere letto ma non è stato scritta.</span><span class="sxs-lookup"><span data-stu-id="270c2-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="270c2-104">Note</span><span class="sxs-lookup"><span data-stu-id="270c2-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="270c2-105">Regole</span><span class="sxs-lookup"><span data-stu-id="270c2-105">Rules</span></span>  
  
-   <span data-ttu-id="270c2-106">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="270c2-106">**Declaration Context.**</span></span> <span data-ttu-id="270c2-107">Si può usare `ReadOnly` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="270c2-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="270c2-108">Ciò significa che il contesto della dichiarazione per un `ReadOnly` elemento deve essere una classe, struttura o modulo e non può essere un file di origine, lo spazio dei nomi o procedure.</span><span class="sxs-lookup"><span data-stu-id="270c2-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="270c2-109">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="270c2-109">**Combined Modifiers.**</span></span> <span data-ttu-id="270c2-110">Non è possibile specificare `ReadOnly` insieme a `Static` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="270c2-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="270c2-111">**Assegnazione di un valore.**</span><span class="sxs-lookup"><span data-stu-id="270c2-111">**Assigning a Value.**</span></span> <span data-ttu-id="270c2-112">Utilizzo di codice un `ReadOnly` proprietà non è possibile impostarne il valore.</span><span class="sxs-lookup"><span data-stu-id="270c2-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="270c2-113">Ma il codice che ha accesso alla risorsa di archiviazione sottostante può assegnare o modificare il valore in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="270c2-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="270c2-114">È possibile assegnare un valore per un `ReadOnly` variabili solo nella relativa dichiarazione o nel costruttore della classe o struttura in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="270c2-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="270c2-115">Quando usare una variabile di sola lettura</span><span class="sxs-lookup"><span data-stu-id="270c2-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="270c2-116">Esistono situazioni in cui non è possibile usare una [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md) dichiarare e assegnare un valore costante.</span><span class="sxs-lookup"><span data-stu-id="270c2-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="270c2-117">Ad esempio, il `Const` istruzione potrebbe non accettare il tipo di dati da assegnare o non è in grado di calcolare il valore in fase di compilazione con un'espressione costante.</span><span class="sxs-lookup"><span data-stu-id="270c2-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="270c2-118">È il valore potrebbe non conoscere in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="270c2-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="270c2-119">In questi casi, è possibile usare un `ReadOnly` variabile per contenere un valore costante.</span><span class="sxs-lookup"><span data-stu-id="270c2-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="270c2-120">Se il tipo di dati della variabile è un tipo riferimento, ad esempio una matrice o un'istanza della classe, i relativi membri possono essere modificati anche se è la variabile stessa `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="270c2-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="270c2-121">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="270c2-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="270c2-122">Durante l'inizializzazione, la matrice a cui punta `characterArray()` conterrà "x", "y" e "z".</span><span class="sxs-lookup"><span data-stu-id="270c2-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="270c2-123">Poiché la variabile `characterArray` è `ReadOnly`, non è possibile modificare il valore dopo l'inizializzazione; ovvero, una nuova matrice non è possibile assegnare a esso.</span><span class="sxs-lookup"><span data-stu-id="270c2-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="270c2-124">Tuttavia, è possibile modificare i valori di uno o più dei membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="270c2-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="270c2-125">In seguito a una chiamata alla routine `changeArrayElement`, la matrice a cui punta `characterArray()` conterrà "x", "M" e "z".</span><span class="sxs-lookup"><span data-stu-id="270c2-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="270c2-126">Si noti che questo è simile alla dichiarazione di un parametro di routine [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), che impedisce la procedura di modificare l'argomento chiamante, ma consente di modificare i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="270c2-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="270c2-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="270c2-127">Example</span></span>  
 <span data-ttu-id="270c2-128">L'esempio seguente definisce un `ReadOnly` proprietà per la data di assunzione di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="270c2-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="270c2-129">La classe archivia il valore della proprietà internamente come una `Private` variabile e solo codice all'interno della classe è possibile modificare tale valore.</span><span class="sxs-lookup"><span data-stu-id="270c2-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="270c2-130">Tuttavia, la proprietà è `Public`, e qualsiasi codice che possa accedere alla classe possa leggere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="270c2-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 <span data-ttu-id="270c2-131">Il modificatore `ReadOnly` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="270c2-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="270c2-132">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="270c2-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="270c2-133">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="270c2-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="270c2-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="270c2-134">See also</span></span>

- [<span data-ttu-id="270c2-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="270c2-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="270c2-136">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="270c2-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
