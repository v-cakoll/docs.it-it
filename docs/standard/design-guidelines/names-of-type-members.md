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
author: KrzysztofCwalina
ms.openlocfilehash: 264627f49a3d2a083f8f46f23f71e8b34d042c8e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127576"
---
# <a name="names-of-type-members"></a><span data-ttu-id="867fa-102">Nomi di membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="867fa-102">Names of Type Members</span></span>
<span data-ttu-id="867fa-103">I tipi sono costituiti da membri: metodi, proprietà, eventi, costruttori e campi.</span><span class="sxs-lookup"><span data-stu-id="867fa-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="867fa-104">Le sezioni seguenti illustrano le linee guida per assegnare nomi ai membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="867fa-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="867fa-105">Nomi dei metodi</span><span class="sxs-lookup"><span data-stu-id="867fa-105">Names of Methods</span></span>  
 <span data-ttu-id="867fa-106">I metodi sono il mezzo per l'esecuzione delle azioni. Pertanto le linee guida di progettazione richiedono che i nomi dei metodi siano verbi o frasi verbali.</span><span class="sxs-lookup"><span data-stu-id="867fa-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="867fa-107">L'osservazione di questa linea guida è anche utile per distinguere i nomi dei metodi dai nomi delle proprietà e dei tipi, che sono frasi nominali o aggettivali.</span><span class="sxs-lookup"><span data-stu-id="867fa-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="867fa-108">**✓ DO** Assegnare ai metodi nomi corrispondenti a verbi o frasi verbali.</span><span class="sxs-lookup"><span data-stu-id="867fa-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="867fa-109">Nomi delle proprietà</span><span class="sxs-lookup"><span data-stu-id="867fa-109">Names of Properties</span></span>  
 <span data-ttu-id="867fa-110">A differenza degli altri membri, è necessario assegnare alle proprietà sintagmi nominali o nomi aggettivali.</span><span class="sxs-lookup"><span data-stu-id="867fa-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="867fa-111">Il motivo è che una proprietà fa riferimento ai dati e il nome della proprietà deve riflettere questo fatto.</span><span class="sxs-lookup"><span data-stu-id="867fa-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="867fa-112">Per i nomi delle proprietà viene sempre usata la notazione Pascal.</span><span class="sxs-lookup"><span data-stu-id="867fa-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="867fa-113">**✓ DO** Denominare le proprietà con un sostantivo, un sintagma nominale o un aggettivo.</span><span class="sxs-lookup"><span data-stu-id="867fa-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="867fa-114">**X DO NOT** Definire proprietà il cui nome corrisponde a quello dei metodi "Get", come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="867fa-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="867fa-115">Questo criterio in genere indica che la proprietà dovrebbe di fatto essere un metodo.</span><span class="sxs-lookup"><span data-stu-id="867fa-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="867fa-116">**✓ DO** Assegnare alle proprietà raccolta una frase plurale che descrive gli elementi nella raccolta, anziché usare una frase singolare seguita da "List" o "Collection".</span><span class="sxs-lookup"><span data-stu-id="867fa-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="867fa-117">**✓ DO** Assegnare alle proprietà booleane una frase affermativa (`CanSeek` invece di `CantSeek`).</span><span class="sxs-lookup"><span data-stu-id="867fa-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="867fa-118">È anche possibile fare iniziare le proprietà booleane con "Is", "Can" o "Has", ma solo se si aggiunge valore.</span><span class="sxs-lookup"><span data-stu-id="867fa-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="867fa-119">**✓ CONSIDER** Assegnare a una proprietà lo stesso nome del tipo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="867fa-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="867fa-120">Ad esempio, la proprietà seguente ottiene e imposta correttamente un valore di enumerazione denominato `Color`, pertanto è denominata `Color`:</span><span class="sxs-lookup"><span data-stu-id="867fa-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="867fa-121">Nomi degli eventi</span><span class="sxs-lookup"><span data-stu-id="867fa-121">Names of Events</span></span>  
 <span data-ttu-id="867fa-122">Gli eventi fanno sempre riferimento a un'azione, che può essere in corso o già terminata.</span><span class="sxs-lookup"><span data-stu-id="867fa-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="867fa-123">Pertanto, come nel caso dei metodi, i nomi degli eventi devono essere verbi e il tempo verbale indica il momento in cui viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="867fa-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="867fa-124">**✓ DO** Assegnare agli eventi nomi corrispondenti a verbi o frasi verbali.</span><span class="sxs-lookup"><span data-stu-id="867fa-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="867fa-125">Alcuni esempi sono `Clicked`, `Painting` o `DroppedDown`.</span><span class="sxs-lookup"><span data-stu-id="867fa-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="867fa-126">**✓ DO** Assegnare agli eventi nomi che includano il concetto di prima e dopo, usando il presente e il passato.</span><span class="sxs-lookup"><span data-stu-id="867fa-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="867fa-127">Ad esempio, un evento di chiusura generato prima della chiusura di una finestra può essere chiamato `Closing`, mentre uno generato dopo la chiusura della finestra può essere chiamato `Closed`.</span><span class="sxs-lookup"><span data-stu-id="867fa-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="867fa-128">**X DO NOT** Usare prefissi o suffissi "Before" o "After" per indicare eventi precedenti o successivi ad altri elementi.</span><span class="sxs-lookup"><span data-stu-id="867fa-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="867fa-129">Usare il presente e il passato come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="867fa-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="867fa-130">**✓ DO** Assegnare ai gestori dell'evento (delegati usati come tipi di eventi) il suffisso "EventHandler", come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="867fa-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="867fa-131">**✓ DO** Usare due parametri denominati `sender` e `e` nei gestori dell'evento.</span><span class="sxs-lookup"><span data-stu-id="867fa-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="867fa-132">Il parametro sender rappresenta l'oggetto che ha generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="867fa-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="867fa-133">Il parametro sender è in genere di tipo `object`, anche se è possibile usare un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="867fa-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="867fa-134">**✓ DO** Denominare le classi di argomenti dell'evento con il suffisso "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="867fa-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="867fa-135">Nomi dei campi</span><span class="sxs-lookup"><span data-stu-id="867fa-135">Names of Fields</span></span>  
 <span data-ttu-id="867fa-136">Le linee guida per i nomi dei campi si applicano ai campi statici pubblici e protetti.</span><span class="sxs-lookup"><span data-stu-id="867fa-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="867fa-137">I campi interni e privati non sono descritti in queste linee guida, mentre i campi istanza pubblica o istanza protetta non sono consentiti dalle [linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md).</span><span class="sxs-lookup"><span data-stu-id="867fa-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="867fa-138">**✓ DO** Usare la notazione Pascal nei nomi dei campi.</span><span class="sxs-lookup"><span data-stu-id="867fa-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="867fa-139">**✓ DO** Denominare i campi con un sostantivo, un sintagma nominale o un aggettivo.</span><span class="sxs-lookup"><span data-stu-id="867fa-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="867fa-140">**X DO NOT** Usare un prefisso per i nomi dei campi.</span><span class="sxs-lookup"><span data-stu-id="867fa-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="867fa-141">Ad esempio evitare di usare "g_" o "s _" per indicare i campi statici.</span><span class="sxs-lookup"><span data-stu-id="867fa-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="867fa-142">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="867fa-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="867fa-143">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="867fa-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="867fa-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="867fa-144">See also</span></span>

- [<span data-ttu-id="867fa-145">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="867fa-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="867fa-146">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="867fa-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
