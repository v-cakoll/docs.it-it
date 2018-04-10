---
title: static (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c47f4a19843039c27ef9f1602581d1004fb8fd76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="static-c-reference"></a><span data-ttu-id="9f36d-102">static (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9f36d-102">static (C# Reference)</span></span>
<span data-ttu-id="9f36d-103">Usare il modificatore `static` per dichiarare un membro statico, che appartiene allo stesso tipo invece che a un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="9f36d-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="9f36d-104">Il modificatore `static` può essere usato con classi, campi, metodi, proprietà, operatori, eventi e costruttori, ma non con indicizzatori, finalizzatori o tipi diversi da classi.</span><span class="sxs-lookup"><span data-stu-id="9f36d-104">The `static` modifier can be used with classes, fields, methods, properties, operators, events, and constructors, but it cannot be used with indexers, finalizers, or types other than classes.</span></span> <span data-ttu-id="9f36d-105">Per altre informazioni, vedere [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="9f36d-105">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f36d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f36d-106">Example</span></span>  
 <span data-ttu-id="9f36d-107">La classe seguente viene dichiarata come `static` e contiene solo metodi `static`:</span><span class="sxs-lookup"><span data-stu-id="9f36d-107">The following class is declared as `static` and contains only `static` methods:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]  
  
 <span data-ttu-id="9f36d-108">Una costante o una dichiarazione di tipo è implicitamente un membro statico.</span><span class="sxs-lookup"><span data-stu-id="9f36d-108">A constant or type declaration is implicitly a static member.</span></span>  
  
 <span data-ttu-id="9f36d-109">Non è possibile fare riferimento a un membro statico tramite un'istanza.</span><span class="sxs-lookup"><span data-stu-id="9f36d-109">A static member cannot be referenced through an instance.</span></span> <span data-ttu-id="9f36d-110">Al contrario, è possibile farvi riferimento tramite il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="9f36d-110">Instead, it is referenced through the type name.</span></span> <span data-ttu-id="9f36d-111">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="9f36d-111">For example, consider the following class:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]  
  
 <span data-ttu-id="9f36d-112">Per fare riferimento al membro statico `x`, usare il nome completo `MyBaseC.MyStruct.x`, a meno che il membro non è accessibile dallo stesso ambito:</span><span class="sxs-lookup"><span data-stu-id="9f36d-112">To refer to the static member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>  
  
```csharp  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 <span data-ttu-id="9f36d-113">Quando un'istanza di una classe contiene una copia separata di tutti i campi istanza della classe, è disponibile solo una copia di ogni campo statico.</span><span class="sxs-lookup"><span data-stu-id="9f36d-113">While an instance of a class contains a separate copy of all instance fields of the class, there is only one copy of each static field.</span></span>  
  
 <span data-ttu-id="9f36d-114">Non è possibile usare [questo](../../../csharp/language-reference/keywords/this.md) per fare riferimento a funzioni di accesso di proprietà o metodi statici.</span><span class="sxs-lookup"><span data-stu-id="9f36d-114">It is not possible to use [this](../../../csharp/language-reference/keywords/this.md) to reference static methods or property accessors.</span></span>  
  
 <span data-ttu-id="9f36d-115">Se la parola chiave `static` viene applicata a una classe, tutti i membri della classe devono essere statici.</span><span class="sxs-lookup"><span data-stu-id="9f36d-115">If the `static` keyword is applied to a class, all the members of the class must be static.</span></span>  
  
 <span data-ttu-id="9f36d-116">Le classi e le classi statiche possono disporre di costruttori statici.</span><span class="sxs-lookup"><span data-stu-id="9f36d-116">Classes and static classes may have static constructors.</span></span> <span data-ttu-id="9f36d-117">I costruttori statici vengono chiamati in un determinato momento tra l'avvio del programma e la creazione di un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="9f36d-117">Static constructors are called at some point between when the program starts and the class is instantiated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f36d-118">La parola chiave `static` ha un uso più limitato rispetto a C++.</span><span class="sxs-lookup"><span data-stu-id="9f36d-118">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="9f36d-119">Per un confronto con la parola chiave di C++, vedere [Classi di archiviazione (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="9f36d-119">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>
  
 <span data-ttu-id="9f36d-120">Per illustrare i membri statici, si consideri una classe che rappresenta un dipendente della società.</span><span class="sxs-lookup"><span data-stu-id="9f36d-120">To demonstrate static members, consider a class that represents a company employee.</span></span> <span data-ttu-id="9f36d-121">Si supponga che la classe contenga un metodo di conteggio dei dipendenti e un campo per memorizzare il numero dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="9f36d-121">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="9f36d-122">Il metodo e il campo non appartengono a nessun dipendente dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="9f36d-122">Both the method and the field do not belong to any instance employee.</span></span> <span data-ttu-id="9f36d-123">Appartengono invece alla classe aziendale.</span><span class="sxs-lookup"><span data-stu-id="9f36d-123">Instead they belong to the company class.</span></span> <span data-ttu-id="9f36d-124">Pertanto, devono essere dichiarati come membri statici della classe.</span><span class="sxs-lookup"><span data-stu-id="9f36d-124">Therefore, they should be declared as static members of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f36d-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f36d-125">Example</span></span>  
 <span data-ttu-id="9f36d-126">Questo esempio legge il nome e l'ID di un nuovo dipendente, il contatore dipendente viene incrementato di uno e vengono visualizzate le informazioni per il nuovo dipendente e il nuovo numero di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="9f36d-126">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="9f36d-127">Per semplicità, questo programma legge il numero corrente di dipendenti dalla tastiera.</span><span class="sxs-lookup"><span data-stu-id="9f36d-127">For simplicity, this program reads the current number of employees from the keyboard.</span></span> <span data-ttu-id="9f36d-128">In un'applicazione reale, queste informazioni devono essere lette da un file.</span><span class="sxs-lookup"><span data-stu-id="9f36d-128">In a real application, this information should be read from a file.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="9f36d-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f36d-129">Example</span></span>  
 <span data-ttu-id="9f36d-130">Questo esempio mostra che anche se è possibile inizializzare un campo statico con un altro campo statico non ancora dichiarato, i risultati non saranno definiti fino a quando non si assegna in modo esplicito un valore al campo statico.</span><span class="sxs-lookup"><span data-stu-id="9f36d-130">This example shows that although you can initialize a static field by using another static field not yet declared, the results will be undefined until you explicitly assign a value to the static field.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="9f36d-131">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="9f36d-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9f36d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f36d-132">See Also</span></span>  
 [<span data-ttu-id="9f36d-133">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="9f36d-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9f36d-134">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9f36d-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9f36d-135">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="9f36d-135">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9f36d-136">Modificatori</span><span class="sxs-lookup"><span data-stu-id="9f36d-136">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="9f36d-137">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="9f36d-137">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
