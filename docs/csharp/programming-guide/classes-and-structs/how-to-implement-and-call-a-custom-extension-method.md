---
title: 'Procedura: Implementare e chiamare un metodo di estensione personalizzato - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: 2fe07f8e4311417980caccc9c286b4f94c7ea994
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65585976"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="f8068-102">Procedura: Implementare e chiamare un metodo di estensione personalizzato (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f8068-102">How to: Implement and Call a Custom Extension Method (C# Programming Guide)</span></span>
<span data-ttu-id="f8068-103">Questo argomento illustra come implementare metodi di estensione personali per qualsiasi tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="f8068-103">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="f8068-104">Il codice client può usare i metodi di estensione aggiungendo un riferimento alla DLL che li contiene, e aggiungendo una direttiva [using](../../../csharp/language-reference/keywords/using-directive.md) che specifica lo spazio dei nomi in cui vengono definiti i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="f8068-104">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../../csharp/language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="f8068-105">Per definire e chiamare il metodo di estensione</span><span class="sxs-lookup"><span data-stu-id="f8068-105">To define and call the extension method</span></span>  
  
1. <span data-ttu-id="f8068-106">Definire una [classe](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) statica per contenere il metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="f8068-106">Define a static [class](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="f8068-107">La classe deve essere visibile al codice client.</span><span class="sxs-lookup"><span data-stu-id="f8068-107">The class must be visible to client code.</span></span> <span data-ttu-id="f8068-108">Per altre informazioni sulle regole di accessibilità, vedere [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="f8068-108">For more information about accessibility rules, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
2. <span data-ttu-id="f8068-109">Implementare il metodo di estensione come metodo statico con almeno la stessa visibilità della classe che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="f8068-109">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3. <span data-ttu-id="f8068-110">Il primo parametro del metodo specifica il tipo su cui il metodo opera e deve essere preceduto dal modificatore [this](../../../csharp/language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="f8068-110">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../../csharp/language-reference/keywords/this.md) modifier.</span></span>  
  
4. <span data-ttu-id="f8068-111">Nel codice chiamante, aggiungere una direttiva `using` per specificare lo [spazio dei nomi](../../../csharp/language-reference/keywords/namespace.md) che contiene la classe del metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="f8068-111">In the calling code, add a `using` directive to specify the [namespace](../../../csharp/language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5. <span data-ttu-id="f8068-112">Chiamare i metodi come se fossero metodi di istanza sul tipo.</span><span class="sxs-lookup"><span data-stu-id="f8068-112">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="f8068-113">Si noti che il primo parametro non viene specificato tramite la chiamata di codice, poiché rappresenta il tipo su cui viene applicato l'operatore e il compilatore conosce già il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f8068-113">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="f8068-114">È sufficiente specificare gli argomenti per i parametri da 2 a `n`.</span><span class="sxs-lookup"><span data-stu-id="f8068-114">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8068-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8068-115">Example</span></span>  
 <span data-ttu-id="f8068-116">Nell'esempio seguente un metodo di estensione denominato `WordCount` viene implementato nella classe `CustomExtensions.StringExtension`.</span><span class="sxs-lookup"><span data-stu-id="f8068-116">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="f8068-117">Il metodo opera sulla classe <xref:System.String>, che viene specificata come primo parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="f8068-117">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="f8068-118">Lo spazio dei nomi `CustomExtensions` viene importato nello spazio dei nomi dell'applicazione e il metodo viene chiamato all'interno del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="f8068-118">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="f8068-119">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f8068-119">.NET Framework Security</span></span>  
 <span data-ttu-id="f8068-120">I metodi di estensione non presentano vulnerabilità di protezione specifiche.</span><span class="sxs-lookup"><span data-stu-id="f8068-120">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="f8068-121">Non possono mai essere usati per rappresentare metodi esistenti su un tipo, perché tutti i conflitti di nomi vengono risolti a favore dell'istanza o del metodo statico definito dal tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="f8068-121">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="f8068-122">I metodi di estensione non possono accedere ai dati privati nella classe estesa.</span><span class="sxs-lookup"><span data-stu-id="f8068-122">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8068-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8068-123">See also</span></span>

- [<span data-ttu-id="f8068-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f8068-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f8068-125">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="f8068-125">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [<span data-ttu-id="f8068-126">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="f8068-126">LINQ (Language-Integrated Query)</span></span>](../../../csharp/linq/linq-in-csharp.md)
- [<span data-ttu-id="f8068-127">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="f8068-127">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="f8068-128">protected</span><span class="sxs-lookup"><span data-stu-id="f8068-128">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
- [<span data-ttu-id="f8068-129">internal</span><span class="sxs-lookup"><span data-stu-id="f8068-129">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
- [<span data-ttu-id="f8068-130">public</span><span class="sxs-lookup"><span data-stu-id="f8068-130">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="f8068-131">this</span><span class="sxs-lookup"><span data-stu-id="f8068-131">this</span></span>](../../../csharp/language-reference/keywords/this.md)
- [<span data-ttu-id="f8068-132">namespace</span><span class="sxs-lookup"><span data-stu-id="f8068-132">namespace</span></span>](../../../csharp/language-reference/keywords/namespace.md)
