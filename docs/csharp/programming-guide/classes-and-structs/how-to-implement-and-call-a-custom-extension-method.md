---
title: Come implementare e chiamare un metodo di estensione personalizzato-Guida per programmatori C#
description: Informazioni su come implementare metodi di estensione per qualsiasi tipo .NET. Il codice client può usare i metodi aggiungendo un riferimento a una DLL e aggiungendo una direttiva using.
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: 7856e78713648a42d1c961f50f7e83f2f7ef05b7
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865060"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="a5aee-104">Come implementare e chiamare un metodo di estensione personalizzato (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a5aee-104">How to implement and call a custom extension method (C# Programming Guide)</span></span>
<span data-ttu-id="a5aee-105">Questo argomento illustra come implementare metodi di estensione personali per qualsiasi tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="a5aee-105">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="a5aee-106">Il codice client può usare i metodi di estensione aggiungendo un riferimento alla DLL che li contiene, e aggiungendo una direttiva [using](../../language-reference/keywords/using-directive.md) che specifica lo spazio dei nomi in cui vengono definiti i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="a5aee-106">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="a5aee-107">Per definire e chiamare il metodo di estensione</span><span class="sxs-lookup"><span data-stu-id="a5aee-107">To define and call the extension method</span></span>  
  
1. <span data-ttu-id="a5aee-108">Definire una [classe](./static-classes-and-static-class-members.md) statica per contenere il metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="a5aee-108">Define a static [class](./static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="a5aee-109">La classe deve essere visibile al codice client.</span><span class="sxs-lookup"><span data-stu-id="a5aee-109">The class must be visible to client code.</span></span> <span data-ttu-id="a5aee-110">Per altre informazioni sulle regole di accessibilità, vedere [Modificatori di accesso](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a5aee-110">For more information about accessibility rules, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
2. <span data-ttu-id="a5aee-111">Implementare il metodo di estensione come metodo statico con almeno la stessa visibilità della classe che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="a5aee-111">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3. <span data-ttu-id="a5aee-112">Il primo parametro del metodo specifica il tipo su cui il metodo opera e deve essere preceduto dal modificatore [this](../../language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="a5aee-112">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../language-reference/keywords/this.md) modifier.</span></span>  
  
4. <span data-ttu-id="a5aee-113">Nel codice chiamante, aggiungere una direttiva `using` per specificare lo [spazio dei nomi](../../language-reference/keywords/namespace.md) che contiene la classe del metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="a5aee-113">In the calling code, add a `using` directive to specify the [namespace](../../language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5. <span data-ttu-id="a5aee-114">Chiamare i metodi come se fossero metodi di istanza sul tipo.</span><span class="sxs-lookup"><span data-stu-id="a5aee-114">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="a5aee-115">Si noti che il primo parametro non viene specificato tramite la chiamata di codice, poiché rappresenta il tipo su cui viene applicato l'operatore e il compilatore conosce già il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a5aee-115">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="a5aee-116">È sufficiente specificare gli argomenti per i parametri da 2 a `n`.</span><span class="sxs-lookup"><span data-stu-id="a5aee-116">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5aee-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5aee-117">Example</span></span>  
 <span data-ttu-id="a5aee-118">Nell'esempio seguente un metodo di estensione denominato `WordCount` viene implementato nella classe `CustomExtensions.StringExtension`.</span><span class="sxs-lookup"><span data-stu-id="a5aee-118">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="a5aee-119">Il metodo opera sulla classe <xref:System.String>, che viene specificata come primo parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="a5aee-119">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="a5aee-120">Lo spazio dei nomi `CustomExtensions` viene importato nello spazio dei nomi dell'applicazione e il metodo viene chiamato all'interno del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="a5aee-120">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="net-security"></a><span data-ttu-id="a5aee-121">Sicurezza .NET</span><span class="sxs-lookup"><span data-stu-id="a5aee-121">.NET Security</span></span>  
 <span data-ttu-id="a5aee-122">I metodi di estensione non presentano vulnerabilità di protezione specifiche.</span><span class="sxs-lookup"><span data-stu-id="a5aee-122">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="a5aee-123">Non possono mai essere usati per rappresentare metodi esistenti su un tipo, perché tutti i conflitti di nomi vengono risolti a favore dell'istanza o del metodo statico definito dal tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="a5aee-123">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="a5aee-124">I metodi di estensione non possono accedere ai dati privati nella classe estesa.</span><span class="sxs-lookup"><span data-stu-id="a5aee-124">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5aee-125">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a5aee-125">See also</span></span>

- [<span data-ttu-id="a5aee-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a5aee-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a5aee-127">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="a5aee-127">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="a5aee-128">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="a5aee-128">LINQ (Language-Integrated Query)</span></span>](../../linq/linq-in-csharp.md)
- [<span data-ttu-id="a5aee-129">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="a5aee-129">Static Classes and Static Class Members</span></span>](./static-classes-and-static-class-members.md)
- [<span data-ttu-id="a5aee-130">protected</span><span class="sxs-lookup"><span data-stu-id="a5aee-130">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="a5aee-131">interno</span><span class="sxs-lookup"><span data-stu-id="a5aee-131">internal</span></span>](../../language-reference/keywords/internal.md)
- [<span data-ttu-id="a5aee-132">pubblico</span><span class="sxs-lookup"><span data-stu-id="a5aee-132">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="a5aee-133">Questo</span><span class="sxs-lookup"><span data-stu-id="a5aee-133">this</span></span>](../../language-reference/keywords/this.md)
- [<span data-ttu-id="a5aee-134">namespace</span><span class="sxs-lookup"><span data-stu-id="a5aee-134">namespace</span></span>](../../language-reference/keywords/namespace.md)
