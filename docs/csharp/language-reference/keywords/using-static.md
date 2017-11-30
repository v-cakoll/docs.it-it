---
title: Direttiva using static (Riferimenti per C#)
ms.date: 03/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5838bede475cf2ad1b72518770241e86206a06bb
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="98766-102">Direttiva using static (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="98766-102">using static Directive (C# Reference)</span></span>

<span data-ttu-id="98766-103">La direttiva `using static` consente di definire un tipo i cui membri statici sono accessibili senza specificare un nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="98766-103">The `using static` directive designates a type whose static members you can access without specifying a type name.</span></span> <span data-ttu-id="98766-104">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="98766-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>
```

<span data-ttu-id="98766-105">dove *fully-qualified-type-name* è il nome del tipo i cui membri statici possono essere usati come riferimento senza specificare un nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="98766-105">where *fully-qualified-type-name* is the name of the type whose static members can be referenced without specifying a type name.</span></span> <span data-ttu-id="98766-106">Se non si specifica un nome di tipo completo (il nome completo dello spazio dei nomi con il nome del tipo), C# genera l'errore del compilatore CS0246: "Impossibile trovare il nome del tipo o dello spazio dei nomi '<type-name>'."</span><span class="sxs-lookup"><span data-stu-id="98766-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error CS0246: "The type or namespace name '<type-name>' could not be found."</span></span>

<span data-ttu-id="98766-107">La direttiva `using static` si applica a qualsiasi tipo che includa membri statici, anche qualora siano presenti membri di istanza.</span><span class="sxs-lookup"><span data-stu-id="98766-107">The `using static` directive applies to any type that has static members, even if it also has instance members.</span></span> <span data-ttu-id="98766-108">Tuttavia, i membri di istanza possono essere chiamati solo tramite l'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="98766-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="98766-109">La direttiva `using static` è stata introdotta in C# 6.</span><span class="sxs-lookup"><span data-stu-id="98766-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="98766-110">Note</span><span class="sxs-lookup"><span data-stu-id="98766-110">Remarks</span></span>
 
<span data-ttu-id="98766-111">Quando si chiama un membro statico si fornisce in genere il nome del tipo e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="98766-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="98766-112">Immettere ripetutamente lo stesso nome di tipo per chiamare i membri del tipo può generare codice troppo dettagliato e incomprensibile.</span><span class="sxs-lookup"><span data-stu-id="98766-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="98766-113">Ad esempio, la seguente definizione di una classe `Circle` fa riferimento a un numero di membri della classe <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="98766-113">For example, the following definition of a `Circle` class references a number of members of the <xref:System.Math> class.</span></span>
  
[!code-csharp[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

<span data-ttu-id="98766-114">Eliminando la necessità di fare riferimento in modo esplicito alla classe <xref:System.Math> ogni volta che si fa riferimento a un membro, la direttiva `using static` genera un codice più chiaro:</span><span class="sxs-lookup"><span data-stu-id="98766-114">By eliminating the need to explicitly reference the <xref:System.Math> class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

[!code-csharp[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

<span data-ttu-id="98766-115">`using static` importa solo i membri statici accessibili e i tipi annidati dichiarati nel tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="98766-115">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="98766-116">I membri ereditati non vengono importati.</span><span class="sxs-lookup"><span data-stu-id="98766-116">Inherited members are not imported.</span></span>  <span data-ttu-id="98766-117">È possibile eseguire l'importazione da qualsiasi tipo denominato con una direttiva using static, inclusi i moduli Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="98766-117">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="98766-118">Se nei metadati vengono visualizzate funzioni di primo livello F# come membri statici di un tipo denominato il cui nome è un identificatore C# valido, le funzioni F# possono essere importate.</span><span class="sxs-lookup"><span data-stu-id="98766-118">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>  
  
 <span data-ttu-id="98766-119">`using static` crea metodi di estensione dichiarati nel tipo specificato disponibile per la ricerca del metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="98766-119">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="98766-120">Tuttavia, i nomi dei metodi di estensione non vengono importati nell'ambito del riferimento non qualificato nel codice.</span><span class="sxs-lookup"><span data-stu-id="98766-120">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>  
  
 <span data-ttu-id="98766-121">I metodi con lo stesso nome importati da tipi diversi tramite direttive `using static` diverse nella stessa unità di compilazione o nello stesso spazio dei nomi costituiscono un gruppo di metodi.</span><span class="sxs-lookup"><span data-stu-id="98766-121">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="98766-122">La risoluzione dell'overload in questi gruppi di metodi segue le normali regole C#.</span><span class="sxs-lookup"><span data-stu-id="98766-122">Overload resolution within these method groups follows normal C# rules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98766-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="98766-123">Example</span></span>

<span data-ttu-id="98766-124">L'esempio seguente usa la direttiva `using static` per rendere i membri statici della classe <xref:System.Console>, <xref:System.Math> e <xref:System.String> disponibili senza dover specificare il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="98766-124">The following example uses the `using static` directive to make the static members of the <xref:System.Console>, <xref:System.Math>, and <xref:System.String> classes available without having to specify their type name.</span></span>

[!code-csharp[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

<span data-ttu-id="98766-125">Nell'esempio la direttiva `using static` può anche essere stata applicata al tipo <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="98766-125">In the example, the `using static` directive could also have been applied to the <xref:System.Double> type.</span></span> <span data-ttu-id="98766-126">Questo sarebbe hanno reso possibile chiamare il <xref:System.Double.TryParse(System.String,System.Double@)> metodo senza specificare un nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="98766-126">This would have made it possible to call the <xref:System.Double.TryParse(System.String,System.Double@)> method without specifying a type name.</span></span> <span data-ttu-id="98766-127">Ciò crea tuttavia codice meno leggibile, poiché è necessario controllare le istruzioni `using static` per quale metodo `TryParse` di tipo numerico viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="98766-127">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="98766-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98766-128">See also</span></span>

<span data-ttu-id="98766-129">[Direttiva using](using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="98766-129">[using directive](using-directive.md) </span></span>  
<span data-ttu-id="98766-130">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="98766-130">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="98766-131">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="98766-131">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="98766-132">[Uso degli spazi dei nomi](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="98766-132">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
<span data-ttu-id="98766-133">[Parole chiave per gli spazi dei nomi](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="98766-133">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
[<span data-ttu-id="98766-134">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="98766-134">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)   
