---
title: static (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- static
- static_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8e46dc2f00d1c185379dba1017ca445b9ae5ae72
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="static-c-reference"></a><span data-ttu-id="dca21-102">static (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="dca21-102">static (C# Reference)</span></span>
<span data-ttu-id="dca21-103">Usare il modificatore `static` per dichiarare un membro statico, che appartiene allo stesso tipo invece che a un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="dca21-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="dca21-104">Il modificatore `static` può essere usato con classi, campi, metodi, proprietà, operatori, eventi e costruttori, ma non con indicizzatori, finalizzatori o tipi diversi da classi.</span><span class="sxs-lookup"><span data-stu-id="dca21-104">The `static` modifier can be used with classes, fields, methods, properties, operators, events, and constructors, but it cannot be used with indexers, finalizers, or types other than classes.</span></span> <span data-ttu-id="dca21-105">Per altre informazioni, vedere [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="dca21-105">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dca21-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="dca21-106">Example</span></span>  
 <span data-ttu-id="dca21-107">La classe seguente viene dichiarata come `static` e contiene solo metodi `static`:</span><span class="sxs-lookup"><span data-stu-id="dca21-107">The following class is declared as `static` and contains only `static` methods:</span></span>  
  
 <span data-ttu-id="dca21-108">[!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dca21-108">[!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]</span></span>  
  
 <span data-ttu-id="dca21-109">Una costante o una dichiarazione di tipo è implicitamente un membro statico.</span><span class="sxs-lookup"><span data-stu-id="dca21-109">A constant or type declaration is implicitly a static member.</span></span>  
  
 <span data-ttu-id="dca21-110">Non è possibile fare riferimento a un membro statico tramite un'istanza.</span><span class="sxs-lookup"><span data-stu-id="dca21-110">A static member cannot be referenced through an instance.</span></span> <span data-ttu-id="dca21-111">Al contrario, è possibile farvi riferimento tramite il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="dca21-111">Instead, it is referenced through the type name.</span></span> <span data-ttu-id="dca21-112">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="dca21-112">For example, consider the following class:</span></span>  
  
 <span data-ttu-id="dca21-113">[!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="dca21-113">[!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]</span></span>  
  
 <span data-ttu-id="dca21-114">Per fare riferimento al membro statico `x`, usare il nome completo `MyBaseC.MyStruct.x`, a meno che il membro non è accessibile dallo stesso ambito:</span><span class="sxs-lookup"><span data-stu-id="dca21-114">To refer to the static member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>  
  
```csharp  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 <span data-ttu-id="dca21-115">Quando un'istanza di una classe contiene una copia separata di tutti i campi istanza della classe, è disponibile solo una copia di ogni campo statico.</span><span class="sxs-lookup"><span data-stu-id="dca21-115">While an instance of a class contains a separate copy of all instance fields of the class, there is only one copy of each static field.</span></span>  
  
 <span data-ttu-id="dca21-116">Non è possibile usare [questo](../../../csharp/language-reference/keywords/this.md) per fare riferimento a funzioni di accesso di proprietà o metodi statici.</span><span class="sxs-lookup"><span data-stu-id="dca21-116">It is not possible to use [this](../../../csharp/language-reference/keywords/this.md) to reference static methods or property accessors.</span></span>  
  
 <span data-ttu-id="dca21-117">Se la parola chiave `static` viene applicata a una classe, tutti i membri della classe devono essere statici.</span><span class="sxs-lookup"><span data-stu-id="dca21-117">If the `static` keyword is applied to a class, all the members of the class must be static.</span></span>  
  
 <span data-ttu-id="dca21-118">Le classi e le classi statiche possono disporre di costruttori statici.</span><span class="sxs-lookup"><span data-stu-id="dca21-118">Classes and static classes may have static constructors.</span></span> <span data-ttu-id="dca21-119">I costruttori statici vengono chiamati in un determinato momento tra l'avvio del programma e la creazione di un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="dca21-119">Static constructors are called at some point between when the program starts and the class is instantiated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dca21-120">La parola chiave `static` ha un uso più limitato rispetto a C++.</span><span class="sxs-lookup"><span data-stu-id="dca21-120">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="dca21-121">Per un confronto con la parola chiave di C++, vedere [Classi di archiviazione (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="dca21-121">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>
  
 <span data-ttu-id="dca21-122">Per illustrare i membri statici, si consideri una classe che rappresenta un dipendente della società.</span><span class="sxs-lookup"><span data-stu-id="dca21-122">To demonstrate static members, consider a class that represents a company employee.</span></span> <span data-ttu-id="dca21-123">Si supponga che la classe contenga un metodo di conteggio dei dipendenti e un campo per memorizzare il numero dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="dca21-123">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="dca21-124">Il metodo e il campo non appartengono a nessun dipendente dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="dca21-124">Both the method and the field do not belong to any instance employee.</span></span> <span data-ttu-id="dca21-125">Appartengono invece alla classe aziendale.</span><span class="sxs-lookup"><span data-stu-id="dca21-125">Instead they belong to the company class.</span></span> <span data-ttu-id="dca21-126">Pertanto, devono essere dichiarati come membri statici della classe.</span><span class="sxs-lookup"><span data-stu-id="dca21-126">Therefore, they should be declared as static members of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dca21-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="dca21-127">Example</span></span>  
 <span data-ttu-id="dca21-128">Questo esempio legge il nome e l'ID di un nuovo dipendente, il contatore dipendente viene incrementato di uno e vengono visualizzate le informazioni per il nuovo dipendente e il nuovo numero di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="dca21-128">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="dca21-129">Per semplicità, questo programma legge il numero corrente di dipendenti dalla tastiera.</span><span class="sxs-lookup"><span data-stu-id="dca21-129">For simplicity, this program reads the current number of employees from the keyboard.</span></span> <span data-ttu-id="dca21-130">In un'applicazione reale, queste informazioni devono essere lette da un file.</span><span class="sxs-lookup"><span data-stu-id="dca21-130">In a real application, this information should be read from a file.</span></span>  
  
 <span data-ttu-id="dca21-131">[!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="dca21-131">[!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="dca21-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="dca21-132">Example</span></span>  
 <span data-ttu-id="dca21-133">Questo esempio mostra che anche se è possibile inizializzare un campo statico con un altro campo statico non ancora dichiarato, i risultati non saranno definiti fino a quando non si assegna in modo esplicito un valore al campo statico.</span><span class="sxs-lookup"><span data-stu-id="dca21-133">This example shows that although you can initialize a static field by using another static field not yet declared, the results will be undefined until you explicitly assign a value to the static field.</span></span>  
  
 <span data-ttu-id="dca21-134">[!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="dca21-134">[!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="dca21-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="dca21-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dca21-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dca21-136">See Also</span></span>  
 <span data-ttu-id="dca21-137">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="dca21-137">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="dca21-138">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dca21-138">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="dca21-139">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="dca21-139">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="dca21-140">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="dca21-140">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="dca21-141">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="dca21-141">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)

