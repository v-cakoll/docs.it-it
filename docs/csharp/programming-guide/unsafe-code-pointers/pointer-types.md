---
title: Tipi di puntatori (Guida per programmatori C#)
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: cbc75a2ec6fe826cb192b1e8bef61c7295f13916
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337168"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="3a807-102">Tipi di puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3a807-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="3a807-103">In un contesto unsafe, un tipo può essere un tipo di puntatore, un tipo di valore o un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3a807-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="3a807-104">La dichiarazione di un tipo di puntatore può assumere uno dei seguenti formati:</span><span class="sxs-lookup"><span data-stu-id="3a807-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="3a807-105">Il tipo specificato prima di `*` in un tipo di puntatore viene chiamato **tipo referrent**.</span><span class="sxs-lookup"><span data-stu-id="3a807-105">The type specified before the `*` in a pointer type is called the **referrent type**.</span></span> <span data-ttu-id="3a807-106">I tipi seguenti possono essere tipi di puntatore referrent:</span><span class="sxs-lookup"><span data-stu-id="3a807-106">Any of the following types may be a referrent type:</span></span>

- <span data-ttu-id="3a807-107">Qualsiasi tipo integrale: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="3a807-107">Any integral type: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span></span>
- <span data-ttu-id="3a807-108">Qualsiasi tipo a virgola mobile: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="3a807-108">Any floating point type: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span></span>
- <span data-ttu-id="3a807-109">[char](../../language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="3a807-109">[char](../../language-reference/keywords/char.md).</span></span>
- <span data-ttu-id="3a807-110">[bool](../../language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="3a807-110">[bool](../../language-reference/keywords/bool.md).</span></span>
- <span data-ttu-id="3a807-111">[decimal](../../language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="3a807-111">[decimal](../../language-reference/keywords/decimal.md).</span></span>
- <span data-ttu-id="3a807-112">Qualsiasi tipo [enum](../../language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="3a807-112">Any [enum](../../language-reference/keywords/enum.md) type.</span></span>
- <span data-ttu-id="3a807-113">Qualsiasi tipo di puntatore.</span><span class="sxs-lookup"><span data-stu-id="3a807-113">Any pointer type.</span></span> <span data-ttu-id="3a807-114">Ciò consente l'utilizzo di espressioni come `void**`.</span><span class="sxs-lookup"><span data-stu-id="3a807-114">This allows expressions such as `void**`.</span></span>
- <span data-ttu-id="3a807-115">Qualsiasi tipo struct definito dall'utente che contenga campi solo di tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="3a807-115">Any user-defined struct type that contains fields of unmanaged types only.</span></span>

<span data-ttu-id="3a807-116">I tipi di puntatore non ereditano da [object](../../language-reference/keywords/object.md). Non sono inoltre previste conversioni tra i tipi di puntatore e `object`.</span><span class="sxs-lookup"><span data-stu-id="3a807-116">Pointer types do not inherit from [object](../../language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="3a807-117">Con i puntatori non sono inoltre supportate le operazioni di boxing e unboxing.</span><span class="sxs-lookup"><span data-stu-id="3a807-117">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="3a807-118">È tuttavia possibile eseguire conversioni tra tipi di puntatore diversi e tra tipi di puntatore e tipi integrali.</span><span class="sxs-lookup"><span data-stu-id="3a807-118">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="3a807-119">Quando si dichiarano più puntatori nella stessa dichiarazione, l'asterisco (\*) viene scritto solo con il tipo sottostante. Non viene utilizzato come prefisso di ogni nome di puntatore.</span><span class="sxs-lookup"><span data-stu-id="3a807-119">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="3a807-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3a807-120">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="3a807-121">Un puntatore non può puntare a un riferimento o a uno [struct](../../language-reference/keywords/struct.md) che contiene riferimenti, perché un riferimento a un oggetto può essere sottoposto a processi di Garbage Collection anche se un puntatore punta a esso.</span><span class="sxs-lookup"><span data-stu-id="3a807-121">A pointer cannot point to a reference or to a [struct](../../language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="3a807-122">Il Garbage Collector non tiene traccia degli altri tipi di puntatore che puntano all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3a807-122">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="3a807-123">Il valore della variabile del puntatore di tipo `myType*` è l'indirizzo di una variabile di tipo `myType`.</span><span class="sxs-lookup"><span data-stu-id="3a807-123">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="3a807-124">Di seguito sono riportati alcuni esempi di dichiarazioni di tipi di puntatore:</span><span class="sxs-lookup"><span data-stu-id="3a807-124">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="3a807-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a807-125">Example</span></span>|<span data-ttu-id="3a807-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a807-126">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="3a807-127">`p` è un puntatore a un Integer.</span><span class="sxs-lookup"><span data-stu-id="3a807-127">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="3a807-128">`p` è un puntatore a un puntatore a un Integer.</span><span class="sxs-lookup"><span data-stu-id="3a807-128">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="3a807-129">`p` è una matrice unidimensionale di puntatori a Integer.</span><span class="sxs-lookup"><span data-stu-id="3a807-129">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="3a807-130">`p` è un puntatore a un carattere.</span><span class="sxs-lookup"><span data-stu-id="3a807-130">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="3a807-131">`p` è un puntatore a un tipo sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3a807-131">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="3a807-132">Per accedere al contenuto nella posizione a cui punta la variabile del puntatore, è possibile utilizzare \*, ovvero l'operatore di riferimento indiretto a puntatore.</span><span class="sxs-lookup"><span data-stu-id="3a807-132">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="3a807-133">Si consideri ad esempio la seguente dichiarazione:</span><span class="sxs-lookup"><span data-stu-id="3a807-133">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="3a807-134">L'espressione `*myVariable` indica la variabile `int` individuata all'indirizzo contenuto in `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="3a807-134">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="3a807-135">Gli argomenti [Istruzione fixed](../../language-reference/keywords/fixed-statement.md) e [Conversioni di puntatori](../../programming-guide/unsafe-code-pointers/pointer-conversions.md) includono diversi esempi di puntatori.</span><span class="sxs-lookup"><span data-stu-id="3a807-135">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span> <span data-ttu-id="3a807-136">L'esempio seguente usa la parola chiave `unsafe` e l'istruzione `fixed` e mostra come incrementare un puntatore interno.</span><span class="sxs-lookup"><span data-stu-id="3a807-136">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="3a807-137">È possibile incollare il codice nella funzione Main di un'applicazione console per eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="3a807-137">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="3a807-138">Questi esempi devono essere compilati con il set di opzioni del compilatore [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="3a807-138">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="3a807-139">Non è possibile applicare l'operatore di riferimento indiretto a un puntatore di tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="3a807-139">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="3a807-140">È tuttavia possibile eseguire un cast per convertire un puntatore void in qualsiasi altro tipo e viceversa.</span><span class="sxs-lookup"><span data-stu-id="3a807-140">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="3a807-141">Un puntatore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="3a807-141">A pointer can be `null`.</span></span> <span data-ttu-id="3a807-142">Se l'operatore di riferimento indiretto viene applicato a un puntatore Null, si otterrà un comportamento definito dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="3a807-142">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="3a807-143">Tenere presente che il passaggio di puntatori tra metodi può generare un comportamento non definito.</span><span class="sxs-lookup"><span data-stu-id="3a807-143">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="3a807-144">Prendere in considerazione un metodo che restituisce un puntatore a una variabile locale tramite un parametro `in`, `out` o `ref` oppure come risultato della funzione.</span><span class="sxs-lookup"><span data-stu-id="3a807-144">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="3a807-145">Se il puntatore è stato impostato in un blocco fisso, la variabile a cui punta potrebbe non essere più fissa.</span><span class="sxs-lookup"><span data-stu-id="3a807-145">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="3a807-146">Nella tabella riportata di seguito sono elencati gli operatori e le istruzioni che è possibile utilizzare con i puntatori in un contesto unsafe:</span><span class="sxs-lookup"><span data-stu-id="3a807-146">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="3a807-147">Operatore/istruzione</span><span class="sxs-lookup"><span data-stu-id="3a807-147">Operator/Statement</span></span>|<span data-ttu-id="3a807-148">Usa</span><span class="sxs-lookup"><span data-stu-id="3a807-148">Use</span></span>|
|-------------------------|---------|
|*|<span data-ttu-id="3a807-149">Esegue il riferimento indiretto al puntatore.</span><span class="sxs-lookup"><span data-stu-id="3a807-149">Performs pointer indirection.</span></span>|
|->|<span data-ttu-id="3a807-150">Accede a un membro di struct tramite un puntatore.</span><span class="sxs-lookup"><span data-stu-id="3a807-150">Accesses a member of a struct through a pointer.</span></span>|
|<span data-ttu-id="3a807-151">[]</span><span class="sxs-lookup"><span data-stu-id="3a807-151">[]</span></span>|<span data-ttu-id="3a807-152">Indicizza un puntatore.</span><span class="sxs-lookup"><span data-stu-id="3a807-152">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="3a807-153">Ottiene l'indirizzo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="3a807-153">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="3a807-154">++ e --</span><span class="sxs-lookup"><span data-stu-id="3a807-154">++ and --</span></span>|<span data-ttu-id="3a807-155">Incrementa e decrementa puntatori.</span><span class="sxs-lookup"><span data-stu-id="3a807-155">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="3a807-156">+ e -</span><span class="sxs-lookup"><span data-stu-id="3a807-156">+ and -</span></span>|<span data-ttu-id="3a807-157">Utilizza l'aritmetica dei puntatori.</span><span class="sxs-lookup"><span data-stu-id="3a807-157">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="3a807-158">==, !=, \<, >, \<= e >=</span><span class="sxs-lookup"><span data-stu-id="3a807-158">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="3a807-159">Confronta puntatori.</span><span class="sxs-lookup"><span data-stu-id="3a807-159">Compares pointers.</span></span>|
|`stackalloc`|<span data-ttu-id="3a807-160">Alloca memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="3a807-160">Allocates memory on the stack.</span></span>|
|<span data-ttu-id="3a807-161">Istruzione `fixed`</span><span class="sxs-lookup"><span data-stu-id="3a807-161">`fixed` statement</span></span>|<span data-ttu-id="3a807-162">Corregge temporaneamente una variabile per consentire di trovarne l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="3a807-162">Temporarily fixes a variable so that its address may be found.</span></span>|

## <a name="c-language-specification"></a><span data-ttu-id="3a807-163">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3a807-163">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3a807-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a807-164">See Also</span></span>
 [<span data-ttu-id="3a807-165">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3a807-165">C# Programming Guide</span></span>](../index.md)  
 [<span data-ttu-id="3a807-166">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="3a807-166">Unsafe Code and Pointers</span></span>](index.md)  
 [<span data-ttu-id="3a807-167">Conversioni puntatore</span><span class="sxs-lookup"><span data-stu-id="3a807-167">Pointer Conversions</span></span>](pointer-conversions.md)  
 [<span data-ttu-id="3a807-168">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="3a807-168">Pointer Expressions</span></span>](pointer-expressions.md)  
 [<span data-ttu-id="3a807-169">Tipi</span><span class="sxs-lookup"><span data-stu-id="3a807-169">Types</span></span>](../../language-reference/keywords/types.md)  
 [<span data-ttu-id="3a807-170">unsafe</span><span class="sxs-lookup"><span data-stu-id="3a807-170">unsafe</span></span>](../../language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="3a807-171">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="3a807-171">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="3a807-172">stackalloc</span><span class="sxs-lookup"><span data-stu-id="3a807-172">stackalloc</span></span>](../../language-reference/keywords/stackalloc.md)  
 [<span data-ttu-id="3a807-173">Boxing e unboxing</span><span class="sxs-lookup"><span data-stu-id="3a807-173">Boxing and Unboxing</span></span>](../types/boxing-and-unboxing.md)
