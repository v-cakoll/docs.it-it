---
title: Cursore1
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: KrzysztofCwalina
ms.openlocfilehash: 7ab499d5a9c8388e9081a07921d3e444c0cdd879
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131430"
---
# <a name="attributes"></a><span data-ttu-id="4ed65-102">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ed65-102">Attributes</span></span>
<span data-ttu-id="4ed65-103"><xref:System.Attribute?displayProperty=nameWithType> una classe di base consente di definire attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4ed65-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="4ed65-104">Gli attributi sono annotazioni che possono essere aggiunti a elementi di programmazione, ad esempio assembly, tipi, membri e parametri.</span><span class="sxs-lookup"><span data-stu-id="4ed65-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="4ed65-105">Essi vengono archiviate nei metadati dell'assembly ed è accessibile in fase di esecuzione usando le API di reflection.</span><span class="sxs-lookup"><span data-stu-id="4ed65-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="4ed65-106">Ad esempio, il Framework definisce il <xref:System.ObsoleteAttribute>, che può essere applicato a un tipo o membro per indicare che il tipo o membro è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="4ed65-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="4ed65-107">Gli attributi possono avere una o più proprietà che contengono dati aggiuntivi correlati all'attributo.</span><span class="sxs-lookup"><span data-stu-id="4ed65-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="4ed65-108">Ad esempio, `ObsoleteAttribute` potrebbe contenere informazioni aggiuntive relative alla versione in cui un tipo o membro è stato deprecato e la descrizione delle nuove API sostituendo l'API obsoleta.</span><span class="sxs-lookup"><span data-stu-id="4ed65-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="4ed65-109">Alcune proprietà di un attributo deve essere specificato quando è applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="4ed65-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="4ed65-110">Queste vengono denominate le proprietà obbligatorie o gli argomenti obbligatori, in quanto vengono rappresentati come parametri posizionali del costruttore.</span><span class="sxs-lookup"><span data-stu-id="4ed65-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="4ed65-111">Ad esempio, il <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> proprietà del <xref:System.Diagnostics.ConditionalAttribute> questa proprietà è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="4ed65-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="4ed65-112">Le proprietà che non hanno necessariamente specificare quando viene applicato l'attributo vengono chiamate proprietà facoltative (o gli argomenti facoltativi).</span><span class="sxs-lookup"><span data-stu-id="4ed65-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="4ed65-113">Sono rappresentate da proprietà impostabili.</span><span class="sxs-lookup"><span data-stu-id="4ed65-113">They are represented by settable properties.</span></span> <span data-ttu-id="4ed65-114">I compilatori forniscono una sintassi speciale per impostare queste proprietà quando viene applicato un attributo.</span><span class="sxs-lookup"><span data-stu-id="4ed65-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="4ed65-115">Ad esempio, il <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> proprietà rappresenta un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4ed65-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="4ed65-116">**✓ DO** denominare le classi di attributo personalizzato con il suffisso "Attributo".</span><span class="sxs-lookup"><span data-stu-id="4ed65-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="4ed65-117">**✓ DO** applica il <xref:System.AttributeUsageAttribute> per gli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4ed65-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="4ed65-118">**✓ DO** forniscono le proprietà impostabili per gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="4ed65-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="4ed65-119">**✓ DO** forniscono proprietà solo get per gli argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4ed65-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="4ed65-120">**✓ DO** forniscono i parametri del costruttore per inizializzare le proprietà corrispondenti per gli argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4ed65-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="4ed65-121">Ogni parametro deve avere lo stesso nome (anche se con maiuscole e minuscole diverse) come la proprietà corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4ed65-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="4ed65-122">**X AVOID** fornendo i parametri del costruttore per inizializzare le proprietà corrispondenti per gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="4ed65-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="4ed65-123">In altre parole, non includono proprietà che possono essere impostate con un costruttore e un setter.</span><span class="sxs-lookup"><span data-stu-id="4ed65-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="4ed65-124">Questa linea guida rende molto esplicite quali gli argomenti sono facoltativi e sono necessari che consenta di evitare la due modi di ottenere la stessa cosa.</span><span class="sxs-lookup"><span data-stu-id="4ed65-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="4ed65-125">**X AVOID** l'overload di costruttori di attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4ed65-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="4ed65-126">Con un solo costruttore chiaramente comunica all'utente cui gli argomenti sono obbligatori e facoltativi.</span><span class="sxs-lookup"><span data-stu-id="4ed65-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="4ed65-127">**✓ DO** proteggere le classi di attributo personalizzato, se possibile.</span><span class="sxs-lookup"><span data-stu-id="4ed65-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="4ed65-128">In questo modo la ricerca per l'attributo più velocemente.</span><span class="sxs-lookup"><span data-stu-id="4ed65-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="4ed65-129">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="4ed65-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4ed65-130">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4ed65-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ed65-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ed65-131">See also</span></span>

- [<span data-ttu-id="4ed65-132">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="4ed65-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="4ed65-133">Linee guida per l'uso</span><span class="sxs-lookup"><span data-stu-id="4ed65-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
