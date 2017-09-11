---
title: Refactoring in funzioni pure (C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 2bce781df80a777203ed8e713bedf83f1c7779a8
ms.contentlocale: it-it
ms.lasthandoff: 08/25/2017

---
# <a name="refactoring-into-pure-functions-c"></a><span data-ttu-id="e28df-102">Refactoring in funzioni pure (C#)</span><span class="sxs-lookup"><span data-stu-id="e28df-102">Refactoring Into Pure Functions (C#)</span></span>

<span data-ttu-id="e28df-103">Per le trasformazioni funzionali pure, è fondamentale comprendere come eseguire il refactoring del codice usando funzioni pure.</span><span class="sxs-lookup"><span data-stu-id="e28df-103">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e28df-104">La nomenclatura comune nella programmazione funzionale prevede il refactoring dei programmi tramite funzioni pure.</span><span class="sxs-lookup"><span data-stu-id="e28df-104">The common nomenclature in functional programming is that you refactor programs using pure functions.</span></span> <span data-ttu-id="e28df-105">In Visual Basic e C++, ciò è in linea con l'uso di funzioni nei rispettivi linguaggi.</span><span class="sxs-lookup"><span data-stu-id="e28df-105">In Visual Basic and C++, this aligns with the use of functions in the respective languages.</span></span> <span data-ttu-id="e28df-106">Tuttavia, in C# le funzioni sono denominate metodi.</span><span class="sxs-lookup"><span data-stu-id="e28df-106">However, in C#, functions are called methods.</span></span> <span data-ttu-id="e28df-107">Ai fini del presente documento, una funzione pura viene implementata come metodo in C#.</span><span class="sxs-lookup"><span data-stu-id="e28df-107">For the purposes of this discussion, a pure function is implemented as a method in C#.</span></span>  
  
 <span data-ttu-id="e28df-108">Come accennato in precedenza, una funzione pura prevede due caratteristiche utili:</span><span class="sxs-lookup"><span data-stu-id="e28df-108">As noted previously in this section, a pure function has two useful characteristics:</span></span>  
  
-   <span data-ttu-id="e28df-109">Non ha effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="e28df-109">It has no side effects.</span></span> <span data-ttu-id="e28df-110">La funzione non cambia le variabili o i dati di qualsiasi tipo all'esterno della funzione.</span><span class="sxs-lookup"><span data-stu-id="e28df-110">The function does not change any variables or the data of any type outside of the function.</span></span>  
  
-   <span data-ttu-id="e28df-111">È coerente.</span><span class="sxs-lookup"><span data-stu-id="e28df-111">It is consistent.</span></span> <span data-ttu-id="e28df-112">Dato lo stesso set di dati di input, restituirà sempre lo stesso valore di output.</span><span class="sxs-lookup"><span data-stu-id="e28df-112">Given the same set of input data, it will always return the same output value.</span></span>  
  
 <span data-ttu-id="e28df-113">Per passare alla programmazione funzionale, è possibile eseguire il refactoring del codice esistente per eliminare inutili effetti collaterali e dipendenze esterne.</span><span class="sxs-lookup"><span data-stu-id="e28df-113">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="e28df-114">In questo modo, è possibile creare versioni di funzioni pure del codice esistente.</span><span class="sxs-lookup"><span data-stu-id="e28df-114">In this way, you can create pure function versions of existing code.</span></span>  
  
 <span data-ttu-id="e28df-115">In questo argomento vengono descritte le caratteristiche presenti e non presenti in una funzione pura.</span><span class="sxs-lookup"><span data-stu-id="e28df-115">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="e28df-116">L'[esercitazione sulla modifica del contenuto in un documento WordprocessingML (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) illustra come modificare un documento WordprocessingML e contiene due esempi su come eseguire il refactoring usando una funzione pura.</span><span class="sxs-lookup"><span data-stu-id="e28df-116">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="e28df-117">Eliminazione di effetti collaterali e dipendenze esterne</span><span class="sxs-lookup"><span data-stu-id="e28df-117">Eliminating Side Effects and External Dependencies</span></span>  
 <span data-ttu-id="e28df-118">Negli esempi seguenti vengono confrontate due funzioni non pure e una funzione pura.</span><span class="sxs-lookup"><span data-stu-id="e28df-118">The following examples contrast two non-pure functions and a pure function.</span></span>  
  
### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="e28df-119">Funzione non pura che modifica un membro di classe</span><span class="sxs-lookup"><span data-stu-id="e28df-119">Non-Pure Function that Changes a Class Member</span></span>  
 <span data-ttu-id="e28df-120">Nel codice seguente la funzione `HypenatedConcat` non è una funzione pura perché modifica il membro dati `aMember` nella classe:</span><span class="sxs-lookup"><span data-stu-id="e28df-120">In the following code, the `HypenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>  
  
```csharp  
public class Program  
{  
    private static string aMember = "StringOne";  
  
    public static void HypenatedConcat(string appendStr)  
    {  
        aMember += '-' + appendStr;  
    }  
  
    public static void Main()  
    {  
        HypenatedConcat("StringTwo");  
        Console.WriteLine(aMember);  
    }  
}  
```  
  
 <span data-ttu-id="e28df-121">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e28df-121">This code produces the following output:</span></span>  
  
```  
StringOne-StringTwo  
```  
  
 <span data-ttu-id="e28df-122">Si noti che è irrilevante se per i dati l'accesso è `public` o `private` oppure se i dati sono un membro `static` o un membro di istanza.</span><span class="sxs-lookup"><span data-stu-id="e28df-122">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a `static` member or an instance member.</span></span> <span data-ttu-id="e28df-123">Una funzione pura non modifica i dati all'eterno della funzione.</span><span class="sxs-lookup"><span data-stu-id="e28df-123">A pure function does not change any data outside of the function.</span></span>  
  
### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="e28df-124">Funzione non pura che modifica un argomento</span><span class="sxs-lookup"><span data-stu-id="e28df-124">Non-Pure Function that Changes an Argument</span></span>  
 <span data-ttu-id="e28df-125">Inoltre, la versione seguente di questa stessa funzione non è pura, perché modifica il contenuto del parametro, `sb`.</span><span class="sxs-lookup"><span data-stu-id="e28df-125">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>  
  
```csharp  
public class Program  
{  
    public static void HypenatedConcat(StringBuilder sb, String appendStr)  
    {  
        sb.Append('-' + appendStr);  
    }  
  
    public static void Main()  
    {  
        StringBuilder sb1 = new StringBuilder("StringOne");  
        HypenatedConcat(sb1, "StringTwo");  
        Console.WriteLine(sb1);  
    }  
}  
```  
  
 <span data-ttu-id="e28df-126">Questa versione del programma produce lo stesso output della prima versione, perché la funzione `HypenatedConcat` ha modificato il valore (stato) del primo parametro richiamando la funzione del membro <xref:System.Text.StringBuilder.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="e28df-126">This version of the program produces the same output as the first version, because the `HypenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="e28df-127">Si noti che questa modifica si verifica nonostante il fatto che `HypenatedConcat` usa il passaggio di parametri in base a chiamata per valore.</span><span class="sxs-lookup"><span data-stu-id="e28df-127">Note that this alteration occurs despite that fact that `HypenatedConcat` uses call-by-value parameter passing.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e28df-128">Per i tipi di riferimenti, se un parametro viene passato per valore, il risultato è una copia del riferimento a un oggetto passato.</span><span class="sxs-lookup"><span data-stu-id="e28df-128">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="e28df-129">Questa copia è ancora associata agli stessi dati di istanza del riferimento originale, finché la variabile di riferimento non viene assegnata a un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="e28df-129">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="e28df-130">La chiamata per riferimento non è necessariamente richiesta affinché una funzione modifichi un parametro.</span><span class="sxs-lookup"><span data-stu-id="e28df-130">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>  
  
### <a name="pure-function"></a><span data-ttu-id="e28df-131">Funzione pura</span><span class="sxs-lookup"><span data-stu-id="e28df-131">Pure Function</span></span>  
<span data-ttu-id="e28df-132">Nella versione successiva del programma viene illustrato come implementare la funzione `HypenatedConcat` come funzione pura.</span><span class="sxs-lookup"><span data-stu-id="e28df-132">This next version of the program shows how to implement the `HypenatedConcat` function as a pure function.</span></span>  
  
```csharp  
class Program  
{  
    public static string HyphenatedConcat(string s, string appendStr)  
    {  
        return (s + '-' + appendStr);  
    }  
  
    public static void Main(string[] args)  
    {  
        string s1 = "StringOne";  
        string s2 = HyphenatedConcat(s1, "StringTwo");  
        Console.WriteLine(s2);  
    }  
}  
```  
  
 <span data-ttu-id="e28df-133">Anche in questo caso, la versione produce la stessa riga di output: `StringOne-StringTwo`</span><span class="sxs-lookup"><span data-stu-id="e28df-133">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="e28df-134">Si noti che per mantenere il valore concatenato, viene archiviato nella variabile intermedia `s2`.</span><span class="sxs-lookup"><span data-stu-id="e28df-134">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>  
  
 <span data-ttu-id="e28df-135">Un approccio che può risultare utile consiste nello scrivere funzioni localmente non pure, ossia che dichiarano e modificano variabili locali, ma globalmente pure.</span><span class="sxs-lookup"><span data-stu-id="e28df-135">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="e28df-136">Tali funzioni presentano molte caratteristiche utili in termini di componibilità, ma evitano alcune delle complessità dei linguaggi di programmazione funzionali, ad esempio la necessità di usare la ricorsione quando con un semplice ciclo si otterrebbe lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="e28df-136">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>  
  
## <a name="standard-query-operators"></a><span data-ttu-id="e28df-137">Operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="e28df-137">Standard Query Operators</span></span>  
 <span data-ttu-id="e28df-138">Una caratteristica importante degli operatori di query standard è che vengono implementati come funzioni pure.</span><span class="sxs-lookup"><span data-stu-id="e28df-138">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>  
  
 <span data-ttu-id="e28df-139">Per altre informazioni, vedere [Panoramica degli operatori di query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e28df-139">For more information, see [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28df-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e28df-140">See Also</span></span>  
 <span data-ttu-id="e28df-141">[Introduzione alle trasformazioni funzionali pure (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="e28df-141">[Introduction to Pure Functional Transformations (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span></span>  
 <span data-ttu-id="e28df-142">[Differenze tra programmazione funzionale e programmazione imperativa (C#)](../../../../csharp/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md).</span><span class="sxs-lookup"><span data-stu-id="e28df-142">[Functional Programming vs. Imperative Programming (C#)](../../../../csharp/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)</span></span>

