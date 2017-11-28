---
title: Nomi di classi, struct e interfacce
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a4f4b9e48587138f3e65c0c6825af0b3e4e8c592
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="c2c0f-102">Nomi di classi, struct e interfacce</span><span class="sxs-lookup"><span data-stu-id="c2c0f-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="c2c0f-103">Convenzioni di denominazione che seguono si applicano per la denominazione di tipo generale.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-103">The naming guidelines that follow apply to general type naming.</span></span>  
  
 <span data-ttu-id="c2c0f-104">**✓ SI** nome classi e struct con sostantivi o sintagmi nominali, utilizzando il sistema Pascal.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-104">**✓ DO** name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>  
  
 <span data-ttu-id="c2c0f-105">Consente di distinguere i nomi dei tipi di metodi, denominati con frasi di verbo.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>  
  
 <span data-ttu-id="c2c0f-106">**✓ SI** nome interfacce aggettivale frasi o occasionalmente con sostantivi o sintagmi nominali.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-106">**✓ DO** name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="c2c0f-107">Sostantivi e sintagmi nominali devono essere utilizzate raramente e potrebbero indicare che il tipo deve essere una classe astratta e non un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>  
  
 <span data-ttu-id="c2c0f-108">**X non** ai nomi delle classi di un prefisso (ad esempio, "C").</span><span class="sxs-lookup"><span data-stu-id="c2c0f-108">**X DO NOT** give class names a prefix (e.g., "C").</span></span>  
  
 <span data-ttu-id="c2c0f-109">**Provare a ✓** il nome della classe derivata con il nome della classe di base.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-109">**✓ CONSIDER** ending the name of derived classes with the name of the base class.</span></span>  
  
 <span data-ttu-id="c2c0f-110">Questo è molto leggibile e illustra chiaramente la relazione.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="c2c0f-111">Sono riportati alcuni esempi di questo codice: `ArgumentOutOfRangeException`, che è un tipo di `Exception`, e `SerializableAttribute`, che è un tipo di `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="c2c0f-112">Tuttavia, è importante utilizzare valutando questa linea guida; ad esempio, il `Button` classe è un tipo di `Control` evento, sebbene `Control` non viene visualizzato nel relativo nome.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>  
  
 <span data-ttu-id="c2c0f-113">**✓ SI** prefisso nei nomi di interfaccia con la lettera I, a indicare che il tipo è un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-113">**✓ DO** prefix interface names with the letter I, to indicate that the type is an interface.</span></span>  
  
 <span data-ttu-id="c2c0f-114">Ad esempio, `IComponent` (nome descrittivo), `ICustomAttributeProvider` (sintagma nominale) e `IPersistable` (aggettivo) sono nomi di interfaccia appropriata.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="c2c0f-115">Come con gli altri nomi di tipo, evitare di abbreviazioni.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-115">As with other type names, avoid abbreviations.</span></span>  
  
 <span data-ttu-id="c2c0f-116">**✓ SI** assicurarsi che i nomi differiscono solo per la "I" prefisso nel nome dell'interfaccia quando si definisce una coppia: interfaccia della classe in cui la classe è un'implementazione standard dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-116">**✓ DO** ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>  
  
## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="c2c0f-117">Nomi dei parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="c2c0f-117">Names of Generic Type Parameters</span></span>  
 <span data-ttu-id="c2c0f-118">I generics sono stati aggiunti a .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="c2c0f-119">La funzionalità introdotto un nuovo tipo di identificatore denominato *parametro di tipo*.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>  
  
 <span data-ttu-id="c2c0f-120">**✓ SI** denominare i parametri di tipo generico con nomi descrittivi a meno che non è completamente chiara di un nome di lettera singola e un nome descrittivo non aggiunge valore.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-120">**✓ DO** name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>  
  
 <span data-ttu-id="c2c0f-121">**Provare a ✓** utilizzando `T` come nome del parametro di tipo per tipi con un parametro di tipo lettera singola.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-121">**✓ CONSIDER** using `T` as the type parameter name for types with one single-letter type parameter.</span></span>  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 <span data-ttu-id="c2c0f-122">**✓ SI** i nomi dei parametri di tipo descrittivo con prefisso `T`.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-122">**✓ DO** prefix descriptive type parameter names with `T`.</span></span>  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 <span data-ttu-id="c2c0f-123">**Provare a ✓** che indica i vincoli posizionati su un parametro di tipo del nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-123">**✓ CONSIDER** indicating constraints placed on a type parameter in the name of the parameter.</span></span>  
  
 <span data-ttu-id="c2c0f-124">Ad esempio, un parametro vincolato a `ISession` potrebbe essere denominata `TSession`.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>  
  
## <a name="names-of-common-types"></a><span data-ttu-id="c2c0f-125">Nomi di tipi comuni</span><span class="sxs-lookup"><span data-stu-id="c2c0f-125">Names of Common Types</span></span>  
 <span data-ttu-id="c2c0f-126">**✓ SI** seguire le linee guida descritte nella tabella seguente per la denominazione di tipi derivati da o implementare determinati tipi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-126">**✓ DO** follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>  
  
|<span data-ttu-id="c2c0f-127">Base Type</span><span class="sxs-lookup"><span data-stu-id="c2c0f-127">Base Type</span></span>|<span data-ttu-id="c2c0f-128">Linee guida di tipo derivato implementazione</span><span class="sxs-lookup"><span data-stu-id="c2c0f-128">Derived/Implementing Type Guideline</span></span>|  
|---------------|------------------------------------------|  
|`System.Attribute`|<span data-ttu-id="c2c0f-129">**✓ SI** aggiungere il suffisso "Attribute" ai nomi delle classi di attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-129">**✓ DO** add the suffix "Attribute" to names of custom attribute classes.</span></span>|  
|`System.Delegate`|<span data-ttu-id="c2c0f-130">**✓ SI** aggiungere il suffisso "EventHandler" ai nomi dei delegati utilizzato negli eventi.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-130">**✓ DO** add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="c2c0f-131">**✓ SI** aggiungere il suffisso "Callback" ai nomi dei delegati diversi da quelli usati come gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-131">**✓ DO** add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="c2c0f-132">**X non** aggiungere il suffisso "Delegato" a un delegato.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-132">**X DO NOT** add the suffix "Delegate" to a delegate.</span></span>|  
|`System.EventArgs`|<span data-ttu-id="c2c0f-133">**✓ SI** aggiungere il suffisso "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="c2c0f-133">**✓ DO** add the suffix "EventArgs."</span></span>|  
|`System.Enum`|<span data-ttu-id="c2c0f-134">**X non** derivano da questa classe; usare la parola chiave supportata dal linguaggio di invece; ad esempio, in c#, utilizzare il `enum` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="c2c0f-134">**X DO NOT** derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="c2c0f-135">**X non** aggiungere il suffisso "Enum" o "Flag".</span><span class="sxs-lookup"><span data-stu-id="c2c0f-135">**X DO NOT** add the suffix "Enum" or "Flag."</span></span>|  
|`System.Exception`|<span data-ttu-id="c2c0f-136">**✓ SI** aggiungere il suffisso "Exception".</span><span class="sxs-lookup"><span data-stu-id="c2c0f-136">**✓ DO** add the suffix "Exception."</span></span>|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="c2c0f-137">**✓ SI** aggiungere il suffisso "Dizionario".</span><span class="sxs-lookup"><span data-stu-id="c2c0f-137">**✓ DO** add the suffix "Dictionary."</span></span> <span data-ttu-id="c2c0f-138">Si noti che `IDictionary` è un tipo specifico della raccolta, ma questa linea guida ha la precedenza su più generale delle linee guida di raccolte che segue.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="c2c0f-139">**✓ SI** aggiungere il suffisso "Collection".</span><span class="sxs-lookup"><span data-stu-id="c2c0f-139">**✓ DO** add the suffix "Collection."</span></span>|  
|`System.IO.Stream`|<span data-ttu-id="c2c0f-140">**✓ SI** aggiungere il suffisso "Stream".</span><span class="sxs-lookup"><span data-stu-id="c2c0f-140">**✓ DO** add the suffix "Stream."</span></span>|  
|`CodeAccessPermission IPermission`|<span data-ttu-id="c2c0f-141">**✓ SI** aggiungere il suffisso "Autorizzazioni".</span><span class="sxs-lookup"><span data-stu-id="c2c0f-141">**✓ DO** add the suffix "Permission."</span></span>|  
  
## <a name="naming-enumerations"></a><span data-ttu-id="c2c0f-142">Denominazione delle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="c2c0f-142">Naming Enumerations</span></span>  
 <span data-ttu-id="c2c0f-143">I nomi dei tipi di enumerazione (detti anche le enumerazioni) in genere devono seguire le regole denominazione di tipo standard (il sistema Pascal, ecc.).</span><span class="sxs-lookup"><span data-stu-id="c2c0f-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="c2c0f-144">Tuttavia, esistono linee guida aggiuntive specifiche per le enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-144">However, there are additional guidelines that apply specifically to enums.</span></span>  
  
 <span data-ttu-id="c2c0f-145">**✓ SI** utilizzare un nome di tipo singolare per un'enumerazione, a meno che i relativi valori sono i campi di bit.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-145">**✓ DO** use a singular type name for an enumeration unless its values are bit fields.</span></span>  
  
 <span data-ttu-id="c2c0f-146">**✓ SI** utilizzare un nome di tipo plurale per un'enumerazione con i campi di bit come valori, l'acronimo di enumerazione di flag.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-146">**✓ DO** use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>  
  
 <span data-ttu-id="c2c0f-147">**X non** utilizzare un suffisso "Enum" nei nomi di tipo enum.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-147">**X DO NOT** use an "Enum" suffix in enum type names.</span></span>  
  
 <span data-ttu-id="c2c0f-148">**X non** utilizzare "Flag" o nomi di tipo suffissi "Flags" nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-148">**X DO NOT** use "Flag" or "Flags" suffixes in enum type names.</span></span>  
  
 <span data-ttu-id="c2c0f-149">**X non** usare un prefisso ai nomi di valore di enumerazione (ad esempio, "ad" per le enumerazioni ADO.), "rtf" per le enumerazioni RTF e così via.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-149">**X DO NOT** use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>  
  
 <span data-ttu-id="c2c0f-150">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="c2c0f-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c2c0f-151">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c2c0f-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2c0f-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2c0f-152">See Also</span></span>  
 [<span data-ttu-id="c2c0f-153">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="c2c0f-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="c2c0f-154">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="c2c0f-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
