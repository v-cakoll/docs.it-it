---
title: Variabile oggetto o variabile del blocco With non impostata
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 766b95163f164ec76135b964115069b6855ceebf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64750672"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="3b0b2-102">Variabile oggetto o variabile del blocco With non impostata</span><span class="sxs-lookup"><span data-stu-id="3b0b2-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="3b0b2-103">Riferimento a una variabile oggetto non valido.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="3b0b2-104">L'errore può essere determinato da numerose cause:</span><span class="sxs-lookup"><span data-stu-id="3b0b2-104">This error can occur for several reasons:</span></span>

- <span data-ttu-id="3b0b2-105">Una variabile è stata dichiarata senza specificare un tipo.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="3b0b2-106">Se una variabile viene dichiarata senza specificare un tipo, per impostazione predefinita per digitare `Object`.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="3b0b2-107">Ad esempio, una variabile dichiarata con `Dim x` saranno di tipo `Object;` una variabile dichiarata con `Dim x As String` saranno di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    >  <span data-ttu-id="3b0b2-108">Il `Option Strict` istruzione la tipizzazione implicita che comporta un `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="3b0b2-109">Se si omette il tipo, si verificherà un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="3b0b2-110">Visualizzare [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3b0b2-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="3b0b2-111">Si sta provando a fare riferimento a un oggetto che è stato impostato su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-111">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="3b0b2-112">Si sta tentando di accedere a un elemento di una variabile di matrice che non è stata dichiarata in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-112">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="3b0b2-113">Ad esempio, una matrice dichiarata come `products() As String` attiveranno l'errore se si tenta di fare riferimento a un elemento della matrice `products(3) = "Widget"`.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-113">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="3b0b2-114">La matrice dispone di alcun elemento e viene considerata come un oggetto.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-114">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="3b0b2-115">Sta tentando di accedere a codice all'interno di un `With...End With` blocco prima che il blocco è stato inizializzato.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-115">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="3b0b2-116">Oggetto `With...End With` blocco deve essere inizializzato mediante l'esecuzione di `With` punto di ingresso di istruzione.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-116">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="3b0b2-117">Nelle versioni precedenti di Visual Basic o VBA questo errore è stato attivato anche assegnando un valore a una variabile senza usare la `Set` parola chiave (`x = "name"` invece di `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="3b0b2-117">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="3b0b2-118">Il `Set` parola chiave non è più valido in Visual Basic .net.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-118">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="3b0b2-119">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3b0b2-119">To correct this error</span></span>

1. <span data-ttu-id="3b0b2-120">Impostare `Option Strict` a `On` aggiungendo il codice seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="3b0b2-120">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="3b0b2-121">Quando si esegue il progetto, verrà visualizzato un errore del compilatore nel **elenco errori** per qualsiasi variabile che è stata specificata senza un tipo.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-121">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="3b0b2-122">Se non si vuole abilitare `Option Strict`, il codice per tutte le variabili che sono stati specificati senza un tipo di ricerca (`Dim x` invece di `Dim x As String`) e aggiungere il tipo desiderato alla dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="3b0b2-123">Assicurarsi che invece non si fa riferimento a una variabile oggetto che è stata impostata su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="3b0b2-124">Eseguire ricerche nel codice per la parola chiave `Nothing`e modificare il codice in modo che l'oggetto non è impostato su `Nothing` fino a quando non dopo che si è fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="3b0b2-125">Assicurarsi che tutte le variabili di matrice vengono dimensionate prima di accedervi.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="3b0b2-126">È possibile assegnare una dimensione al momento della creazione della matrice (`Dim x(5) As String` invece di `Dim x() As String`), oppure usare il `ReDim` parola chiave per impostare le dimensioni della matrice prima che si accede.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="3b0b2-127">Assicurarsi che il `With` blocco viene inizializzato tramite l'esecuzione di `With` punto di ingresso di istruzione.</span><span class="sxs-lookup"><span data-stu-id="3b0b2-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b0b2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b0b2-128">See also</span></span>

- [<span data-ttu-id="3b0b2-129">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="3b0b2-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="3b0b2-130">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="3b0b2-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="3b0b2-131">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="3b0b2-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
