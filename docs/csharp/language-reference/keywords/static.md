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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76744656"
---
# <a name="static-c-reference"></a><span data-ttu-id="a1bc1-102">static (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a1bc1-102">static (C# Reference)</span></span>

<span data-ttu-id="a1bc1-103">Usare il modificatore `static` per dichiarare un membro statico, che appartiene allo stesso tipo invece che a un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="a1bc1-104">Il `static` modificatore può `static` essere utilizzato per dichiarare le classi.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-104">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="a1bc1-105">Nelle classi, interfacce e struct è `static` possibile aggiungere il modificatore a campi, metodi, proprietà, operatori, eventi e costruttori.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-105">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="a1bc1-106">Il `static` modificatore non può essere utilizzato con gli indicizzatori o i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-106">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="a1bc1-107">Per ulteriori informazioni, vedere [Classi statiche e Membri di classi statiche](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="a1bc1-107">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="a1bc1-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1bc1-108">Example</span></span>

<span data-ttu-id="a1bc1-109">La classe seguente viene dichiarata come `static` e contiene solo metodi `static`:</span><span class="sxs-lookup"><span data-stu-id="a1bc1-109">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="a1bc1-110">Una dichiarazione di tipo `static` o costante è implicitamente un membro.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-110">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="a1bc1-111">Non `static` è possibile fare riferimento a un membro tramite un'istanza.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-111">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="a1bc1-112">Al contrario, viene fatto riferimento tramite il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-112">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="a1bc1-113">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="a1bc1-113">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="a1bc1-114">Per fare `static` riferimento `x`al membro , `MyBaseC.MyStruct.x`utilizzare il nome completo, , a meno che il membro non sia accessibile dallo stesso ambito:</span><span class="sxs-lookup"><span data-stu-id="a1bc1-114">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="a1bc1-115">Mentre un'istanza di una classe contiene una copia separata di tutti i `static` campi di istanza della classe, è disponibile una sola copia di ogni campo.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-115">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="a1bc1-116">Non è possibile usare [`this`](this.md) metodi `static` di riferimento o funzioni di accesso alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-116">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="a1bc1-117">Se `static` la parola chiave viene applicata a una `static`classe, tutti i membri della classe devono essere .</span><span class="sxs-lookup"><span data-stu-id="a1bc1-117">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="a1bc1-118">Le classi, le `static` interfacce `static` e le classi possono avere costruttori.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-118">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="a1bc1-119">Un `static` costruttore viene chiamato a un certo punto tra l'avvio del programma e la classe viene creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-119">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="a1bc1-120">La parola chiave `static` ha un uso più limitato rispetto a C++.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-120">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="a1bc1-121">Per un confronto con la parola chiave di C++, vedere [Classi di archiviazione (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="a1bc1-121">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="a1bc1-122">Per `static` illustrare i membri, prendere in considerazione una classe che rappresenta un dipendente dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-122">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="a1bc1-123">Si supponga che la classe contenga un metodo di conteggio dei dipendenti e un campo per memorizzare il numero dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-123">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="a1bc1-124">Sia il metodo che il campo non appartengono a nessuna istanza del dipendente.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-124">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="a1bc1-125">Appartengono invece alla classe dei dipendenti nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-125">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="a1bc1-126">Devono essere dichiarati come `static` membri della classe.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-126">They should be declared as `static` members of the class.</span></span>

## <a name="example"></a><span data-ttu-id="a1bc1-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1bc1-127">Example</span></span>

<span data-ttu-id="a1bc1-128">Questo esempio legge il nome e l'ID di un nuovo dipendente, il contatore dipendente viene incrementato di uno e vengono visualizzate le informazioni per il nuovo dipendente e il nuovo numero di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-128">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="a1bc1-129">Questo programma legge il numero corrente di dipendenti dalla tastiera.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-129">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a><span data-ttu-id="a1bc1-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1bc1-130">Example</span></span>

<span data-ttu-id="a1bc1-131">In questo esempio viene `static` illustrato che `static` è possibile inizializzare un campo utilizzando un altro campo non ancora dichiarato.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-131">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="a1bc1-132">I risultati rimarranno indefiniti fino a `static` quando non si assegna esplicitamente un valore al campo.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-132">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="a1bc1-133">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a1bc1-133">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a1bc1-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1bc1-134">See also</span></span>

- [<span data-ttu-id="a1bc1-135">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="a1bc1-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a1bc1-136">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a1bc1-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a1bc1-137">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="a1bc1-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a1bc1-138">Modificatori</span><span class="sxs-lookup"><span data-stu-id="a1bc1-138">Modifiers</span></span>](index.md)
- [<span data-ttu-id="a1bc1-139">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="a1bc1-139">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
