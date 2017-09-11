---
title: Direttiva using static (Riferimenti per C#)
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: b7d69d0262ba6f450e2cc0d5b30692bba181f9d9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="04754-102">Direttiva using static (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="04754-102">using static Directive (C# Reference)</span></span>

<span data-ttu-id="04754-103">La direttiva `using static` consente di definire un tipo i cui membri statici sono accessibili senza specificare un nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="04754-103">The `using static` directive designates a type whose static members you can access without specifying a type name.</span></span> <span data-ttu-id="04754-104">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="04754-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>
```

<span data-ttu-id="04754-105">dove *fully-qualified-type-name* è il nome del tipo i cui membri statici possono essere usati come riferimento senza specificare un nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="04754-105">where *fully-qualified-type-name* is the name of the type whose static members can be referenced without specifying a type name.</span></span> <span data-ttu-id="04754-106">Se non si specifica un nome di tipo completo (il nome completo dello spazio dei nomi con il nome del tipo), C# genera l'errore del compilatore CS0246: "Impossibile trovare il nome del tipo o dello spazio dei nomi '<type-name>'."</span><span class="sxs-lookup"><span data-stu-id="04754-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error CS0246: "The type or namespace name '<type-name>' could not be found."</span></span>

<span data-ttu-id="04754-107">La direttiva `using static` si applica a qualsiasi tipo che includa membri statici, anche qualora siano presenti membri di istanza.</span><span class="sxs-lookup"><span data-stu-id="04754-107">The `using static` directive applies to any type that has static members, even if it also has instance members.</span></span> <span data-ttu-id="04754-108">Tuttavia, i membri di istanza possono essere chiamati solo tramite l'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="04754-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="04754-109">La direttiva `using static` è stata introdotta in C# 6.</span><span class="sxs-lookup"><span data-stu-id="04754-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="04754-110">Note</span><span class="sxs-lookup"><span data-stu-id="04754-110">Remarks</span></span>
 
<span data-ttu-id="04754-111">Quando si chiama un membro statico si fornisce in genere il nome del tipo e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="04754-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="04754-112">Immettere ripetutamente lo stesso nome di tipo per chiamare i membri del tipo può generare codice troppo dettagliato e incomprensibile.</span><span class="sxs-lookup"><span data-stu-id="04754-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="04754-113">Ad esempio, la seguente definizione di una classe `Circle` fa riferimento a un numero di membri della classe @System.Math.</span><span class="sxs-lookup"><span data-stu-id="04754-113">For example, the following definition of a `Circle` class references a number of members of the @System.Math class.</span></span>
  
<span data-ttu-id="04754-114">[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="04754-114">[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]</span></span>

<span data-ttu-id="04754-115">Eliminando la necessità di fare riferimento in modo esplicito alla classe @System.Math ogni volta che si fa riferimento a un membro, la direttiva `using static` genera un codice più chiaro:</span><span class="sxs-lookup"><span data-stu-id="04754-115">By eliminating the need to explicitly reference the @System.Math class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

<span data-ttu-id="04754-116">[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="04754-116">[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]</span></span>

<span data-ttu-id="04754-117">`using static` importa solo i membri statici accessibili e i tipi annidati dichiarati nel tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="04754-117">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="04754-118">I membri ereditati non vengono importati.</span><span class="sxs-lookup"><span data-stu-id="04754-118">Inherited members are not imported.</span></span>  <span data-ttu-id="04754-119">È possibile eseguire l'importazione da qualsiasi tipo denominato con una direttiva using static, inclusi i moduli Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="04754-119">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="04754-120">Se nei metadati vengono visualizzate funzioni di primo livello F# come membri statici di un tipo denominato il cui nome è un identificatore C# valido, le funzioni F# possono essere importate.</span><span class="sxs-lookup"><span data-stu-id="04754-120">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>  
  
 <span data-ttu-id="04754-121">`using static` crea metodi di estensione dichiarati nel tipo specificato disponibile per la ricerca del metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="04754-121">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="04754-122">Tuttavia, i nomi dei metodi di estensione non vengono importati nell'ambito del riferimento non qualificato nel codice.</span><span class="sxs-lookup"><span data-stu-id="04754-122">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>  
  
 <span data-ttu-id="04754-123">I metodi con lo stesso nome importati da tipi diversi tramite direttive `using static` diverse nella stessa unità di compilazione o nello stesso spazio dei nomi costituiscono un gruppo di metodi.</span><span class="sxs-lookup"><span data-stu-id="04754-123">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="04754-124">La risoluzione dell'overload in questi gruppi di metodi segue le normali regole C#.</span><span class="sxs-lookup"><span data-stu-id="04754-124">Overload resolution within these method groups follows normal C# rules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04754-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="04754-125">Example</span></span>

<span data-ttu-id="04754-126">L'esempio seguente usa la direttiva `using static` per rendere i membri statici della classe @System.Console, @System.Math e @System.String disponibili senza dover specificare il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="04754-126">The following example uses the `using static` directive to make the static members of the @System.Console, @System.Math, and @System.String classes available without having to specify their type name.</span></span>

<span data-ttu-id="04754-127">[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]</span><span class="sxs-lookup"><span data-stu-id="04754-127">[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]</span></span>

<span data-ttu-id="04754-128">Nell'esempio la direttiva `using static` può anche essere stata applicata al tipo @System.Double.</span><span class="sxs-lookup"><span data-stu-id="04754-128">In the example, the `using static` directive could also have been applied to the @System.Double type.</span></span> <span data-ttu-id="04754-129">In questo caso sarebbe stato possibile chiamare il metodo @System.Double.TryParse(System.String,System.Double@) senza specificare un nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="04754-129">This would have made it possible to call the @System.Double.TryParse(System.String,System.Double@) method without specifying a type name.</span></span> <span data-ttu-id="04754-130">Ciò crea tuttavia codice meno leggibile, poiché è necessario controllare le istruzioni `using static` per quale metodo `TryParse` di tipo numerico viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="04754-130">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="04754-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04754-131">See also</span></span>

<span data-ttu-id="04754-132">[Direttiva using](using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="04754-132">[using directive](using-directive.md) </span></span>  
<span data-ttu-id="04754-133">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="04754-133">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="04754-134">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="04754-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="04754-135">[Uso degli spazi dei nomi](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="04754-135">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
<span data-ttu-id="04754-136">[Parole chiave per gli spazi dei nomi](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="04754-136">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
[<span data-ttu-id="04754-137">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="04754-137">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)   

