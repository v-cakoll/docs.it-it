---
title: Refactoring in funzioni pure
ms.date: 07/20/2015
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
ms.openlocfilehash: 415b088661eca347330f4776901d68ee514d8dad
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413479"
---
# <a name="refactoring-into-pure-functions-visual-basic"></a><span data-ttu-id="006fa-102">Refactoring in funzioni pure (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="006fa-102">Refactoring Into Pure Functions (Visual Basic)</span></span>

<span data-ttu-id="006fa-103">Per le trasformazioni funzionali pure, è fondamentale comprendere come eseguire il refactoring del codice usando funzioni pure.</span><span class="sxs-lookup"><span data-stu-id="006fa-103">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>

<span data-ttu-id="006fa-104">Come accennato in precedenza, una funzione pura prevede due caratteristiche utili:</span><span class="sxs-lookup"><span data-stu-id="006fa-104">As noted previously in this section, a pure function has two useful characteristics:</span></span>

- <span data-ttu-id="006fa-105">Non ha effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="006fa-105">It has no side effects.</span></span> <span data-ttu-id="006fa-106">La funzione non cambia le variabili o i dati di qualsiasi tipo all'esterno della funzione.</span><span class="sxs-lookup"><span data-stu-id="006fa-106">The function does not change any variables or the data of any type outside of the function.</span></span>

- <span data-ttu-id="006fa-107">È coerente.</span><span class="sxs-lookup"><span data-stu-id="006fa-107">It is consistent.</span></span> <span data-ttu-id="006fa-108">Dato lo stesso set di dati di input, restituirà sempre lo stesso valore di output.</span><span class="sxs-lookup"><span data-stu-id="006fa-108">Given the same set of input data, it will always return the same output value.</span></span>

 <span data-ttu-id="006fa-109">Per passare alla programmazione funzionale, è possibile eseguire il refactoring del codice esistente per eliminare inutili effetti collaterali e dipendenze esterne.</span><span class="sxs-lookup"><span data-stu-id="006fa-109">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="006fa-110">In questo modo, è possibile creare versioni di funzioni pure del codice esistente.</span><span class="sxs-lookup"><span data-stu-id="006fa-110">In this way, you can create pure function versions of existing code.</span></span>

<span data-ttu-id="006fa-111">In questo argomento vengono descritte le caratteristiche presenti e non presenti in una funzione pura.</span><span class="sxs-lookup"><span data-stu-id="006fa-111">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="006fa-112">L'esercitazione [: manipolazione di contenuto in un documento WordprocessingML (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) Mostra come modificare un documento WordprocessingML e include due esempi di come effettuare il refactoring con una funzione pura.</span><span class="sxs-lookup"><span data-stu-id="006fa-112">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>

## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="006fa-113">Eliminazione di effetti collaterali e dipendenze esterne</span><span class="sxs-lookup"><span data-stu-id="006fa-113">Eliminating Side Effects and External Dependencies</span></span>

<span data-ttu-id="006fa-114">Negli esempi seguenti vengono confrontate due funzioni non pure e una funzione pura.</span><span class="sxs-lookup"><span data-stu-id="006fa-114">The following examples contrast two non-pure functions and a pure function.</span></span>

### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="006fa-115">Funzione non pura che modifica un membro di classe</span><span class="sxs-lookup"><span data-stu-id="006fa-115">Non-Pure Function that Changes a Class Member</span></span>

<span data-ttu-id="006fa-116">Nel codice seguente la funzione `HyphenatedConcat` non è una funzione pura perché modifica il membro dati `aMember` nella classe:</span><span class="sxs-lookup"><span data-stu-id="006fa-116">In the following code, the `HyphenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>

```vb
Module Module1
    Dim aMember As String = "StringOne"

    Public Sub HyphenatedConcat(ByVal appendStr As String)
        aMember = aMember & "-" & appendStr
    End Sub

    Sub Main()
        HyphenatedConcat("StringTwo")
        Console.WriteLine(aMember)
    End Sub
End Module
```

<span data-ttu-id="006fa-117">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="006fa-117">This code produces the following output:</span></span>

```console
StringOne-StringTwo
```

<span data-ttu-id="006fa-118">Si noti che è irrilevante se i dati da modificare hanno `public` o hanno `private` accesso oppure è un membro `shared` o un membro di istanza.</span><span class="sxs-lookup"><span data-stu-id="006fa-118">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a  `shared` member or an instance member.</span></span> <span data-ttu-id="006fa-119">Una funzione pura non modifica i dati all'eterno della funzione.</span><span class="sxs-lookup"><span data-stu-id="006fa-119">A pure function does not change any data outside of the function.</span></span>

### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="006fa-120">Funzione non pura che modifica un argomento</span><span class="sxs-lookup"><span data-stu-id="006fa-120">Non-Pure Function that Changes an Argument</span></span>

<span data-ttu-id="006fa-121">Inoltre, la versione seguente di questa stessa funzione non è pura, perché modifica il contenuto del parametro, `sb`.</span><span class="sxs-lookup"><span data-stu-id="006fa-121">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>

```vb
Module Module1
    Public Sub HyphenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)
        sb.Append("-" & appendStr)
    End Sub

    Sub Main()
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")
        HyphenatedConcat(sb1, "StringTwo")
        Console.WriteLine(sb1)
    End Sub
End Module
```

<span data-ttu-id="006fa-122">Questa versione del programma produce lo stesso output della prima versione, perché la funzione `HyphenatedConcat` ha modificato il valore (stato) del primo parametro richiamando la funzione del membro <xref:System.Text.StringBuilder.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="006fa-122">This version of the program produces the same output as the first version, because the `HyphenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="006fa-123">Si noti che questa modifica si verifica nonostante il fatto che `HyphenatedConcat` usa il passaggio di parametri in base a chiamata per valore.</span><span class="sxs-lookup"><span data-stu-id="006fa-123">Note that this alteration occurs despite that fact that `HyphenatedConcat` uses call-by-value parameter passing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="006fa-124">Per i tipi di riferimenti, se un parametro viene passato per valore, il risultato è una copia del riferimento a un oggetto passato.</span><span class="sxs-lookup"><span data-stu-id="006fa-124">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="006fa-125">Questa copia è ancora associata agli stessi dati di istanza del riferimento originale, finché la variabile di riferimento non viene assegnata a un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="006fa-125">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="006fa-126">La chiamata per riferimento non è necessariamente richiesta affinché una funzione modifichi un parametro.</span><span class="sxs-lookup"><span data-stu-id="006fa-126">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>

### <a name="pure-function"></a><span data-ttu-id="006fa-127">Funzione pura</span><span class="sxs-lookup"><span data-stu-id="006fa-127">Pure Function</span></span>

<span data-ttu-id="006fa-128">Nella versione successiva del programma viene illustrato come implementare la funzione `HyphenatedConcat` come funzione pura.</span><span class="sxs-lookup"><span data-stu-id="006fa-128">This next version of the program hows how to implement the `HyphenatedConcat` function as a pure function.</span></span>

```vb
Module Module1
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String
        Return (s & "-" & appendStr)
    End Function

    Sub Main()
        Dim s1 As String = "StringOne"
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")
        Console.WriteLine(s2)
    End Sub
End Module
```

<span data-ttu-id="006fa-129">Anche in questo caso, la versione produce la stessa riga di output: `StringOne-StringTwo`</span><span class="sxs-lookup"><span data-stu-id="006fa-129">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="006fa-130">Si noti che per mantenere il valore concatenato, viene archiviato nella variabile intermedia `s2`.</span><span class="sxs-lookup"><span data-stu-id="006fa-130">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>

<span data-ttu-id="006fa-131">Un approccio che può risultare utile consiste nello scrivere funzioni localmente non pure, ossia che dichiarano e modificano variabili locali, ma globalmente pure.</span><span class="sxs-lookup"><span data-stu-id="006fa-131">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="006fa-132">Tali funzioni presentano molte caratteristiche utili in termini di componibilità, ma evitano alcune delle complessità dei linguaggi di programmazione funzionali, ad esempio la necessità di usare la ricorsione quando con un semplice ciclo si otterrebbe lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="006fa-132">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>

## <a name="standard-query-operators"></a><span data-ttu-id="006fa-133">Operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="006fa-133">Standard Query Operators</span></span>

<span data-ttu-id="006fa-134">Una caratteristica importante degli operatori di query standard è che vengono implementati come funzioni pure.</span><span class="sxs-lookup"><span data-stu-id="006fa-134">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>

<span data-ttu-id="006fa-135">Per ulteriori informazioni, vedere [Cenni preliminari sugli operatori di query standard (Visual Basic)](standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="006fa-135">For more information, see [Standard Query Operators Overview (Visual Basic)](standard-query-operators-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="006fa-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="006fa-136">See also</span></span>

- [<span data-ttu-id="006fa-137">Introduzione alle trasformazioni funzionali pure (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="006fa-137">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](introduction-to-pure-functional-transformations.md)
- [<span data-ttu-id="006fa-138">Programmazione funzionale e programmazione imperativa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="006fa-138">Functional Programming vs. Imperative Programming (Visual Basic)</span></span>](functional-programming-vs-imperative-programming.md)
