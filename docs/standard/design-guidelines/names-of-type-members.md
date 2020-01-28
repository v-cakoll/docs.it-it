---
title: Nomi di membri dei tipi
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
ms.openlocfilehash: 81c837bd045992043208a59f6ee16803c1d6eb3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744185"
---
# <a name="names-of-type-members"></a><span data-ttu-id="e2dd4-102">Nomi di membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="e2dd4-102">Names of Type Members</span></span>
<span data-ttu-id="e2dd4-103">I tipi sono costituiti da membri: metodi, proprietà, eventi, costruttori e campi.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="e2dd4-104">Le sezioni seguenti illustrano le linee guida per assegnare nomi ai membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-104">The following sections describe guidelines for naming type members.</span></span>

## <a name="names-of-methods"></a><span data-ttu-id="e2dd4-105">Nomi dei metodi</span><span class="sxs-lookup"><span data-stu-id="e2dd4-105">Names of Methods</span></span>
 <span data-ttu-id="e2dd4-106">I metodi sono il mezzo per l'esecuzione delle azioni. Pertanto le linee guida di progettazione richiedono che i nomi dei metodi siano verbi o frasi verbali.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="e2dd4-107">L'osservazione di questa linea guida è anche utile per distinguere i nomi dei metodi dai nomi delle proprietà e dei tipi, che sono frasi nominali o aggettivali.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>

 <span data-ttu-id="e2dd4-108">✔️ assegnare i nomi dei metodi che sono verbi o frasi verbo.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-108">✔️ DO give methods names that are verbs or verb phrases.</span></span>

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a><span data-ttu-id="e2dd4-109">Nomi delle proprietà</span><span class="sxs-lookup"><span data-stu-id="e2dd4-109">Names of Properties</span></span>
 <span data-ttu-id="e2dd4-110">A differenza degli altri membri, è necessario assegnare alle proprietà sintagmi nominali o nomi aggettivali.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="e2dd4-111">Il motivo è che una proprietà fa riferimento ai dati e il nome della proprietà deve riflettere questo fatto.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="e2dd4-112">Per i nomi delle proprietà viene sempre usata la notazione Pascal.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-112">PascalCasing is always used for property names.</span></span>

 <span data-ttu-id="e2dd4-113">✔️ le proprietà del nome usando un sostantivo, una frase nominale o un aggettivo.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-113">✔️ DO name properties using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="e2dd4-114">❌ non dispongono di proprietà corrispondenti al nome dei metodi "Get", come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e2dd4-114">❌ DO NOT have properties that match the name of "Get" methods as in the following example:</span></span>

 <span data-ttu-id="e2dd4-115">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span><span class="sxs-lookup"><span data-stu-id="e2dd4-115">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span></span>

 <span data-ttu-id="e2dd4-116">Questo criterio in genere indica che la proprietà dovrebbe di fatto essere un metodo.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-116">This pattern typically indicates that the property should really be a method.</span></span>

 <span data-ttu-id="e2dd4-117">✔️ ESEGUIRE le proprietà della raccolta dei nomi con una frase plurale che descrive gli elementi nella raccolta invece di usare una frase singolare seguita da "list" o "Collection".</span><span class="sxs-lookup"><span data-stu-id="e2dd4-117">✔️ DO name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection".</span></span>

 <span data-ttu-id="e2dd4-118">✔️ denominare le proprietà booleane con una frase affermativa (`CanSeek` invece di `CantSeek`).</span><span class="sxs-lookup"><span data-stu-id="e2dd4-118">✔️ DO name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="e2dd4-119">Facoltativamente, è anche possibile precedere le proprietà booleane con "is", "Can" o "has", ma solo dove viene aggiunto value.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-119">Optionally, you can also prefix Boolean properties with "Is", "Can", or "Has", but only where it adds value.</span></span>

 <span data-ttu-id="e2dd4-120">✔️ PROVARE a assegnare a una proprietà lo stesso nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-120">✔️ CONSIDER giving a property the same name as its type.</span></span>

 <span data-ttu-id="e2dd4-121">Ad esempio, la proprietà seguente ottiene e imposta correttamente un valore di enumerazione denominato `Color`, pertanto è denominata `Color`:</span><span class="sxs-lookup"><span data-stu-id="e2dd4-121">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a><span data-ttu-id="e2dd4-122">Nomi degli eventi</span><span class="sxs-lookup"><span data-stu-id="e2dd4-122">Names of Events</span></span>
 <span data-ttu-id="e2dd4-123">Gli eventi fanno sempre riferimento a un'azione, che può essere in corso o già terminata.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-123">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="e2dd4-124">Pertanto, come nel caso dei metodi, i nomi degli eventi devono essere verbi e il tempo verbale indica il momento in cui viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-124">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>

 <span data-ttu-id="e2dd4-125">✔️ ESEGUIRE gli eventi di denominazione con un verbo o una frase verbo.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-125">✔️ DO name events with a verb or a verb phrase.</span></span>

 <span data-ttu-id="e2dd4-126">Alcuni esempi sono `Clicked`, `Painting` o `DroppedDown`.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-126">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>

 <span data-ttu-id="e2dd4-127">✔️ assegnare i nomi degli eventi con un concetto di prima e dopo, usando le decine attuali e precedenti.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-127">✔️ DO give events names with a concept of before and after, using the present and past tenses.</span></span>

 <span data-ttu-id="e2dd4-128">Ad esempio, un evento di chiusura generato prima della chiusura di una finestra può essere chiamato `Closing`, mentre uno generato dopo la chiusura della finestra può essere chiamato `Closed`.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-128">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>

 <span data-ttu-id="e2dd4-129">❌ non usare prefissi o postcorrezioni "before" o "After" per indicare gli eventi pre-e post-post.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-129">❌ DO NOT use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="e2dd4-130">Usare il presente e il passato come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-130">Use present and past tenses as just described.</span></span>

 <span data-ttu-id="e2dd4-131">✔️ i gestori eventi dei nomi (delegati usati come tipi di eventi) con il suffisso "EventHandler", come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e2dd4-131">✔️ DO name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 <span data-ttu-id="e2dd4-132">✔️ utilizzare due parametri denominati `sender` e `e` nei gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-132">✔️ DO use two parameters named `sender` and `e` in event handlers.</span></span>

 <span data-ttu-id="e2dd4-133">Il parametro sender rappresenta l'oggetto che ha generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-133">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="e2dd4-134">Il parametro sender è in genere di tipo `object`, anche se è possibile usare un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-134">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>

 <span data-ttu-id="e2dd4-135">✔️ le classi di argomenti dell'evento Name con il suffisso "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="e2dd4-135">✔️ DO name event argument classes with the "EventArgs" suffix.</span></span>

## <a name="names-of-fields"></a><span data-ttu-id="e2dd4-136">Nomi dei campi</span><span class="sxs-lookup"><span data-stu-id="e2dd4-136">Names of Fields</span></span>
 <span data-ttu-id="e2dd4-137">Le linee guida per i nomi dei campi si applicano ai campi statici pubblici e protetti.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-137">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="e2dd4-138">I campi interni e privati non sono descritti in queste linee guida, mentre i campi istanza pubblica o istanza protetta non sono consentiti dalle [linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md).</span><span class="sxs-lookup"><span data-stu-id="e2dd4-138">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>

 <span data-ttu-id="e2dd4-139">✔️ utilizzare sistema Pascal nei nomi dei campi.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-139">✔️ DO use PascalCasing in field names.</span></span>

 <span data-ttu-id="e2dd4-140">✔️ i campi nome usando un sostantivo, una frase nominale o un aggettivo.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-140">✔️ DO name fields using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="e2dd4-141">❌ non utilizzano un prefisso per i nomi dei campi.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-141">❌ DO NOT use a prefix for field names.</span></span>

 <span data-ttu-id="e2dd4-142">Ad esempio evitare di usare "g_" o "s _" per indicare i campi statici.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-142">For example, do not use "g_" or "s_" to indicate static fields.</span></span>

 <span data-ttu-id="e2dd4-143">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="e2dd4-143">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="e2dd4-144">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="e2dd4-144">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="e2dd4-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2dd4-145">See also</span></span>

- [<span data-ttu-id="e2dd4-146">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="e2dd4-146">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="e2dd4-147">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="e2dd4-147">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
