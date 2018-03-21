---
title: Tipi di puntatori (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.assetid: 3319faf9-336d-4148-9af2-1da2579cdd1e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fe7b926bdf9f662d25f2fe960b51fc8254b7aa3a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2018
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="7d7ec-102">Tipi di puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7d7ec-102">Pointer types (C# Programming Guide)</span></span>
<span data-ttu-id="7d7ec-103">In un contesto unsafe, un tipo può essere un tipo di puntatore, un tipo di valore o un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="7d7ec-104">La dichiarazione di un tipo di puntatore può assumere uno dei seguenti formati:</span><span class="sxs-lookup"><span data-stu-id="7d7ec-104">A pointer type declaration takes one of the following forms:</span></span>  
  
```  
type* identifier;  
void* identifier; //allowed but not recommended  
```  
  
 <span data-ttu-id="7d7ec-105">I tipi seguenti possono essere tipi di puntatore:</span><span class="sxs-lookup"><span data-stu-id="7d7ec-105">Any of the following types may be a pointer type:</span></span>  
  
-   <span data-ttu-id="7d7ec-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md) o [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="7d7ec-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md), or [bool](../../../csharp/language-reference/keywords/bool.md).</span></span>  
  
-   <span data-ttu-id="7d7ec-107">Qualsiasi tipo [enum](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="7d7ec-107">Any [enum](../../../csharp/language-reference/keywords/enum.md) type.</span></span>  
  
-   <span data-ttu-id="7d7ec-108">Qualsiasi tipo di puntatore.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-108">Any pointer type.</span></span>  
  
-   <span data-ttu-id="7d7ec-109">Qualsiasi tipo struct definito dall'utente che contenga campi solo di tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-109">Any user-defined struct type that contains fields of unmanaged types only.</span></span>  
  
 <span data-ttu-id="7d7ec-110">I tipi di puntatore non ereditano da [object](../../../csharp/language-reference/keywords/object.md). Non sono inoltre previste conversioni tra i tipi di puntatore e `object`.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-110">Pointer types do not inherit from [object](../../../csharp/language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="7d7ec-111">Con i puntatori non sono inoltre supportate le operazioni di boxing e unboxing.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-111">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="7d7ec-112">È tuttavia possibile eseguire conversioni tra tipi di puntatore diversi e tra tipi di puntatore e tipi integrali.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-112">However, you can convert between different pointer types and between pointer types and integral types.</span></span>  
  
 <span data-ttu-id="7d7ec-113">Quando si dichiarano più puntatori nella stessa dichiarazione, l'asterisco (\*) viene scritto solo con il tipo sottostante. Non viene utilizzato come prefisso di ogni nome di puntatore.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-113">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="7d7ec-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7d7ec-114">For example:</span></span>  
  
```  
int* p1, p2, p3;   // Ok  
int *p1, *p2, *p3;   // Invalid in C#  
```  
  
 <span data-ttu-id="7d7ec-115">Un puntatore non può puntare a un riferimento o a uno [struct](../../../csharp/language-reference/keywords/struct.md) che contiene riferimenti, perché un riferimento a un oggetto può essere sottoposto a processi di Garbage Collection anche se un puntatore punta a esso.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-115">A pointer cannot point to a reference or to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="7d7ec-116">Il Garbage Collector non tiene traccia degli altri tipi di puntatore che puntano all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-116">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>  
  
 <span data-ttu-id="7d7ec-117">Il valore della variabile del puntatore di tipo `myType*` è l'indirizzo di una variabile di tipo `myType`.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-117">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="7d7ec-118">Di seguito sono riportati alcuni esempi di dichiarazioni di tipi di puntatore:</span><span class="sxs-lookup"><span data-stu-id="7d7ec-118">The following are examples of pointer type declarations:</span></span>  
  
|<span data-ttu-id="7d7ec-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d7ec-119">Example</span></span>|<span data-ttu-id="7d7ec-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d7ec-120">Description</span></span>|  
|-------------|-----------------|  
|`int* p`|<span data-ttu-id="7d7ec-121">`p` è un puntatore a un Integer.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-121">`p` is a pointer to an integer.</span></span>|  
|`int** p`|<span data-ttu-id="7d7ec-122">`p` è un puntatore a un puntatore a un Integer.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-122">`p` is a pointer to a pointer to an integer.</span></span>|  
|`int*[] p`|<span data-ttu-id="7d7ec-123">`p` è una matrice unidimensionale di puntatori a Integer.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-123">`p` is a single-dimensional array of pointers to integers.</span></span>|  
|`char* p`|<span data-ttu-id="7d7ec-124">`p` è un puntatore a un carattere.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-124">`p` is a pointer to a char.</span></span>|  
|`void* p`|<span data-ttu-id="7d7ec-125">`p` è un puntatore a un tipo sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-125">`p` is a pointer to an unknown type.</span></span>|  
  
 <span data-ttu-id="7d7ec-126">Per accedere al contenuto nella posizione a cui punta la variabile del puntatore, è possibile utilizzare \*, ovvero l'operatore di riferimento indiretto a puntatore.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-126">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="7d7ec-127">Si consideri ad esempio la seguente dichiarazione:</span><span class="sxs-lookup"><span data-stu-id="7d7ec-127">For example, consider the following declaration:</span></span>  
  
```  
int* myVariable;  
```  
  
 <span data-ttu-id="7d7ec-128">L'espressione `*myVariable` indica la variabile `int` individuata all'indirizzo contenuto in `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-128">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>  
  
 <span data-ttu-id="7d7ec-129">Gli argomenti [Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md) e [Conversioni di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md) includono diversi esempi di puntatori.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-129">There are several examples of pointers in the topics [fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span>  <span data-ttu-id="7d7ec-130">Nell'esempio seguente viene illustrata la necessità della parola chiave `unsafe` e dell'istruzione `fixed` e come incrementare un puntatore interno.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-130">The following example shows the need for the `unsafe` keyword and the `fixed` statement, and how to increment an interior pointer.</span></span>  <span data-ttu-id="7d7ec-131">È possibile incollare il codice nella funzione Main di un'applicazione console per eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-131">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="7d7ec-132">Ricordarsi di abilitare il codice unsafe in **Creazione progetti**. Scegliere **Progetto**, **Proprietà** nella barra dei menu e quindi selezionare **Consenti codice unsafe** nella scheda **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-132">(Remember to enable unsafe code in the **Project Designer**; choose **Project**, **Properties** on the menu bar, and then select **Allow unsafe code** in the **Build** tab.)</span></span>  
  
```  
// Normal pointer to an object.  
int[] a = new int[5] {10, 20, 30, 40, 50};  
// Must be in unsafe code to use interior pointers.  
unsafe  
{  
    // Must pin object on heap so that it doesn't move while using interior pointers.  
    fixed (int* p = &a[0])  
    {  
        // p is pinned as well as object, so create another pointer to show incrementing it.  
        int* p2 = p;  
        Console.WriteLine(*p2);  
        // Incrementing p2 bumps the pointer by four bytes due to its type ...  
        p2 += 1;  
        Console.WriteLine(*p2);  
        p2 += 1;  
        Console.WriteLine(*p2);  
        Console.WriteLine("--------");  
        Console.WriteLine(*p);  
        // Deferencing p and incrementing changes the value of a[0] ...  
        *p += 1;  
        Console.WriteLine(*p);  
        *p += 1;  
        Console.WriteLine(*p);  
    }  
}  
  
Console.WriteLine("--------");  
Console.WriteLine(a[0]);  
Console.ReadLine();  
  
// Output:  
//10  
//20  
//30  
//--------  
//10  
//11  
//12  
//--------  
//12  
```  
  
 <span data-ttu-id="7d7ec-133">Non è possibile applicare l'operatore di riferimento indiretto a un puntatore di tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-133">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="7d7ec-134">È tuttavia possibile eseguire un cast per convertire un puntatore void in qualsiasi altro tipo e viceversa.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-134">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>  
  
 <span data-ttu-id="7d7ec-135">Un puntatore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-135">A pointer can be `null`.</span></span> <span data-ttu-id="7d7ec-136">Se l'operatore di riferimento indiretto viene applicato a un puntatore Null, si otterrà un comportamento definito dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-136">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>  
  
 <span data-ttu-id="7d7ec-137">Tenere presente che il passaggio di puntatori tra metodi può generare un comportamento non definito,</span><span class="sxs-lookup"><span data-stu-id="7d7ec-137">Be aware that passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="7d7ec-138">Prendere in considerazione un metodo che restituisce un puntatore a una variabile locale tramite un parametro `in`, `out` o `ref` oppure come risultato della funzione.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-138">Consider a method that returns a pointer to a local variable through an `in`, `out` or `ref` parameter or as the function result.</span></span> <span data-ttu-id="7d7ec-139">Se il puntatore è stato impostato in un blocco fisso, la variabile a cui punta potrebbe non essere più fissa.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-139">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>  
  
 <span data-ttu-id="7d7ec-140">Nella tabella riportata di seguito sono elencati gli operatori e le istruzioni che è possibile utilizzare con i puntatori in un contesto unsafe:</span><span class="sxs-lookup"><span data-stu-id="7d7ec-140">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>  
  
|<span data-ttu-id="7d7ec-141">Operatore/istruzione</span><span class="sxs-lookup"><span data-stu-id="7d7ec-141">Operator/Statement</span></span>|<span data-ttu-id="7d7ec-142">Usa</span><span class="sxs-lookup"><span data-stu-id="7d7ec-142">Use</span></span>|  
|-------------------------|---------|  
|*|<span data-ttu-id="7d7ec-143">Esegue il riferimento indiretto al puntatore.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-143">Performs pointer indirection.</span></span>|  
|->|<span data-ttu-id="7d7ec-144">Accede a un membro di struct tramite un puntatore.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-144">Accesses a member of a struct through a pointer.</span></span>|  
|<span data-ttu-id="7d7ec-145">[]</span><span class="sxs-lookup"><span data-stu-id="7d7ec-145">[]</span></span>|<span data-ttu-id="7d7ec-146">Indicizza un puntatore.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-146">Indexes a pointer.</span></span>|  
|`&`|<span data-ttu-id="7d7ec-147">Ottiene l'indirizzo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-147">Obtains the address of a variable.</span></span>|  
|<span data-ttu-id="7d7ec-148">++ e --</span><span class="sxs-lookup"><span data-stu-id="7d7ec-148">++ and --</span></span>|<span data-ttu-id="7d7ec-149">Incrementa e decrementa puntatori.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-149">Increments and decrements pointers.</span></span>|  
|<span data-ttu-id="7d7ec-150">+ e -</span><span class="sxs-lookup"><span data-stu-id="7d7ec-150">+ and -</span></span>|<span data-ttu-id="7d7ec-151">Utilizza l'aritmetica dei puntatori.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-151">Performs pointer arithmetic.</span></span>|  
|<span data-ttu-id="7d7ec-152">==, !=, \<, >, \<= e >=</span><span class="sxs-lookup"><span data-stu-id="7d7ec-152">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="7d7ec-153">Confronta puntatori.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-153">Compares pointers.</span></span>|  
|`stackalloc`|<span data-ttu-id="7d7ec-154">Alloca memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-154">Allocates memory on the stack.</span></span>|  
|<span data-ttu-id="7d7ec-155">Istruzione `fixed`</span><span class="sxs-lookup"><span data-stu-id="7d7ec-155">`fixed` statement</span></span>|<span data-ttu-id="7d7ec-156">Corregge temporaneamente una variabile per consentire di trovarne l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="7d7ec-156">Temporarily fixes a variable so that its address may be found.</span></span>|  
  
## <a name="c-language-specification"></a><span data-ttu-id="7d7ec-157">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7d7ec-157">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7d7ec-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d7ec-158">See Also</span></span>  
 [<span data-ttu-id="7d7ec-159">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7d7ec-159">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7d7ec-160">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="7d7ec-160">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="7d7ec-161">Conversioni puntatore</span><span class="sxs-lookup"><span data-stu-id="7d7ec-161">Pointer Conversions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md)  
 [<span data-ttu-id="7d7ec-162">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="7d7ec-162">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="7d7ec-163">Tipi</span><span class="sxs-lookup"><span data-stu-id="7d7ec-163">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="7d7ec-164">unsafe</span><span class="sxs-lookup"><span data-stu-id="7d7ec-164">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="7d7ec-165">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="7d7ec-165">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="7d7ec-166">stackalloc</span><span class="sxs-lookup"><span data-stu-id="7d7ec-166">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)  
 [<span data-ttu-id="7d7ec-167">Boxing e unboxing</span><span class="sxs-lookup"><span data-stu-id="7d7ec-167">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
