---
title: Nomi di classi, struct e interfacce
description: Usare queste linee guida per rinominare classi, struct e interfacce come parte delle linee guida per la progettazione di librerie che estendono e interagiscono con le librerie .NET.
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
ms.openlocfilehash: e7eee414c5bf5c69f63543ef240e50a4d2d948a3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419083"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="4a878-103">Nomi di classi, struct e interfacce</span><span class="sxs-lookup"><span data-stu-id="4a878-103">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="4a878-104">Le linee guida per la denominazione che seguono si applicano alla denominazione generale dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4a878-104">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="4a878-105">✔️ le classi nome e gli struct con sostantivi o frasi sostantive, usando sistema Pascal.</span><span class="sxs-lookup"><span data-stu-id="4a878-105">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="4a878-106">In questo modo i nomi dei tipi vengono distinti dai metodi, denominati con frasi del verbo.</span><span class="sxs-lookup"><span data-stu-id="4a878-106">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="4a878-107">✔️ le interfacce dei nomi con frasi aggettivali o occasionalmente con sostantivi o frasi sostantive.</span><span class="sxs-lookup"><span data-stu-id="4a878-107">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="4a878-108">I sostantivi e le frasi sostantivi devono essere usati raramente e potrebbero indicare che il tipo deve essere una classe astratta e non un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4a878-108">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="4a878-109">❌NON assegnare al nome della classe un prefisso (ad esempio, "C").</span><span class="sxs-lookup"><span data-stu-id="4a878-109">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="4a878-110">✔️ CONSIDERARE la fine del nome delle classi derivate con il nome della classe di base.</span><span class="sxs-lookup"><span data-stu-id="4a878-110">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="4a878-111">Questa operazione è molto leggibile e spiega chiaramente la relazione.</span><span class="sxs-lookup"><span data-stu-id="4a878-111">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="4a878-112">Alcuni esempi di questo codice sono: `ArgumentOutOfRangeException` , che è un tipo di `Exception` , e `SerializableAttribute` , che è un tipo di `Attribute` .</span><span class="sxs-lookup"><span data-stu-id="4a878-112">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="4a878-113">Tuttavia, è importante usare una ragionevole decisione nell'applicare questa linea guida; ad esempio, la `Button` classe è un tipo di `Control` evento, sebbene `Control` non sia presente nel nome.</span><span class="sxs-lookup"><span data-stu-id="4a878-113">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="4a878-114">✔️ i nomi di interfaccia di prefisso con la lettera I, per indicare che il tipo è un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4a878-114">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="4a878-115">Ad esempio, ( `IComponent` sostantivo descrittivo), `ICustomAttributeProvider` (sintagma sostantivo) e `IPersistable` (aggettivo) sono nomi di interfaccia appropriati.</span><span class="sxs-lookup"><span data-stu-id="4a878-115">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="4a878-116">Come per gli altri nomi di tipo, evitare abbreviazioni.</span><span class="sxs-lookup"><span data-stu-id="4a878-116">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="4a878-117">✔️ Assicurarsi che i nomi si differenziano solo per il prefisso "I" sul nome dell'interfaccia quando si definisce una coppia classe-interfaccia in cui la classe è un'implementazione standard dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4a878-117">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="4a878-118">Nomi dei parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="4a878-118">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="4a878-119">I generics sono stati aggiunti a .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="4a878-119">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="4a878-120">La funzionalità ha introdotto un nuovo tipo di identificatore denominato *parametro di tipo*.</span><span class="sxs-lookup"><span data-stu-id="4a878-120">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="4a878-121">✔️ denominare parametri di tipo generico con nomi descrittivi, a meno che un nome di una sola lettera non sia completamente comprensibile e un nome descrittivo non aggiungerebbe valore.</span><span class="sxs-lookup"><span data-stu-id="4a878-121">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="4a878-122">✔️ CONSIGLIABILE utilizzare `T` come nome del parametro di tipo per i tipi con un parametro di tipo a lettera singola.</span><span class="sxs-lookup"><span data-stu-id="4a878-122">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="4a878-123">✔️ i nomi di parametro di tipo descrittivo con `T` .</span><span class="sxs-lookup"><span data-stu-id="4a878-123">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="4a878-124">✔️ considerare la possibilità di indicare i vincoli posizionati su un parametro di tipo nel nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="4a878-124">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="4a878-125">Ad esempio, è possibile chiamare un parametro vincolato a `ISession` `TSession` .</span><span class="sxs-lookup"><span data-stu-id="4a878-125">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="4a878-126">Nomi dei tipi comuni</span><span class="sxs-lookup"><span data-stu-id="4a878-126">Names of Common Types</span></span>
 <span data-ttu-id="4a878-127">✔️ seguire le linee guida descritte nella tabella seguente per la denominazione dei tipi derivati da o per l'implementazione di determinati tipi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a878-127">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="4a878-128">Base Type</span><span class="sxs-lookup"><span data-stu-id="4a878-128">Base Type</span></span>|<span data-ttu-id="4a878-129">Linee guida sul tipo derivato/di implementazione</span><span class="sxs-lookup"><span data-stu-id="4a878-129">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="4a878-130">✔️ aggiungere il suffisso "Attribute" ai nomi delle classi di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4a878-130">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="4a878-131">✔️ aggiungere il suffisso "EventHandler" ai nomi dei delegati utilizzati negli eventi.</span><span class="sxs-lookup"><span data-stu-id="4a878-131">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="4a878-132">✔️ aggiungere il suffisso "callback" ai nomi di delegati diversi da quelli usati come gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="4a878-132">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="4a878-133">❌NON aggiungere il suffisso "delegate" a un delegato.</span><span class="sxs-lookup"><span data-stu-id="4a878-133">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="4a878-134">✔️ aggiungere il suffisso "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="4a878-134">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="4a878-135">❌NON derivare da questa classe; usare invece la parola chiave supportata dal linguaggio; in C#, ad esempio, usare la `enum` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="4a878-135">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="4a878-136">❌Non aggiungere il suffisso "enum" o "flag".</span><span class="sxs-lookup"><span data-stu-id="4a878-136">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="4a878-137">✔️ aggiungere il suffisso "Exception".</span><span class="sxs-lookup"><span data-stu-id="4a878-137">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="4a878-138">✔️ aggiungere il suffisso "Dictionary".</span><span class="sxs-lookup"><span data-stu-id="4a878-138">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="4a878-139">Si noti che `IDictionary` è un tipo specifico di raccolta, ma questa linea guida ha la precedenza rispetto alle linee guida per le raccolte più generali riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="4a878-139">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="4a878-140">✔️ aggiungere il suffisso "Collection".</span><span class="sxs-lookup"><span data-stu-id="4a878-140">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="4a878-141">✔️ aggiungere il suffisso "Stream".</span><span class="sxs-lookup"><span data-stu-id="4a878-141">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="4a878-142">✔️ aggiungere il suffisso "permission".</span><span class="sxs-lookup"><span data-stu-id="4a878-142">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="4a878-143">Enumerazioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="4a878-143">Naming Enumerations</span></span>
 <span data-ttu-id="4a878-144">I nomi dei tipi di enumerazione (detti anche enum) in generale devono rispettare le regole di denominazione dei tipi standard (sistema Pascal e così via).</span><span class="sxs-lookup"><span data-stu-id="4a878-144">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="4a878-145">Tuttavia, esistono altre linee guida che si applicano in modo specifico alle enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="4a878-145">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="4a878-146">✔️ utilizzare un nome di tipo singolare per un'enumerazione, a meno che i relativi valori non siano campi di bit.</span><span class="sxs-lookup"><span data-stu-id="4a878-146">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="4a878-147">✔️ utilizzare un nome di tipo plurale per un'enumerazione con campi di bit come valori, denominati anche enumerazione Flags.</span><span class="sxs-lookup"><span data-stu-id="4a878-147">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="4a878-148">❌Non usare un suffisso "enum" nei nomi di tipo enum.</span><span class="sxs-lookup"><span data-stu-id="4a878-148">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="4a878-149">❌Non usare suffissi "flag" o "Flags" nei nomi di tipo enum.</span><span class="sxs-lookup"><span data-stu-id="4a878-149">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="4a878-150">❌Non usare un prefisso per i nomi dei valori di enumerazione (ad esempio, "ad" per le enumerazioni ADO, "RTF" per le enumerazioni di testo RTF e così via).</span><span class="sxs-lookup"><span data-stu-id="4a878-150">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="4a878-151">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="4a878-151">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4a878-152">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4a878-152">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4a878-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a878-153">See also</span></span>

- [<span data-ttu-id="4a878-154">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="4a878-154">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="4a878-155">Linee guida per la denominazione</span><span class="sxs-lookup"><span data-stu-id="4a878-155">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
