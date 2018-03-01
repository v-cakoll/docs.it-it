---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9ca1d2e4eddb3b88073d6fcd46b0de5c627ba809
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="128cd-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="128cd-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="128cd-103">Specifica che una variabile o proprietà può essere letto ma non è stato scritto.</span><span class="sxs-lookup"><span data-stu-id="128cd-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="128cd-104">Note</span><span class="sxs-lookup"><span data-stu-id="128cd-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="128cd-105">Regole</span><span class="sxs-lookup"><span data-stu-id="128cd-105">Rules</span></span>  
  
-   <span data-ttu-id="128cd-106">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="128cd-106">**Declaration Context.**</span></span> <span data-ttu-id="128cd-107">Si può usare `ReadOnly` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="128cd-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="128cd-108">Ciò significa che il contesto della dichiarazione per un `ReadOnly` elemento deve essere una classe, struttura o modulo e non può essere un file di origine, lo spazio dei nomi o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="128cd-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="128cd-109">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="128cd-109">**Combined Modifiers.**</span></span> <span data-ttu-id="128cd-110">Non è possibile specificare `ReadOnly` assieme `Static` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="128cd-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="128cd-111">**Assegnazione di un valore.**</span><span class="sxs-lookup"><span data-stu-id="128cd-111">**Assigning a Value.**</span></span> <span data-ttu-id="128cd-112">Utilizzo di codice un `ReadOnly` proprietà non è possibile impostarne il valore.</span><span class="sxs-lookup"><span data-stu-id="128cd-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="128cd-113">Tuttavia, il codice che ha accesso alla risorsa di archiviazione sottostante può assegnare o modificare il valore in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="128cd-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="128cd-114">È possibile assegnare un valore per un `ReadOnly` variabile solo nella relativa dichiarazione o nel costruttore di una classe o struttura in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="128cd-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="128cd-115">Quando utilizzare una variabile di sola lettura</span><span class="sxs-lookup"><span data-stu-id="128cd-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="128cd-116">Esistono casi in cui è possibile utilizzare un [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante.</span><span class="sxs-lookup"><span data-stu-id="128cd-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="128cd-117">Ad esempio, il `Const` istruzione potrebbe non accettare il tipo di dati che si desidera assegnare o potrebbe essere in grado di calcolare il valore in fase di compilazione con un'espressione costante.</span><span class="sxs-lookup"><span data-stu-id="128cd-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="128cd-118">Potrebbe non conoscere anche il valore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="128cd-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="128cd-119">In questi casi, è possibile utilizzare un `ReadOnly` variabile per contenere un valore costante.</span><span class="sxs-lookup"><span data-stu-id="128cd-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="128cd-120">Se il tipo di dati della variabile è un tipo riferimento, ad esempio una matrice o un'istanza della classe, i relativi membri possono essere modificati anche se la variabile è `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="128cd-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="128cd-121">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="128cd-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="128cd-122">Durante l'inizializzazione, la matrice a cui puntava `characterArray()` conterrà "x", "y" e "z".</span><span class="sxs-lookup"><span data-stu-id="128cd-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="128cd-123">Poiché la variabile `characterArray` è `ReadOnly`, non è possibile modificare il valore dopo l'inizializzazione; ovvero, una nuova matrice non è possibile assegnare a esso.</span><span class="sxs-lookup"><span data-stu-id="128cd-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="128cd-124">Tuttavia, è possibile modificare i valori di uno o più membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="128cd-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="128cd-125">In seguito a una chiamata alla procedura `changeArrayElement`, la matrice a cui puntava `characterArray()` conterrà "x", "M" e "z".</span><span class="sxs-lookup"><span data-stu-id="128cd-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="128cd-126">Si noti che è simile alla dichiarazione di un parametro di routine [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), che impedisce la procedura di modificare l'argomento chiamante, ma consente di modificare i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="128cd-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="128cd-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="128cd-127">Example</span></span>  
 <span data-ttu-id="128cd-128">L'esempio seguente definisce un `ReadOnly` proprietà per la data di assunzione di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="128cd-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="128cd-129">La classe archivia il valore della proprietà internamente come una `Private` variabile e solo codice all'interno della classe è possibile modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="128cd-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="128cd-130">Tuttavia, la proprietà è `Public`, e qualsiasi codice che è possibile accedere alla classe è possibile leggere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="128cd-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 <span data-ttu-id="128cd-131">Il modificatore `ReadOnly` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="128cd-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="128cd-132">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="128cd-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="128cd-133">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="128cd-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="128cd-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="128cd-134">See Also</span></span>  
 [<span data-ttu-id="128cd-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="128cd-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [<span data-ttu-id="128cd-136">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="128cd-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
