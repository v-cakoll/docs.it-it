---
title: Attributes
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: 12a67d75a5f9642408cca69b2e3764a67f101549
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280582"
---
# <a name="attributes"></a><span data-ttu-id="3eb30-102">Attributes</span><span class="sxs-lookup"><span data-stu-id="3eb30-102">Attributes</span></span>

<span data-ttu-id="3eb30-103"><xref:System.Attribute?displayProperty=nameWithType>è una classe di base utilizzata per definire attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3eb30-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>

 <span data-ttu-id="3eb30-104">Gli attributi sono annotazioni che possono essere aggiunte a elementi di programmazione quali assembly, tipi, membri e parametri.</span><span class="sxs-lookup"><span data-stu-id="3eb30-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="3eb30-105">Vengono archiviati nei metadati dell'assembly ed è possibile accedervi in fase di esecuzione usando le API di Reflection.</span><span class="sxs-lookup"><span data-stu-id="3eb30-105">They are stored in the metadata of the assembly and can be accessed at run time using the reflection APIs.</span></span> <span data-ttu-id="3eb30-106">Ad esempio, .NET definisce l' <xref:System.ObsoleteAttribute> attributo, che può essere applicato a un tipo o a un membro per indicare che il tipo o il membro è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="3eb30-106">For example, .NET defines the <xref:System.ObsoleteAttribute> attribute, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>

 <span data-ttu-id="3eb30-107">Gli attributi possono avere una o più proprietà che contengono dati aggiuntivi correlati all'attributo.</span><span class="sxs-lookup"><span data-stu-id="3eb30-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="3eb30-108">Ad esempio, `ObsoleteAttribute` potrebbe contenere informazioni aggiuntive sulla versione in cui un tipo o un membro è stato deprecato e una descrizione della nuova API che sostituisce l'API obsoleta.</span><span class="sxs-lookup"><span data-stu-id="3eb30-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and a description of the new API that replaces the obsolete API.</span></span>

 <span data-ttu-id="3eb30-109">Quando l'attributo viene applicato, è necessario specificare alcune proprietà di un attributo.</span><span class="sxs-lookup"><span data-stu-id="3eb30-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="3eb30-110">Queste proprietà sono denominate proprietà obbligatorie o argomenti obbligatori, perché sono rappresentate come parametri del costruttore posizionale.</span><span class="sxs-lookup"><span data-stu-id="3eb30-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="3eb30-111">Ad esempio, la <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> proprietà di <xref:System.Diagnostics.ConditionalAttribute> è una proprietà obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="3eb30-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>

 <span data-ttu-id="3eb30-112">Le proprietà che non devono necessariamente essere specificate quando l'attributo viene applicato sono denominate proprietà facoltative (o argomenti facoltativi).</span><span class="sxs-lookup"><span data-stu-id="3eb30-112">Properties that don't necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="3eb30-113">Sono rappresentate da proprietà impostabili.</span><span class="sxs-lookup"><span data-stu-id="3eb30-113">They are represented by settable properties.</span></span> <span data-ttu-id="3eb30-114">I compilatori forniscono una sintassi speciale per impostare queste proprietà quando viene applicato un attributo.</span><span class="sxs-lookup"><span data-stu-id="3eb30-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="3eb30-115">Ad esempio, la <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> proprietà rappresenta un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3eb30-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>

 <span data-ttu-id="3eb30-116">✔️ denominare le classi di attributi personalizzate con il suffisso "Attribute".</span><span class="sxs-lookup"><span data-stu-id="3eb30-116">✔️ DO name custom attribute classes with the suffix "Attribute."</span></span>

 <span data-ttu-id="3eb30-117">✔️ applicare agli <xref:System.AttributeUsageAttribute> attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3eb30-117">✔️ DO apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>

 <span data-ttu-id="3eb30-118">✔️ forniscono proprietà impostabili per gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="3eb30-118">✔️ DO provide settable properties for optional arguments.</span></span>

 <span data-ttu-id="3eb30-119">✔️ forniscono proprietà solo Get per gli argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="3eb30-119">✔️ DO provide get-only properties for required arguments.</span></span>

 <span data-ttu-id="3eb30-120">✔️ forniscono i parametri del costruttore per inizializzare le proprietà corrispondenti agli argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="3eb30-120">✔️ DO provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="3eb30-121">Ogni parametro deve avere lo stesso nome (anche se con maiuscole e minuscole diverse) come proprietà corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3eb30-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>

 <span data-ttu-id="3eb30-122">❌EVITARE di fornire parametri del costruttore per inizializzare proprietà corrispondenti agli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="3eb30-122">❌ AVOID providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>

 <span data-ttu-id="3eb30-123">In altre parole, non dispongono di proprietà che possono essere impostate con un costruttore e un setter.</span><span class="sxs-lookup"><span data-stu-id="3eb30-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="3eb30-124">Questa linea guida rende molto espliciti gli argomenti facoltativi e quelli necessari, evitando di avere due modi per eseguire la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="3eb30-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>

 <span data-ttu-id="3eb30-125">❌EVITARE l'overload di costruttori di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3eb30-125">❌ AVOID overloading custom attribute constructors.</span></span>

 <span data-ttu-id="3eb30-126">La presenza di un solo costruttore comunica chiaramente all'utente quali argomenti sono obbligatori e quali sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="3eb30-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>

 <span data-ttu-id="3eb30-127">✔️ ESEGUE il sealing delle classi di attributi personalizzate, se possibile.</span><span class="sxs-lookup"><span data-stu-id="3eb30-127">✔️ DO seal custom attribute classes, if possible.</span></span> <span data-ttu-id="3eb30-128">Questa operazione rende più veloce la ricerca dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="3eb30-128">This makes the look-up for the attribute faster.</span></span>

 <span data-ttu-id="3eb30-129">*Parti &copy; 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="3eb30-129">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3eb30-130">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="3eb30-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3eb30-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eb30-131">See also</span></span>

- [<span data-ttu-id="3eb30-132">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="3eb30-132">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="3eb30-133">Linee guida sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="3eb30-133">Usage Guidelines</span></span>](usage-guidelines.md)
