---
title: Modificatore static - Riferimenti per C#
ms.date: 01/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: e7671e9db488a7b50f4ed736864d6fa8d95eef1a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744656"
---
# <a name="static-c-reference"></a><span data-ttu-id="34be5-102">static (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="34be5-102">static (C# Reference)</span></span>

<span data-ttu-id="34be5-103">Usare il modificatore `static` per dichiarare un membro statico, che appartiene allo stesso tipo invece che a un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="34be5-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="34be5-104">È possibile utilizzare il modificatore `static` per dichiarare classi `static`.</span><span class="sxs-lookup"><span data-stu-id="34be5-104">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="34be5-105">In classi, interfacce e struct è possibile aggiungere il modificatore `static` a campi, metodi, proprietà, operatori, eventi e costruttori.</span><span class="sxs-lookup"><span data-stu-id="34be5-105">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="34be5-106">Impossibile utilizzare il modificatore `static` con gli indicizzatori o i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="34be5-106">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="34be5-107">Per altre informazioni, vedere [Classi statiche e membri di classi statiche](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="34be5-107">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="34be5-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="34be5-108">Example</span></span>

<span data-ttu-id="34be5-109">La classe seguente viene dichiarata come `static` e contiene solo metodi `static`:</span><span class="sxs-lookup"><span data-stu-id="34be5-109">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="34be5-110">Una costante o una dichiarazione di tipo è implicitamente un membro `static`.</span><span class="sxs-lookup"><span data-stu-id="34be5-110">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="34be5-111">Non è possibile fare riferimento A un membro `static` tramite un'istanza.</span><span class="sxs-lookup"><span data-stu-id="34be5-111">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="34be5-112">Al contrario, viene fatto riferimento tramite il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="34be5-112">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="34be5-113">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="34be5-113">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="34be5-114">Per fare riferimento al `x``static` membri, utilizzare il nome completo, `MyBaseC.MyStruct.x`, a meno che il membro non sia accessibile dallo stesso ambito:</span><span class="sxs-lookup"><span data-stu-id="34be5-114">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="34be5-115">Mentre un'istanza di una classe contiene una copia separata di tutti i campi di istanza della classe, è presente una sola copia di ogni campo `static`.</span><span class="sxs-lookup"><span data-stu-id="34be5-115">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="34be5-116">Non è possibile usare [`this`](this.md) per fare riferimento a `static` metodi o alle funzioni di accesso alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="34be5-116">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="34be5-117">Se la parola chiave `static` viene applicata a una classe, tutti i membri della classe devono essere `static`.</span><span class="sxs-lookup"><span data-stu-id="34be5-117">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="34be5-118">Classi, interfacce e classi di `static` possono avere costruttori di `static`.</span><span class="sxs-lookup"><span data-stu-id="34be5-118">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="34be5-119">Un costruttore di `static` viene chiamato in un determinato punto tra l'avvio del programma e la creazione di un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="34be5-119">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="34be5-120">La parola chiave `static` ha un uso più limitato rispetto a C++.</span><span class="sxs-lookup"><span data-stu-id="34be5-120">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="34be5-121">Per un confronto con la parola chiave di C++, vedere [Classi di archiviazione (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="34be5-121">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="34be5-122">Per illustrare i membri `static`, prendere in considerazione una classe che rappresenta un dipendente della società.</span><span class="sxs-lookup"><span data-stu-id="34be5-122">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="34be5-123">Si supponga che la classe contenga un metodo di conteggio dei dipendenti e un campo per memorizzare il numero dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="34be5-123">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="34be5-124">Sia il metodo che il campo non appartengono ad alcuna istanza di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="34be5-124">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="34be5-125">Appartengono invece alla classe di dipendenti nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="34be5-125">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="34be5-126">Devono essere dichiarati come membri `static` della classe.</span><span class="sxs-lookup"><span data-stu-id="34be5-126">They should be declared as `static` members of the class.</span></span>

## <a name="example"></a><span data-ttu-id="34be5-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="34be5-127">Example</span></span>

<span data-ttu-id="34be5-128">Questo esempio legge il nome e l'ID di un nuovo dipendente, il contatore dipendente viene incrementato di uno e vengono visualizzate le informazioni per il nuovo dipendente e il nuovo numero di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="34be5-128">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="34be5-129">Questo programma legge il numero corrente di dipendenti dalla tastiera.</span><span class="sxs-lookup"><span data-stu-id="34be5-129">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a><span data-ttu-id="34be5-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="34be5-130">Example</span></span>

<span data-ttu-id="34be5-131">Questo esempio mostra che è possibile inizializzare un campo di `static` usando un altro campo `static` non ancora dichiarato.</span><span class="sxs-lookup"><span data-stu-id="34be5-131">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="34be5-132">I risultati non saranno definiti fino a quando non si assegna in modo esplicito un valore al campo `static`.</span><span class="sxs-lookup"><span data-stu-id="34be5-132">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="34be5-133">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="34be5-133">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="34be5-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34be5-134">See also</span></span>

- [<span data-ttu-id="34be5-135">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="34be5-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="34be5-136">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="34be5-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="34be5-137">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="34be5-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="34be5-138">Modificatori</span><span class="sxs-lookup"><span data-stu-id="34be5-138">Modifiers</span></span>](index.md)
- [<span data-ttu-id="34be5-139">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="34be5-139">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
