---
title: Direttiva using - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: a2028ccce47de54b59323194a0ffab3a643d878c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712975"
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="b6edc-102">Direttiva using (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b6edc-102">using directive (C# Reference)</span></span>

<span data-ttu-id="b6edc-103">La direttiva `using` ha tre usi:</span><span class="sxs-lookup"><span data-stu-id="b6edc-103">The `using` directive has three uses:</span></span>

- <span data-ttu-id="b6edc-104">Consentire l'uso di tipi in uno spazio dei nomi in modo da non dover qualificare l'uso di un tipo in tale spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="b6edc-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>

    ```csharp
    using System.Text;
    ```

- <span data-ttu-id="b6edc-105">Consentire l'accesso ai membri statici e ai tipi nidificati di un tipo senza dover qualificare l'accesso con il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="b6edc-105">To allow you to access static members and nested types of a type without having to qualify the access with the type name.</span></span>

    ```csharp
    using static System.Math;
    ```

    <span data-ttu-id="b6edc-106">Per altre informazioni, vedere la [direttiva using static](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="b6edc-106">For more information, see the [using static directive](using-static.md).</span></span>

- <span data-ttu-id="b6edc-107">Creare un alias per uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="b6edc-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="b6edc-108">Si tratta di una *direttiva alias using*.</span><span class="sxs-lookup"><span data-stu-id="b6edc-108">This is called a *using alias directive*.</span></span>

    ```csharp
    using Project = PC.MyCompany.Project;
    ```

<span data-ttu-id="b6edc-109">La parola chiave `using` viene usata anche per creare *istruzioni using*, che garantiscono che gli oggetti <xref:System.IDisposable>, ad esempio file e tipi di carattere, vengano gestiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="b6edc-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="b6edc-110">Per altre informazioni, vedere [Istruzione using](using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b6edc-110">See [using Statement](using-statement.md) for more information.</span></span>

## <a name="using-static-type"></a><span data-ttu-id="b6edc-111">Tipo using static</span><span class="sxs-lookup"><span data-stu-id="b6edc-111">Using static type</span></span>

<span data-ttu-id="b6edc-112">È possibile accedere ai membri statici di un tipo senza dover qualificare l'accesso con il nome del tipo:</span><span class="sxs-lookup"><span data-stu-id="b6edc-112">You can access static members of a type without having to qualify the access with the type name:</span></span>

```csharp
using static System.Console;
using static System.Math;
class Program
{
    static void Main()
    {
        WriteLine(Sqrt(3*3 + 4*4));
    }
}
```

## <a name="remarks"></a><span data-ttu-id="b6edc-113">Note</span><span class="sxs-lookup"><span data-stu-id="b6edc-113">Remarks</span></span>

<span data-ttu-id="b6edc-114">L'ambito di una direttiva `using` è limitato al file in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="b6edc-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>

<span data-ttu-id="b6edc-115">La direttiva `using` può essere visualizzata:</span><span class="sxs-lookup"><span data-stu-id="b6edc-115">The `using` directive can appear:</span></span>

- <span data-ttu-id="b6edc-116">All'inizio del file del codice sorgente, prima di eventuali definizioni di spazio dei nomi o tipo.</span><span class="sxs-lookup"><span data-stu-id="b6edc-116">At the beginning of a source code file, before any namespace or type definitions.</span></span>
- <span data-ttu-id="b6edc-117">In qualsiasi spazio dei nomi, ma prima di un spazio dei nomi o di tipi dichiarati nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b6edc-117">In any namespace, but before any namespace or types declared in this namespace.</span></span>

<span data-ttu-id="b6edc-118">In caso contrario, viene generato l'errore del compilatore [CS1529](../../misc/cs1529.md).</span><span class="sxs-lookup"><span data-stu-id="b6edc-118">Otherwise, compiler error [CS1529](../../misc/cs1529.md) is generated.</span></span>

<span data-ttu-id="b6edc-119">Creare una direttiva alias `using` per semplificare la qualifica di un identificatore in uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="b6edc-119">Create a `using` alias directive to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="b6edc-120">In una direttiva `using` è necessario usare lo spazio dei nomi o il tipo completo indipendentemente dalle direttive `using` che la precedono.</span><span class="sxs-lookup"><span data-stu-id="b6edc-120">In any `using` directive, the fully-qualified namespace or type must be used regardless of the `using` directives that come before it.</span></span> <span data-ttu-id="b6edc-121">Non è possibile usare alcun alias `using` nella dichiarazione di una direttiva `using`.</span><span class="sxs-lookup"><span data-stu-id="b6edc-121">No `using` alias can be used in the declaration of a `using` directive.</span></span> <span data-ttu-id="b6edc-122">Ad esempio, il codice seguente genera un errore del compilatore:</span><span class="sxs-lookup"><span data-stu-id="b6edc-122">For example, the following generates a compiler error:</span></span>

```csharp
using s = System.Text;
using s.RegularExpressions;
```

<span data-ttu-id="b6edc-123">Creare una direttiva `using` per usare i tipi in uno spazio dei nomi senza dover specificare tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b6edc-123">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="b6edc-124">Una direttiva `using` non offre accesso ad alcuno spazio dei nomi annidato nello spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="b6edc-124">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>

<span data-ttu-id="b6edc-125">Gli spazi dei nomi sono disponibili in due categorie: definiti dall'utente e definiti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="b6edc-125">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="b6edc-126">Gli spazi dei nomi definiti dall'utente vengono definiti nel codice.</span><span class="sxs-lookup"><span data-stu-id="b6edc-126">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="b6edc-127">Per un elenco di spazi dei nomi definiti dal sistema, vedere [Browser API .NET](../../../../api/index.md).</span><span class="sxs-lookup"><span data-stu-id="b6edc-127">For a list of the system-defined namespaces, see [.NET API Browser](../../../../api/index.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="b6edc-128">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="b6edc-128">Example 1</span></span>

<span data-ttu-id="b6edc-129">Nell'esempio seguente viene illustrato come definire e usare un alias `using` per uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b6edc-129">The following example shows how to define and use a `using` alias for a namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#8)]

<span data-ttu-id="b6edc-130">Una direttiva alias using non può contenere un tipo generico aperto nella parte destra.</span><span class="sxs-lookup"><span data-stu-id="b6edc-130">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="b6edc-131">Ad esempio, non è possibile creare un alias using per`List<T>`, ma è possibile crearne uno per `List<int>`.</span><span class="sxs-lookup"><span data-stu-id="b6edc-131">For example, you cannot create a using alias for a `List<T>`, but you can create one for a `List<int>`.</span></span>

## <a name="example-2"></a><span data-ttu-id="b6edc-132">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="b6edc-132">Example 2</span></span>

<span data-ttu-id="b6edc-133">Nell'esempio seguente viene illustrato come definire una direttiva `using` e un alias `using` per una classe:</span><span class="sxs-lookup"><span data-stu-id="b6edc-133">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>

[!code-csharp[csrefKeywordsNamespace#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="b6edc-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b6edc-134">C# language specification</span></span>

<span data-ttu-id="b6edc-135">Per altre informazioni, vedere [Direttive using](~/_csharplang/spec/namespaces.md#using-directives) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="b6edc-135">For more information, see [Using directives](~/_csharplang/spec/namespaces.md#using-directives) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="b6edc-136">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="b6edc-136">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6edc-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6edc-137">See also</span></span>

- [<span data-ttu-id="b6edc-138">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b6edc-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b6edc-139">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b6edc-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b6edc-140">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="b6edc-140">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="b6edc-141">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b6edc-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b6edc-142">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="b6edc-142">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
- [<span data-ttu-id="b6edc-143">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="b6edc-143">using Statement</span></span>](using-statement.md)
