---
title: Nomi di classi, struct e interfacce
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727793"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="9bf62-102">Nomi di classi, struct e interfacce</span><span class="sxs-lookup"><span data-stu-id="9bf62-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="9bf62-103">Le linee guida per la denominazione che seguono si applicano alla denominazione generale dei tipi.</span><span class="sxs-lookup"><span data-stu-id="9bf62-103">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="9bf62-104">✔️ le classi nome e gli struct con sostantivi o frasi sostantive, usando sistema Pascal.</span><span class="sxs-lookup"><span data-stu-id="9bf62-104">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="9bf62-105">In questo modo i nomi dei tipi vengono distinti dai metodi, denominati con frasi del verbo.</span><span class="sxs-lookup"><span data-stu-id="9bf62-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="9bf62-106">✔️ le interfacce dei nomi con frasi aggettivali o occasionalmente con sostantivi o frasi sostantive.</span><span class="sxs-lookup"><span data-stu-id="9bf62-106">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="9bf62-107">I sostantivi e le frasi sostantivi devono essere usati raramente e potrebbero indicare che il tipo deve essere una classe astratta e non un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9bf62-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="9bf62-108">❌ non assegnano ai nomi di classe un prefisso (ad esempio, "C").</span><span class="sxs-lookup"><span data-stu-id="9bf62-108">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="9bf62-109">✔️ CONSIDERARE la fine del nome delle classi derivate con il nome della classe di base.</span><span class="sxs-lookup"><span data-stu-id="9bf62-109">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="9bf62-110">Questa operazione è molto leggibile e spiega chiaramente la relazione.</span><span class="sxs-lookup"><span data-stu-id="9bf62-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="9bf62-111">Alcuni esempi di questo codice sono: `ArgumentOutOfRangeException`, che è un tipo di `Exception`e `SerializableAttribute`, che è un tipo di `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="9bf62-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="9bf62-112">Tuttavia, è importante usare una ragionevole decisione nell'applicare questa linea guida; ad esempio, la classe `Button` è un tipo di evento di `Control`, anche se `Control` non viene visualizzato nel nome.</span><span class="sxs-lookup"><span data-stu-id="9bf62-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="9bf62-113">✔️ i nomi di interfaccia di prefisso con la lettera I, per indicare che il tipo è un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9bf62-113">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="9bf62-114">Ad esempio, `IComponent` (nome descrittivo), `ICustomAttributeProvider` (sintagma nominale) e `IPersistable` (aggettivo) sono nomi di interfaccia appropriati.</span><span class="sxs-lookup"><span data-stu-id="9bf62-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="9bf62-115">Come per gli altri nomi di tipo, evitare abbreviazioni.</span><span class="sxs-lookup"><span data-stu-id="9bf62-115">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="9bf62-116">✔️ Assicurarsi che i nomi si differenziano solo per il prefisso "I" sul nome dell'interfaccia quando si definisce una coppia classe-interfaccia in cui la classe è un'implementazione standard dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9bf62-116">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="9bf62-117">Nomi dei parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="9bf62-117">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="9bf62-118">I generics sono stati aggiunti a .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="9bf62-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="9bf62-119">La funzionalità ha introdotto un nuovo tipo di identificatore denominato *parametro di tipo*.</span><span class="sxs-lookup"><span data-stu-id="9bf62-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="9bf62-120">✔️ denominare parametri di tipo generico con nomi descrittivi, a meno che un nome di una sola lettera non sia completamente comprensibile e un nome descrittivo non aggiungerebbe valore.</span><span class="sxs-lookup"><span data-stu-id="9bf62-120">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="9bf62-121">✔️ CONSIGLIABILE usare `T` come nome del parametro di tipo per i tipi con un parametro di tipo a lettera singola.</span><span class="sxs-lookup"><span data-stu-id="9bf62-121">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="9bf62-122">✔️ i nomi di parametro di tipo descrittivo di prefisso con `T`.</span><span class="sxs-lookup"><span data-stu-id="9bf62-122">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="9bf62-123">✔️ considerare la possibilità di indicare i vincoli posizionati su un parametro di tipo nel nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="9bf62-123">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="9bf62-124">Ad esempio, un parametro vincolato a `ISession` potrebbe essere chiamato `TSession`.</span><span class="sxs-lookup"><span data-stu-id="9bf62-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="9bf62-125">Nomi dei tipi comuni</span><span class="sxs-lookup"><span data-stu-id="9bf62-125">Names of Common Types</span></span>
 <span data-ttu-id="9bf62-126">✔️ seguire le linee guida descritte nella tabella seguente per la denominazione dei tipi derivati da o per l'implementazione di determinati tipi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9bf62-126">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="9bf62-127">Tipo di base</span><span class="sxs-lookup"><span data-stu-id="9bf62-127">Base Type</span></span>|<span data-ttu-id="9bf62-128">Linee guida sul tipo derivato/di implementazione</span><span class="sxs-lookup"><span data-stu-id="9bf62-128">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="9bf62-129">✔️ aggiungere il suffisso "Attribute" ai nomi delle classi di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="9bf62-129">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="9bf62-130">✔️ aggiungere il suffisso "EventHandler" ai nomi dei delegati utilizzati negli eventi.</span><span class="sxs-lookup"><span data-stu-id="9bf62-130">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="9bf62-131">✔️ aggiungere il suffisso "callback" ai nomi di delegati diversi da quelli usati come gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="9bf62-131">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="9bf62-132">❌ non aggiungere il suffisso "delegate" a un delegato.</span><span class="sxs-lookup"><span data-stu-id="9bf62-132">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="9bf62-133">✔️ aggiungere il suffisso "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="9bf62-133">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="9bf62-134">❌ non derivano da questa classe; usare invece la parola chiave supportata dal linguaggio; in C#, ad esempio, usare la parola chiave `enum`.</span><span class="sxs-lookup"><span data-stu-id="9bf62-134">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="9bf62-135">❌ non aggiungere il suffisso "enum" o "flag".</span><span class="sxs-lookup"><span data-stu-id="9bf62-135">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="9bf62-136">✔️ aggiungere il suffisso "Exception".</span><span class="sxs-lookup"><span data-stu-id="9bf62-136">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="9bf62-137">✔️ aggiungere il suffisso "Dictionary".</span><span class="sxs-lookup"><span data-stu-id="9bf62-137">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="9bf62-138">Si noti che `IDictionary` è un tipo specifico di raccolta, ma questa guida ha la precedenza sulle linee guida più generali raccolte che seguono.</span><span class="sxs-lookup"><span data-stu-id="9bf62-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="9bf62-139">✔️ aggiungere il suffisso "Collection".</span><span class="sxs-lookup"><span data-stu-id="9bf62-139">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="9bf62-140">✔️ aggiungere il suffisso "Stream".</span><span class="sxs-lookup"><span data-stu-id="9bf62-140">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="9bf62-141">✔️ aggiungere il suffisso "permission".</span><span class="sxs-lookup"><span data-stu-id="9bf62-141">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="9bf62-142">Enumerazioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="9bf62-142">Naming Enumerations</span></span>
 <span data-ttu-id="9bf62-143">I nomi dei tipi di enumerazione (detti anche enum) in generale devono rispettare le regole di denominazione dei tipi standard (sistema Pascal e così via).</span><span class="sxs-lookup"><span data-stu-id="9bf62-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="9bf62-144">Tuttavia, esistono altre linee guida che si applicano in modo specifico alle enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="9bf62-144">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="9bf62-145">✔️ utilizzare un nome di tipo singolare per un'enumerazione, a meno che i relativi valori non siano campi di bit.</span><span class="sxs-lookup"><span data-stu-id="9bf62-145">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="9bf62-146">✔️ utilizzare un nome di tipo plurale per un'enumerazione con campi di bit come valori, denominati anche enumerazione Flags.</span><span class="sxs-lookup"><span data-stu-id="9bf62-146">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="9bf62-147">❌ non utilizzano un suffisso "enum" nei nomi di tipo enum.</span><span class="sxs-lookup"><span data-stu-id="9bf62-147">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="9bf62-148">❌ non utilizzare suffissi "flag" o "flag" nei nomi dei tipi enum.</span><span class="sxs-lookup"><span data-stu-id="9bf62-148">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="9bf62-149">❌ non utilizzano un prefisso per i nomi dei valori di enumerazione (ad esempio, "ad" per le enumerazioni ADO, "RTF" per le enumerazioni di testo RTF e così via).</span><span class="sxs-lookup"><span data-stu-id="9bf62-149">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="9bf62-150">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="9bf62-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="9bf62-151">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="9bf62-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="9bf62-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bf62-152">See also</span></span>

- [<span data-ttu-id="9bf62-153">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="9bf62-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="9bf62-154">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="9bf62-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
