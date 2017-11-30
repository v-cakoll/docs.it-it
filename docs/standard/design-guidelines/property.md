---
title: "Progettazione di proprietà"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 477b3b69ce1b8a3bb160e8e120885239e3d99e56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="property-design"></a><span data-ttu-id="b8fb9-102">Progettazione di proprietà</span><span class="sxs-lookup"><span data-stu-id="b8fb9-102">Property Design</span></span>
<span data-ttu-id="b8fb9-103">Anche se tecnicamente molto simile ai metodi, proprietà sono diversi in termini relativi scenari di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="b8fb9-104">Si dovrebbero essere considerate come campi intelligenti.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-104">They should be seen as smart fields.</span></span> <span data-ttu-id="b8fb9-105">Hanno la sintassi per la chiamata di campi e la flessibilità dei metodi.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="b8fb9-106">**✓ SI** creare le proprietà di sola lettura se il chiamante non deve essere in grado di modificare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="b8fb9-107">Tenere presente che se il tipo di proprietà è un tipo di riferimento modificabile, il valore della proprietà può essere modificato anche se la proprietà solo get.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="b8fb9-108">**X non** fornire solo set di proprietà o il setter con accessibilità più ampia rispetto al metodo Get.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="b8fb9-109">Ad esempio, non utilizzare proprietà con un setter pubblico e un metodo di richiamo protetto.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="b8fb9-110">Se il metodo Get della proprietà non può essere fornito, è possibile implementare la funzionalità di un metodo.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="b8fb9-111">È consigliabile iniziare con il nome del metodo `Set` e seguire con ciò che si avrebbero denominato la proprietà.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="b8fb9-112">Ad esempio, <xref:System.AppDomain> ha un metodo denominato `SetCachePath` anziché una set di proprietà di sola `CachePath`.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="b8fb9-113">**✓ SI** fornire valori predefiniti appropriati per tutte le proprietà, assicurandosi che le impostazioni predefinite non comportano un problema di sicurezza o di codice particolarmente inefficiente.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="b8fb9-114">**✓ SI** consente di proprietà da impostare in qualsiasi ordine, anche se il risultato è un stato temporaneo non valido dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="b8fb9-115">È comune per due o più delle proprietà correlate a un punto in cui alcuni valori di una proprietà potrebbero essere non validi in base ai valori di altre proprietà sull'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="b8fb9-116">In questi casi, le eccezioni derivanti da stato non valido devono essere rinviate fino a quando le proprietà correlate vengono effettivamente utilizzate insieme dall'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="b8fb9-117">**✓ SI** mantenere il valore precedente, se un setter di proprietà genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="b8fb9-118">**X evitare** la generazione di eccezioni da metodi get di proprietà.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="b8fb9-119">Metodi get di proprietà devono essere operazioni semplici e non deve avere le precondizioni.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="b8fb9-120">Se un metodo Get può generare un'eccezione, deve probabilmente riprogettato per essere un metodo.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="b8fb9-121">Si noti che questa regola viene applicata per gli indicizzatori, in cui è prevista eccezioni come risultato di convalida gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="b8fb9-122">Progettazione di proprietà indicizzate</span><span class="sxs-lookup"><span data-stu-id="b8fb9-122">Indexed Property Design</span></span>  
 <span data-ttu-id="b8fb9-123">Una proprietà indicizzata è una proprietà speciale che può avere parametri e può essere chiamata con una sintassi speciale simile all'indicizzazione di matrice.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="b8fb9-124">Proprietà indicizzate sono conosciute come gli indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="b8fb9-125">Gli indicizzatori devono essere utilizzati solo nelle API che forniscono l'accesso agli elementi in una raccolta logica.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="b8fb9-126">Ad esempio, una stringa è un insieme di caratteri e l'indicizzatore in <xref:System.String?displayProperty=nameWithType> è stato aggiunto per accedere ai relativi caratteri.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="b8fb9-127">**Provare a ✓** utilizzo degli indicizzatori per fornire l'accesso ai dati archiviati in una matrice interna.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="b8fb9-128">**Provare a ✓** fornendo gli indicizzatori in tipi che rappresentano raccolte di elementi.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="b8fb9-129">**X evitare** utilizzando proprietà con più di un parametro indicizzate.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="b8fb9-130">Se la progettazione richiede più parametri, verificare che la proprietà rappresenta una funzione di accesso a un insieme logico.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="b8fb9-131">In caso contrario, è possibile utilizzare metodi.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-131">If it does not, use methods instead.</span></span> <span data-ttu-id="b8fb9-132">È consigliabile iniziare con il nome del metodo `Get` o `Set`.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="b8fb9-133">**X evitare** indicizzatori con tipi di parametro diverso da <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, o un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="b8fb9-134">Se il progetto richiede altri tipi di parametri, rivalutare se l'API rappresenta una funzione di accesso a un insieme logico.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="b8fb9-135">In caso contrario, utilizzare un metodo.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-135">If it does not, use a method.</span></span> <span data-ttu-id="b8fb9-136">È consigliabile iniziare con il nome del metodo `Get` o `Set`.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="b8fb9-137">**✓ SI** utilizzare il nome `Item` per le proprietà indicizzate, a meno che non è un nome chiaramente più (ad esempio, vedere il <xref:System.String.Chars%2A> proprietà `System.String`).</span><span class="sxs-lookup"><span data-stu-id="b8fb9-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="b8fb9-138">In c#, gli indicizzatori sono per impostazione predefinita l'elemento denominato.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="b8fb9-139">Il <xref:System.Runtime.CompilerServices.IndexerNameAttribute> può essere utilizzato per personalizzare questo nome.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="b8fb9-140">**X non** fornire sia un indicizzatore e i metodi sono semanticamente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="b8fb9-141">**X non** fornire più di una famiglia di indicizzatori overload in un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="b8fb9-142">Questo viene applicato dal compilatore c#.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="b8fb9-143">**X non** non predefinite utilizzare proprietà indicizzate.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="b8fb9-144">Questo viene applicato dal compilatore c#.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="b8fb9-145">Eventi di notifica di modifica di proprietà</span><span class="sxs-lookup"><span data-stu-id="b8fb9-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="b8fb9-146">Talvolta è utile fornire un evento di notificare all'utente di modifiche in un valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="b8fb9-147">Ad esempio, `System.Windows.Forms.Control` genera un `TextChanged` eventi quando il valore della relativa `Text` proprietà è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="b8fb9-148">**Provare a ✓** generato modificare eventi di notifica quando vengono modificati i valori delle proprietà generale per le API (in genere della finestra di progettazione componenti).</span><span class="sxs-lookup"><span data-stu-id="b8fb9-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="b8fb9-149">Se è presente uno scenario ottimo per un utente di conoscere quando si modifica una proprietà di un oggetto, l'oggetto deve generare un evento di notifica di modifica per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="b8fb9-150">Tuttavia, non viene in genere valere la pena l'overhead per generare tali eventi per le API di basso livello, ad esempio tipi di base o raccolte.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="b8fb9-151">Ad esempio, <xref:System.Collections.Generic.List%601> potrebbe non generare tali eventi quando un nuovo elemento viene aggiunto all'elenco e `Count` le modifiche alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="b8fb9-152">**Provare a ✓** generato modificare eventi di notifica quando cambia il valore di una proprietà tramite forze esterne.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="b8fb9-153">Se un valore della proprietà viene modificata tramite alcuni forza esterna (in modo diverso da chiamando i metodi per l'oggetto), generare gli eventi indicano allo sviluppatore che il valore in fase di modifica e che è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="b8fb9-154">Un buon esempio è la `Text` proprietà di un controllo casella di testo.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="b8fb9-155">Quando l'utente digita il testo in un `TextBox`, viene automaticamente modificato il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b8fb9-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="b8fb9-156">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="b8fb9-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b8fb9-157">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="b8fb9-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8fb9-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8fb9-158">See Also</span></span>  
 [<span data-ttu-id="b8fb9-159">Linee guida di progettazione di membro</span><span class="sxs-lookup"><span data-stu-id="b8fb9-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="b8fb9-160">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="b8fb9-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
