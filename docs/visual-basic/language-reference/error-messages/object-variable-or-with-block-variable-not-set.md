---
title: Variabile oggetto o variabile del blocco With non impostata
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: b2bd1be83f57dbdc7a64b407dc1052074e19c74b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597664"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="a4d87-102">Variabile oggetto o variabile del blocco With non impostata</span><span class="sxs-lookup"><span data-stu-id="a4d87-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="a4d87-103">Riferimento a una variabile oggetto non valido.</span><span class="sxs-lookup"><span data-stu-id="a4d87-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="a4d87-104">L'errore può essere determinato da numerose cause:</span><span class="sxs-lookup"><span data-stu-id="a4d87-104">This error can occur for several reasons:</span></span>  
  
-   <span data-ttu-id="a4d87-105">Una variabile è stata dichiarata senza specificare un tipo.</span><span class="sxs-lookup"><span data-stu-id="a4d87-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="a4d87-106">Se una variabile viene dichiarata senza specificare un tipo, il valore predefinito per digitare `Object`.</span><span class="sxs-lookup"><span data-stu-id="a4d87-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>  
  
     <span data-ttu-id="a4d87-107">Ad esempio, una variabile dichiarata con `Dim x` saranno di tipo `Object;` una variabile dichiarata con `Dim x As String` saranno di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="a4d87-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="a4d87-108">Il `Option Strict` istruzione la tipizzazione implicita che comporta un `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="a4d87-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="a4d87-109">Se si omette il tipo, si verificherà un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a4d87-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="a4d87-110">Vedere [Option Strict (istruzione)](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a4d87-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
-   <span data-ttu-id="a4d87-111">Si sta tentando di fare riferimento a un oggetto che è stato impostato su `Nothing`</span><span class="sxs-lookup"><span data-stu-id="a4d87-111">You are attempting to reference an object that has been set to `Nothing`</span></span>  
  
     <span data-ttu-id="a4d87-112">.</span><span class="sxs-lookup"><span data-stu-id="a4d87-112">.</span></span>  
  
-   <span data-ttu-id="a4d87-113">Si sta tentando di accedere a un elemento di una variabile di matrice non è stato dichiarato in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="a4d87-113">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>  
  
     <span data-ttu-id="a4d87-114">Ad esempio, una matrice dichiarata come `products() As String` genererà l'errore se si tenta di fare riferimento a un elemento della matrice `products(3) = "Widget"`.</span><span class="sxs-lookup"><span data-stu-id="a4d87-114">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="a4d87-115">La matrice non dispone di elementi e viene considerata come un oggetto.</span><span class="sxs-lookup"><span data-stu-id="a4d87-115">The array has no elements and is treated as an object.</span></span>  
  
-   <span data-ttu-id="a4d87-116">Si sta tentando di accedere a codice all'interno di un `With...End With` blocco prima che il blocco è stato inizializzato.</span><span class="sxs-lookup"><span data-stu-id="a4d87-116">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="a4d87-117">Oggetto `With...End With` blocco deve essere inizializzato mediante l'esecuzione di `With` il punto di ingresso di istruzione.</span><span class="sxs-lookup"><span data-stu-id="a4d87-117">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4d87-118">Nelle versioni precedenti di Visual Basic o VBA questo errore è stato attivato anche assegnando un valore a una variabile senza utilizzare il `Set` (parola chiave) (`x = "name"` anziché `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="a4d87-118">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="a4d87-119">Il `Set` (parola chiave) non è più valida in Visual Basic .net.</span><span class="sxs-lookup"><span data-stu-id="a4d87-119">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a4d87-120">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a4d87-120">To correct this error</span></span>  
  
1.  <span data-ttu-id="a4d87-121">Impostare `Option Strict` a `On` aggiungendo il codice seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="a4d87-121">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  <span data-ttu-id="a4d87-122">Se non si desidera abilitare `Option Strict`, cercare nel codice per eventuali variabili che sono state specificate senza un tipo (`Dim x` anziché `Dim x As String`) e aggiungere il tipo previsto per la dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="a4d87-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>  
  
3.  <span data-ttu-id="a4d87-123">Assicurarsi che invece non fa riferimento a una variabile oggetto che è stata impostata su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="a4d87-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="a4d87-124">Cercare nel codice per la parola chiave `Nothing`e modificare il codice in modo che l'oggetto non è impostato su `Nothing` fino a quando non dopo che è stato fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="a4d87-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>  
  
4.  <span data-ttu-id="a4d87-125">Assicurarsi che tutte le variabili di matrice vengono dimensionate prima di accedervi.</span><span class="sxs-lookup"><span data-stu-id="a4d87-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="a4d87-126">È possibile assegnare una dimensione al momento della creazione della matrice (`Dim x(5) As String` anziché `Dim x() As String`), oppure utilizzare il `ReDim` (parola chiave) per impostare le dimensioni della matrice prima che si accede.</span><span class="sxs-lookup"><span data-stu-id="a4d87-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>  
  
5.  <span data-ttu-id="a4d87-127">Verificare che il `With` blocco viene inizializzato tramite l'esecuzione di `With` il punto di ingresso di istruzione.</span><span class="sxs-lookup"><span data-stu-id="a4d87-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d87-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4d87-128">See Also</span></span>  
 [<span data-ttu-id="a4d87-129">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="a4d87-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="a4d87-130">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="a4d87-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="a4d87-131">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="a4d87-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
