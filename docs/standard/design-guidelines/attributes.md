---
title: Attributi
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: c7bbbda88bd2fddb235b9ae639848e08a452c913
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741795"
---
# <a name="attributes"></a><span data-ttu-id="df27c-102">Attributi</span><span class="sxs-lookup"><span data-stu-id="df27c-102">Attributes</span></span>
<span data-ttu-id="df27c-103"><xref:System.Attribute?displayProperty=nameWithType> è una classe di base utilizzata per definire attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="df27c-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>

 <span data-ttu-id="df27c-104">Gli attributi sono annotazioni che possono essere aggiunte a elementi di programmazione quali assembly, tipi, membri e parametri.</span><span class="sxs-lookup"><span data-stu-id="df27c-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="df27c-105">Sono archiviati nei metadati dell'assembly ed è possibile accedervi in fase di esecuzione usando le API di Reflection.</span><span class="sxs-lookup"><span data-stu-id="df27c-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="df27c-106">Il Framework, ad esempio, definisce il <xref:System.ObsoleteAttribute>, che può essere applicato a un tipo o a un membro per indicare che il tipo o il membro è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="df27c-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>

 <span data-ttu-id="df27c-107">Gli attributi possono avere una o più proprietà che contengono dati aggiuntivi correlati all'attributo.</span><span class="sxs-lookup"><span data-stu-id="df27c-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="df27c-108">Ad esempio, `ObsoleteAttribute` potrebbe contenere informazioni aggiuntive sulla versione in cui un tipo o un membro è stato deprecato e la descrizione delle nuove API che sostituiscono l'API obsoleta.</span><span class="sxs-lookup"><span data-stu-id="df27c-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>

 <span data-ttu-id="df27c-109">Quando l'attributo viene applicato, è necessario specificare alcune proprietà di un attributo.</span><span class="sxs-lookup"><span data-stu-id="df27c-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="df27c-110">Queste proprietà sono denominate proprietà obbligatorie o argomenti obbligatori, perché sono rappresentate come parametri del costruttore posizionale.</span><span class="sxs-lookup"><span data-stu-id="df27c-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="df27c-111">Ad esempio, la proprietà <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> del <xref:System.Diagnostics.ConditionalAttribute> è una proprietà obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="df27c-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>

 <span data-ttu-id="df27c-112">Le proprietà che non devono necessariamente essere specificate quando l'attributo viene applicato sono denominate proprietà facoltative (o argomenti facoltativi).</span><span class="sxs-lookup"><span data-stu-id="df27c-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="df27c-113">Sono rappresentate da proprietà impostabili.</span><span class="sxs-lookup"><span data-stu-id="df27c-113">They are represented by settable properties.</span></span> <span data-ttu-id="df27c-114">I compilatori forniscono una sintassi speciale per impostare queste proprietà quando viene applicato un attributo.</span><span class="sxs-lookup"><span data-stu-id="df27c-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="df27c-115">Ad esempio, la proprietà <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> rappresenta un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="df27c-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>

 <span data-ttu-id="df27c-116">✔️ denominare le classi di attributi personalizzate con il suffisso "Attribute".</span><span class="sxs-lookup"><span data-stu-id="df27c-116">✔️ DO name custom attribute classes with the suffix "Attribute."</span></span>

 <span data-ttu-id="df27c-117">✔️ applicare la <xref:System.AttributeUsageAttribute> agli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="df27c-117">✔️ DO apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>

 <span data-ttu-id="df27c-118">✔️ forniscono proprietà impostabili per gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="df27c-118">✔️ DO provide settable properties for optional arguments.</span></span>

 <span data-ttu-id="df27c-119">✔️ forniscono proprietà solo Get per gli argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="df27c-119">✔️ DO provide get-only properties for required arguments.</span></span>

 <span data-ttu-id="df27c-120">✔️ forniscono i parametri del costruttore per inizializzare le proprietà corrispondenti agli argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="df27c-120">✔️ DO provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="df27c-121">Ogni parametro deve avere lo stesso nome (anche se con maiuscole e minuscole diverse) come proprietà corrispondente.</span><span class="sxs-lookup"><span data-stu-id="df27c-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>

 <span data-ttu-id="df27c-122">❌ evitare di fornire parametri del costruttore per inizializzare proprietà corrispondenti agli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="df27c-122">❌ AVOID providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>

 <span data-ttu-id="df27c-123">In altre parole, non dispongono di proprietà che possono essere impostate con un costruttore e un setter.</span><span class="sxs-lookup"><span data-stu-id="df27c-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="df27c-124">Questa linea guida rende molto espliciti gli argomenti facoltativi e quelli necessari, evitando di avere due modi per eseguire la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="df27c-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>

 <span data-ttu-id="df27c-125">❌ evitare l'overload di costruttori di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="df27c-125">❌ AVOID overloading custom attribute constructors.</span></span>

 <span data-ttu-id="df27c-126">La presenza di un solo costruttore comunica chiaramente all'utente quali argomenti sono obbligatori e quali sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="df27c-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>

 <span data-ttu-id="df27c-127">✔️ ESEGUE il sealing delle classi di attributi personalizzate, se possibile.</span><span class="sxs-lookup"><span data-stu-id="df27c-127">✔️ DO seal custom attribute classes, if possible.</span></span> <span data-ttu-id="df27c-128">Questa operazione rende più veloce la ricerca dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="df27c-128">This makes the look-up for the attribute faster.</span></span>

 <span data-ttu-id="df27c-129">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="df27c-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="df27c-130">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="df27c-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="df27c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df27c-131">See also</span></span>

- [<span data-ttu-id="df27c-132">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="df27c-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="df27c-133">Linee guida per l'uso</span><span class="sxs-lookup"><span data-stu-id="df27c-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
