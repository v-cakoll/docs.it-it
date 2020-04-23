---
title: Modificatore static - Riferimenti per C#
ms.date: 04/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: 771bcfdac4c4bf27c15da4bc374d804405317a78
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102060"
---
# <a name="static-c-reference"></a><span data-ttu-id="47d7b-102">static (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="47d7b-102">static (C# Reference)</span></span>

<span data-ttu-id="47d7b-103">Questa pagina `static` copre la parola chiave modificatore.</span><span class="sxs-lookup"><span data-stu-id="47d7b-103">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="47d7b-104">Anche `static` la parola chiave [`using static`](using-static.md) fa parte della direttiva.</span><span class="sxs-lookup"><span data-stu-id="47d7b-104">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="47d7b-105">Usare il modificatore `static` per dichiarare un membro statico, che appartiene allo stesso tipo invece che a un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="47d7b-105">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="47d7b-106">Il `static` modificatore può `static` essere utilizzato per dichiarare le classi.</span><span class="sxs-lookup"><span data-stu-id="47d7b-106">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="47d7b-107">Nelle classi, interfacce e struct è `static` possibile aggiungere il modificatore a campi, metodi, proprietà, operatori, eventi e costruttori.</span><span class="sxs-lookup"><span data-stu-id="47d7b-107">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="47d7b-108">Il `static` modificatore non può essere utilizzato con gli indicizzatori o i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="47d7b-108">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="47d7b-109">Per ulteriori informazioni, vedere [Classi statiche e Membri di classi statiche](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="47d7b-109">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example---static-class"></a><span data-ttu-id="47d7b-110">Esempio - classe statica</span><span class="sxs-lookup"><span data-stu-id="47d7b-110">Example - static class</span></span>

<span data-ttu-id="47d7b-111">La classe seguente viene dichiarata come `static` e contiene solo metodi `static`:</span><span class="sxs-lookup"><span data-stu-id="47d7b-111">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="47d7b-112">Una dichiarazione di tipo `static` o costante è implicitamente un membro.</span><span class="sxs-lookup"><span data-stu-id="47d7b-112">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="47d7b-113">Non `static` è possibile fare riferimento a un membro tramite un'istanza.</span><span class="sxs-lookup"><span data-stu-id="47d7b-113">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="47d7b-114">Al contrario, viene fatto riferimento tramite il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="47d7b-114">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="47d7b-115">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="47d7b-115">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="47d7b-116">Per fare `static` riferimento `x`al membro , `MyBaseC.MyStruct.x`utilizzare il nome completo, , a meno che il membro non sia accessibile dallo stesso ambito:</span><span class="sxs-lookup"><span data-stu-id="47d7b-116">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="47d7b-117">Mentre un'istanza di una classe contiene una copia separata di tutti i `static` campi di istanza della classe, è disponibile una sola copia di ogni campo.</span><span class="sxs-lookup"><span data-stu-id="47d7b-117">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="47d7b-118">Non è possibile usare [`this`](this.md) metodi `static` di riferimento o funzioni di accesso alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="47d7b-118">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="47d7b-119">Se `static` la parola chiave viene applicata a una `static`classe, tutti i membri della classe devono essere .</span><span class="sxs-lookup"><span data-stu-id="47d7b-119">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="47d7b-120">Le classi, le `static` interfacce `static` e le classi possono avere costruttori.</span><span class="sxs-lookup"><span data-stu-id="47d7b-120">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="47d7b-121">Un `static` costruttore viene chiamato a un certo punto tra l'avvio del programma e la classe viene creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="47d7b-121">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="47d7b-122">La parola chiave `static` ha un uso più limitato rispetto a C++.</span><span class="sxs-lookup"><span data-stu-id="47d7b-122">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="47d7b-123">Per un confronto con la parola chiave di C++, vedere [Classi di archiviazione (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="47d7b-123">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="47d7b-124">Per `static` illustrare i membri, prendere in considerazione una classe che rappresenta un dipendente dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="47d7b-124">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="47d7b-125">Si supponga che la classe contenga un metodo di conteggio dei dipendenti e un campo per memorizzare il numero dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="47d7b-125">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="47d7b-126">Sia il metodo che il campo non appartengono a nessuna istanza del dipendente.</span><span class="sxs-lookup"><span data-stu-id="47d7b-126">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="47d7b-127">Appartengono invece alla classe dei dipendenti nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="47d7b-127">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="47d7b-128">Devono essere dichiarati come `static` membri della classe.</span><span class="sxs-lookup"><span data-stu-id="47d7b-128">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="47d7b-129">Esempio - campo statico e metodo</span><span class="sxs-lookup"><span data-stu-id="47d7b-129">Example - static field and method</span></span>

<span data-ttu-id="47d7b-130">Questo esempio legge il nome e l'ID di un nuovo dipendente, il contatore dipendente viene incrementato di uno e vengono visualizzate le informazioni per il nuovo dipendente e il nuovo numero di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="47d7b-130">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="47d7b-131">Questo programma legge il numero corrente di dipendenti dalla tastiera.</span><span class="sxs-lookup"><span data-stu-id="47d7b-131">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="47d7b-132">Esempio - inizializzazione staticaExample - static initialization</span><span class="sxs-lookup"><span data-stu-id="47d7b-132">Example - static initialization</span></span>

<span data-ttu-id="47d7b-133">In questo esempio viene `static` illustrato che `static` è possibile inizializzare un campo utilizzando un altro campo non ancora dichiarato.</span><span class="sxs-lookup"><span data-stu-id="47d7b-133">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="47d7b-134">I risultati rimarranno indefiniti fino a `static` quando non si assegna esplicitamente un valore al campo.</span><span class="sxs-lookup"><span data-stu-id="47d7b-134">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="47d7b-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="47d7b-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="47d7b-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47d7b-136">See also</span></span>

- [<span data-ttu-id="47d7b-137">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="47d7b-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="47d7b-138">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="47d7b-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="47d7b-139">Parole chiave di C</span><span class="sxs-lookup"><span data-stu-id="47d7b-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="47d7b-140">Modificatori</span><span class="sxs-lookup"><span data-stu-id="47d7b-140">Modifiers</span></span>](index.md)
- [<span data-ttu-id="47d7b-141">utilizzando la direttiva statica</span><span class="sxs-lookup"><span data-stu-id="47d7b-141">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="47d7b-142">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="47d7b-142">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
