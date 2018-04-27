---
title: Nomi di membri dei tipi
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6584eecb2df652f12fd14710bb5f15933aead541
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="names-of-type-members"></a><span data-ttu-id="c3cd7-102">Nomi di membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="c3cd7-102">Names of Type Members</span></span>
<span data-ttu-id="c3cd7-103">I tipi sono costituiti da membri: metodi, proprietà, eventi, costruttori e campi.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="c3cd7-104">Le sezioni seguenti descrivono le linee guida per la denominazione dei membri di tipo.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="c3cd7-105">Nomi dei metodi</span><span class="sxs-lookup"><span data-stu-id="c3cd7-105">Names of Methods</span></span>  
 <span data-ttu-id="c3cd7-106">Poiché i metodi sono il mezzo di un'azione intrapresa, linee guida di progettazione richiedono che i nomi di metodo verbi o frasi di verbo.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="c3cd7-107">Di queste indicazioni inoltre viene usato per distinguere i nomi di metodo da nomi di proprietà e il tipo, ovvero sostantivo o aggettivo frasi.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="c3cd7-108">**✓ SI** fornire metodi i nomi di verbi o frasi verbo.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="c3cd7-109">Nomi delle proprietà</span><span class="sxs-lookup"><span data-stu-id="c3cd7-109">Names of Properties</span></span>  
 <span data-ttu-id="c3cd7-110">A differenza di altri membri, è necessario assegnare proprietà sintagma nominale o nomi aggettivali.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="c3cd7-111">Ciò avviene perché una proprietà fa riferimento a dati e il nome della proprietà corrisponde a quello.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="c3cd7-112">Il sistema Pascal viene sempre utilizzato per i nomi delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="c3cd7-113">**✓ SI** nome proprietà tramite un sostantivo, sintagmi nominali o aggettivo.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="c3cd7-114">**X non** dispongono di proprietà che corrispondono al nome dei metodi "Get" come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c3cd7-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="c3cd7-115">Questo modello è in genere indica che la proprietà deve essere effettivamente un metodo.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="c3cd7-116">**✓ SI** nome proprietà della raccolta con una plurale frase che descrive gli elementi nella raccolta invece di usare una frase singola seguita da "List" o "Collection".</span><span class="sxs-lookup"><span data-stu-id="c3cd7-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="c3cd7-117">**✓ SI** nome di proprietà booleane con una frase affermativa (`CanSeek` anziché `CantSeek`).</span><span class="sxs-lookup"><span data-stu-id="c3cd7-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="c3cd7-118">Facoltativamente, è possibile anteporre anche le proprietà booleane con "Is", "può" o "Include" ma solo se aggiunge valore.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="c3cd7-119">**✓ Provare a** assegnare lo stesso nome di tipo a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="c3cd7-120">Ad esempio, la proprietà seguente correttamente viene impostato un valore di enumerazione denominato `Color`, pertanto la proprietà è denominata `Color`:</span><span class="sxs-lookup"><span data-stu-id="c3cd7-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="c3cd7-121">Nomi degli eventi</span><span class="sxs-lookup"><span data-stu-id="c3cd7-121">Names of Events</span></span>  
 <span data-ttu-id="c3cd7-122">Gli eventi si riferiscono sempre a un'azione, un problema o che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="c3cd7-123">Pertanto, come con i metodi, eventi sono denominati con i verbi e al tempo di verbi viene utilizzato per indicare l'ora quando viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="c3cd7-124">**✓ SI** denominare eventi con un verbo o una frase di verbo.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="c3cd7-125">Gli esempi includono `Clicked`, `Painting`, `DroppedDown`e così via.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="c3cd7-126">**✓ SI** assegnare un nome di eventi con un concetto di prima e dopo, utilizzando il presente e tempi e coniugazioni passato.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="c3cd7-127">Ad esempio, un evento di chiusura che viene generato prima della chiusura di una finestra deve essere chiamato `Closing`, e uno che viene generato dopo la chiusura di finestra deve essere chiamato `Closed`.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="c3cd7-128">**X non** utilizzare "Before" o "After" prefissi o suffissi per indicare pre- e post-eventi.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="c3cd7-129">Usare presente e passato tempi come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="c3cd7-130">**✓ SI** denominare i gestori di eventi (delegati utilizzati come tipi di eventi) con il suffisso "EventHandler", come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c3cd7-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="c3cd7-131">**✓ SI** utilizzare due parametri denominati `sender` e `e` nei gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="c3cd7-132">Il parametro mittente rappresenta l'oggetto che ha generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="c3cd7-133">Il parametro mittente è in genere di tipo `object`, anche se è possibile utilizzare un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="c3cd7-134">**✓ SI** nome evento classi di argomenti con il suffisso "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="c3cd7-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="c3cd7-135">Nomi dei campi</span><span class="sxs-lookup"><span data-stu-id="c3cd7-135">Names of Fields</span></span>  
 <span data-ttu-id="c3cd7-136">Le convenzioni di denominazione per campo si applicano ai campi statici pubblici e protetti.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="c3cd7-137">I campi interni e privati non coperti dalle linee guida e i campi di istanza pubblici o protetti non sono consentiti dal [indicazioni per la progettazione di membro](../../../docs/standard/design-guidelines/member.md).</span><span class="sxs-lookup"><span data-stu-id="c3cd7-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="c3cd7-138">**✓ SI** utilizzare il sistema Pascal nei nomi di campo.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="c3cd7-139">**✓ SI** nome campi utilizzando un sostantivo, sintagmi nominali o aggettivo.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="c3cd7-140">**X non** usare un prefisso per i nomi dei campi.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="c3cd7-141">Ad esempio, non utilizzare "g _" o "s _" per indicare i campi statici.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="c3cd7-142">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="c3cd7-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c3cd7-143">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c3cd7-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3cd7-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3cd7-144">See Also</span></span>  
 [<span data-ttu-id="c3cd7-145">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="c3cd7-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="c3cd7-146">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="c3cd7-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
