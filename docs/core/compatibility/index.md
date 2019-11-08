---
title: Valutare le modifiche che causano un'interruzione - .NET Core
description: Informazioni sui modi in cui .NET Core tenta di garantire la compatibilità tra le versioni di .NET per sviluppatori.
ms.date: 06/10/2019
ms.openlocfilehash: f4e18a17f58452c9325f36390626ae690f5ed777
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739344"
---
# <a name="evaluate-breaking-changes-in-net-core"></a><span data-ttu-id="ec03d-103">Valutare le modifiche che causano un'interruzione</span><span class="sxs-lookup"><span data-stu-id="ec03d-103">Evaluate breaking changes in .NET Core</span></span>

<span data-ttu-id="ec03d-104">Nel corso del tempo, .NET ha tentato di mantenere un elevato livello di compatibilità tra le diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="ec03d-104">Throughout its history, .NET has attempted to maintain a high level of compatibility from version to version and across flavors of .NET.</span></span> <span data-ttu-id="ec03d-105">Questo è vero anche per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ec03d-105">This continues to be true for .NET Core.</span></span> <span data-ttu-id="ec03d-106">Anche se la tecnologia .NET Core può essere considerata indipendente da .NET Framework, due fattori principali limitano la possibilità di .NET Core di discostarsi da .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ec03d-106">Although .NET Core can be considered as a new technology that is independent of the .NET Framework, two major factors limit the ability of .NET Core to diverge from .NET Framework:</span></span>

- <span data-ttu-id="ec03d-107">Numerosi sviluppatori hanno originariamente sviluppato o continuano a sviluppare applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ec03d-107">A large number of developers either originally developed or continue to develop .NET Framework applications.</span></span> <span data-ttu-id="ec03d-108">e si aspettano un comportamento coerente in tutte le implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="ec03d-108">They expect consistent behavior across .NET implementations.</span></span>

- <span data-ttu-id="ec03d-109">I progetti di libreria .NET Standard consentono agli sviluppatori di creare librerie per API comuni condivise da .NET Core e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ec03d-109">.NET Standard library projects allow developers to create libraries that target common APIs shared by .NET Core and .NET Framework.</span></span> <span data-ttu-id="ec03d-110">Gli sviluppatori si aspettano che una libreria usata in un'applicazione .NET Core debba comportarsi in modo identico alla stessa libreria usata in un'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ec03d-110">Developers expect that a library used in a .NET Core application should behave identically to the same library used in a .NET Framework application.</span></span>

<span data-ttu-id="ec03d-111">Oltre alla compatibilità tra le implementazioni di .NET, gli sviluppatori si aspettano un elevato livello di compatibilità tra le versioni di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ec03d-111">Along with compatibility across .NET implementations, developers expect a high level of compatibility across .NET Core versions.</span></span> <span data-ttu-id="ec03d-112">In particolare, il codice scritto per una versione precedente di .NET Core dovrebbe essere eseguito senza problemi in una versione successiva di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ec03d-112">In particular, code written for an earlier version of .NET Core should run seamlessly on a later version of .NET Core.</span></span> <span data-ttu-id="ec03d-113">In realtà, molti gli sviluppatori si aspettano che le nuove API incluse nelle nuove versioni rilasciate di .NET Core siano compatibili anche con le versioni non definitive in cui sono state introdotte le API.</span><span class="sxs-lookup"><span data-stu-id="ec03d-113">In fact, many developers expect that the new APIs found in newly released versions of .NET Core should also be compatible with the pre-release versions in which those APIs were introduced.</span></span>

<span data-ttu-id="ec03d-114">Questo articolo descrive le categorie di modifiche di compatibilità (o che causano un'interruzione) e il modo in cui le modifiche di ogni categoria vengono valutate dal team di .NET.</span><span class="sxs-lookup"><span data-stu-id="ec03d-114">This article outlines the categories of compatibility changes (or breaking changes) and the way in which the .NET team evaluates changes in each of these categories.</span></span> <span data-ttu-id="ec03d-115">Le informazioni sull'approccio del team di .NET alle possibili modifiche che causano un'interruzione sono particolarmente utili per gli sviluppatori che aprono richieste pull nel repository [dotnet/corefx](https://github.com/dotnet/corefx) di GitHub per modificare il comportamento di API esistenti.</span><span class="sxs-lookup"><span data-stu-id="ec03d-115">Understanding how the .NET team approaches possible breaking changes is particularly helpful for developers who are opening pull requests in the [dotnet/corefx](https://github.com/dotnet/corefx) GitHub repository that modify the behavior of existing APIs.</span></span>

> [!NOTE]
> <span data-ttu-id="ec03d-116">Per una definizione delle categorie di compatibilità, come la compatibilità a livello di codice binario e la compatibilità con le versioni precedenti, vedere [Categorie di modifiche che causano un'interruzione](categories.md).</span><span class="sxs-lookup"><span data-stu-id="ec03d-116">For a definition of compatibility categories, such as binary compatibility and backward compatibility, see [Breaking change categories](categories.md).</span></span>

<span data-ttu-id="ec03d-117">Le sezioni seguenti descrivono le categorie delle modifiche apportate alle API di .NET Core e il relativo impatto sulla compatibilità delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ec03d-117">The following sections describes the categories of changes made to .NET Core APIs and their impact on application compatibility.</span></span> <span data-ttu-id="ec03d-118">L'icona ✔️ indica che è consentito un particolare tipo di modifica, ❌ indica che non è consentita e ❓ indica una modifica che può essere o meno consentita.</span><span class="sxs-lookup"><span data-stu-id="ec03d-118">The ✔️ icon indicates that a particular kind of change is allowed, ❌ indicates that it is disallowed, and  ❓ indicates a change that may or may not be allowed.</span></span> <span data-ttu-id="ec03d-119">Le modifiche di quest'ultima categoria richiedono una valutazione della prevedibilità, ovvietà e coerenza del comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="ec03d-119">Changes in this last category require judgment and an evaluation of how predictable, obvious, and consistent the previous behavior was.</span></span>

> [!NOTE]
> <span data-ttu-id="ec03d-120">Oltre a servire da guida per la valutazione delle modifiche alle librerie di .NET Core, questi criteri possono essere usati dagli sviluppatori di librerie per valutare le modifiche alle librerie destinate a più versioni e implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="ec03d-120">In addition to serving as a guide to how changes to .NET Core libraries are evaluated, library developers can also use these criteria to evaluate changes to their libraries that target multiple .NET implementations and versions.</span></span>

## <a name="modifications-to-the-public-contract"></a><span data-ttu-id="ec03d-121">Modifiche al contratto pubblico</span><span class="sxs-lookup"><span data-stu-id="ec03d-121">Modifications to the public contract</span></span>

<span data-ttu-id="ec03d-122">Le modifiche di questa categoria *interessano* la superficie di attacco pubblica di un tipo.</span><span class="sxs-lookup"><span data-stu-id="ec03d-122">Changes in this category *modify* the public surface area of a type.</span></span> <span data-ttu-id="ec03d-123">La maggior parte delle modifiche incluse in questa categoria non è consentita perché viola la *compatibilità con le versioni precedenti*, ovvero la capacità di un'applicazione sviluppata con una versione precedente di un'API di essere eseguita senza ricompilazione in una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="ec03d-123">Most of the changes in this category are disallowed since they violate *backwards compatibility* (the ability of an application that was developed with a previous version of an API to execute without recompilation on a later version).</span></span>

### <a name="types"></a><span data-ttu-id="ec03d-124">Tipi</span><span class="sxs-lookup"><span data-stu-id="ec03d-124">Types</span></span>

- <span data-ttu-id="ec03d-125">**✔️ Rimozione di un'implementazione dell'interfaccia da un tipo quando l'interfaccia è già implementata da un tipo di base**</span><span class="sxs-lookup"><span data-stu-id="ec03d-125">**✔️ Removing an interface implementation from a type when the interface is already implemented by a base type**</span></span>

- <span data-ttu-id="ec03d-126">**❓ Aggiunta di una nuova implementazione dell'interfaccia a un tipo**</span><span class="sxs-lookup"><span data-stu-id="ec03d-126">**❓ Adding a new interface implementation to a type**</span></span>

  <span data-ttu-id="ec03d-127">Questa è una modifica accettabile perché non ha effetti negativi sui client esistenti.</span><span class="sxs-lookup"><span data-stu-id="ec03d-127">This is an acceptable change because it does not adversely affect existing clients.</span></span> <span data-ttu-id="ec03d-128">Affinché la nuova implementazione rimanga accettabile, le modifiche al tipo devono rimanere entro i limiti delle modifiche accettabili definite di seguito.</span><span class="sxs-lookup"><span data-stu-id="ec03d-128">Any changes to the type must work within the boundaries of acceptable changes defined here for the new implementation to remain acceptable.</span></span> <span data-ttu-id="ec03d-129">È necessario prestare particolare attenzione quando si aggiungono interfacce che influiscono direttamente sulla capacità di una finestra di progettazione o un serializzatore di generare codice o dati che non possono essere utilizzati nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="ec03d-129">Extreme caution is necessary when adding interfaces that directly affect the ability of a designer or serializer to generate code or data that cannot be consumed down-level.</span></span> <span data-ttu-id="ec03d-130">Un esempio è costituito dall'interfaccia <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="ec03d-130">An example is the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

- <span data-ttu-id="ec03d-131">**❓ Introduzione di una nuova classe di base**</span><span class="sxs-lookup"><span data-stu-id="ec03d-131">**❓ Introducing a new base class**</span></span>

  <span data-ttu-id="ec03d-132">Un tipo può essere introdotto in una gerarchia tra due tipi esistenti se non introduce nuovi membri [astratti](../../csharp/language-reference/keywords/abstract.md) o modifica la semantica o il comportamento di tipi esistenti.</span><span class="sxs-lookup"><span data-stu-id="ec03d-132">A type can be introduced into an hierarchy between two existing types if it doesn't introduce any new [abstract](../../csharp/language-reference/keywords/abstract.md) members or change the semantics or behavior of existing types.</span></span> <span data-ttu-id="ec03d-133">Ad esempio, in .NET Framework 2.0, la classe <xref:System.Data.Common.DbConnection> è diventata una nuova classe di base per <xref:System.Data.SqlClient.SqlConnection>, che in precedenza derivava direttamente da <xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="ec03d-133">For example, in .NET Framework 2.0, the <xref:System.Data.Common.DbConnection> class became a new base class for <xref:System.Data.SqlClient.SqlConnection>, which had previously derived directly from <xref:System.ComponentModel.Component>.</span></span>

- <span data-ttu-id="ec03d-134">**✔️ Spostamento di un tipo da un assembly a un altro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-134">**✔️ Moving a type from one assembly to another**</span></span>

  <span data-ttu-id="ec03d-135">Si noti che l'assembly *precedente* deve essere contrassegnato con l'attributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> che punta al nuovo assembly.</span><span class="sxs-lookup"><span data-stu-id="ec03d-135">Note that the *old* assembly must be marked with the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> that points to the new assembly.</span></span>

- <span data-ttu-id="ec03d-136">**✔️ Modifica di un tipo [struct](../../csharp/language-reference/keywords/struct.md) in un tipo `readonly struct`**</span><span class="sxs-lookup"><span data-stu-id="ec03d-136">**✔️ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `readonly struct` type**</span></span>

  <span data-ttu-id="ec03d-137">Si noti che la modifica un tipo `readonly struct` in un tipo `struct` non è consentita.</span><span class="sxs-lookup"><span data-stu-id="ec03d-137">Note that changing a `readonly struct` type to a `struct` type is not allowed.</span></span>

- <span data-ttu-id="ec03d-138">**✔️ Aggiunta della parola chiave [sealed](../../csharp/language-reference/keywords/sealed.md) o [abstract](../../csharp/language-reference/keywords/abstract.md) a un tipo quando non sono presenti costruttori *accessibili* (pubblici o protetti)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-138">**✔️ Adding the [sealed](../../csharp/language-reference/keywords/sealed.md) or [abstract](../../csharp/language-reference/keywords/abstract.md) keyword to a type when there are no *accessible* (public or protected) constructors**</span></span>

- <span data-ttu-id="ec03d-139">**✔️ Espansione della visibilità di un tipo**</span><span class="sxs-lookup"><span data-stu-id="ec03d-139">**✔️ Expanding the visibility of a type**</span></span>

- <span data-ttu-id="ec03d-140">**❌ modifica dello spazio dei nomi o del nome di un tipo**</span><span class="sxs-lookup"><span data-stu-id="ec03d-140">**❌ Changing the namespace or name of a type**</span></span>

- <span data-ttu-id="ec03d-141">**❌ la ridenominazione o la rimozione di un tipo pubblico**</span><span class="sxs-lookup"><span data-stu-id="ec03d-141">**❌ Renaming or removing a public type**</span></span>

   <span data-ttu-id="ec03d-142">Questa operazione causa l'interruzione di tutto il codice che usa il tipo rinominato o rimosso.</span><span class="sxs-lookup"><span data-stu-id="ec03d-142">This breaks all code that uses the renamed or removed type.</span></span>

- <span data-ttu-id="ec03d-143">**❌ modifica del tipo sottostante di un'enumerazione**</span><span class="sxs-lookup"><span data-stu-id="ec03d-143">**❌ Changing the underlying type of an enumeration**</span></span>

   <span data-ttu-id="ec03d-144">Si tratta di una modifica che causa un'interruzione a livello di compilazione, comportamento e codice binario che può rendere non analizzabili gli argomenti degli attributi.</span><span class="sxs-lookup"><span data-stu-id="ec03d-144">This is a compile-time and behavioral breaking change as well as a binary breaking change that can make attribute arguments unparsable.</span></span>

- <span data-ttu-id="ec03d-145">**❌ il sealing di un tipo precedentemente non sealed**</span><span class="sxs-lookup"><span data-stu-id="ec03d-145">**❌ Sealing a type that was previously unsealed**</span></span>

- <span data-ttu-id="ec03d-146">**❌ l'aggiunta di un'interfaccia al set di tipi di base di un'interfaccia**</span><span class="sxs-lookup"><span data-stu-id="ec03d-146">**❌ Adding an interface to the set of base types of an interface**</span></span>

   <span data-ttu-id="ec03d-147">Se un'interfaccia implementa un'interfaccia che in precedenza non implementava, tutti i tipi che implementavano la versione originale dell'interfaccia vengono interrotti.</span><span class="sxs-lookup"><span data-stu-id="ec03d-147">If an interface implements an interface that it previously did not implement, all types that implemented the original version of the interface are broken.</span></span>

- <span data-ttu-id="ec03d-148">**❓ Rimozione di una classe da un set di classi di base o di un'interfaccia dal set di interfacce implementate**</span><span class="sxs-lookup"><span data-stu-id="ec03d-148">**❓ Removing a class from the set of base classes or an interface from the set of implemented interfaces**</span></span>

  <span data-ttu-id="ec03d-149">Esiste un'unica eccezione alla regola per la rimozione di un'interfaccia. È possibile aggiungere l'implementazione di un'interfaccia che deriva dall'interfaccia rimossa.</span><span class="sxs-lookup"><span data-stu-id="ec03d-149">There is one exception to the rule for interface removal: you can add the implementation of an interface that derives from the removed interface.</span></span> <span data-ttu-id="ec03d-150">È ad esempio possibile rimuovere <xref:System.IDisposable> se il tipo o l'interfaccia implementa ora <xref:System.ComponentModel.IComponent>, che implementa a sua volta l'interfaccia <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="ec03d-150">For example, you can remove <xref:System.IDisposable> if the type or interface now implements <xref:System.ComponentModel.IComponent>, which implements <xref:System.IDisposable>.</span></span>

- <span data-ttu-id="ec03d-151">**❌ la modifica di un tipo di `readonly struct` in un tipo [struct](../../csharp/language-reference/keywords/struct.md)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-151">**❌ Changing a `readonly struct` type to a [struct](../../csharp/language-reference/keywords/struct.md) type**</span></span>

  <span data-ttu-id="ec03d-152">Si noti che la modifica di un tipo `struct` in un tipo `readonly struct` è consentita.</span><span class="sxs-lookup"><span data-stu-id="ec03d-152">Note that the change of a `struct` type to a `readonly struct` type is allowed.</span></span>

- <span data-ttu-id="ec03d-153">**❌ la modifica di un tipo [struct](../../csharp/language-reference/keywords/struct.md) in un tipo di `ref struct` e viceversa**</span><span class="sxs-lookup"><span data-stu-id="ec03d-153">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `ref struct` type, and vice versa**</span></span>

- <span data-ttu-id="ec03d-154">**❌ riduzione della visibilità di un tipo**</span><span class="sxs-lookup"><span data-stu-id="ec03d-154">**❌ Reducing the visibility of a type**</span></span>

   <span data-ttu-id="ec03d-155">L'espansione della visibilità di un tipo è tuttavia consentita.</span><span class="sxs-lookup"><span data-stu-id="ec03d-155">However, increasing the visibility of a type is allowed.</span></span>

### <a name="members"></a><span data-ttu-id="ec03d-156">Members</span><span class="sxs-lookup"><span data-stu-id="ec03d-156">Members</span></span>

- <span data-ttu-id="ec03d-157">**✔️ Espansione della visibilità di un membro non [virtuale](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-157">**✔️ Expanding the visibility of a member that is not [virtual](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="ec03d-158">**✔️ Aggiunta di un membro astratto a un tipo pubblico che non ha costruttori *accessibili* (pubblici o protetti) o che è [sealed](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-158">**✔️ Adding an abstract member to a public type that has no *accessible* (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

  <span data-ttu-id="ec03d-159">Non è tuttavia consentita l'aggiunta di un membro astratto a un tipo pubblico che ha costruttori accessibili (pubblici o protetti) e che non è `sealed`.</span><span class="sxs-lookup"><span data-stu-id="ec03d-159">However, adding an abstract member to a type that has accessible (public or protected) constructors and is not `sealed` is not allowed.</span></span>

- <span data-ttu-id="ec03d-160">**✔️ Limitazione della visibilità di un membro [protetto](../../csharp/language-reference/keywords/protected.md) quando il tipo non ha costruttori accessibili (pubblici o protetti) oppure è [sealed](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-160">**✔️ Restricting the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when the type has no accessible (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="ec03d-161">**✔️ Spostamento di un membro in una classe di livello superiore nella gerarchia rispetto al tipo da cui è stato rimosso**</span><span class="sxs-lookup"><span data-stu-id="ec03d-161">**✔️ Moving a member into a class higher in the hierarchy than the type from which it was removed**</span></span>

- <span data-ttu-id="ec03d-162">**✔️ Aggiunta o rimozione di un override**</span><span class="sxs-lookup"><span data-stu-id="ec03d-162">**✔️ Adding or removing an override**</span></span>

  <span data-ttu-id="ec03d-163">Si noti che, se si introduce un override, i consumer precedenti potrebbero ignorare l'override quando eseguono la chiamata a [base](../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="ec03d-163">Note that introducing an override might cause previous consumers to skip over the override when calling [base](../../csharp/language-reference/keywords/base.md).</span></span>

- <span data-ttu-id="ec03d-164">**✔️ Aggiunta di un costruttore a una classe, insieme a un costruttore predefinito (senza parametri), se in precedenza la classe era priva di costruttori**</span><span class="sxs-lookup"><span data-stu-id="ec03d-164">**✔️ Adding a constructor to a class, along with a default (parameterless) constructor if the class previously had no constructors**</span></span>

   <span data-ttu-id="ec03d-165">Non è tuttavia consentita l'aggiunta di un costruttore a una classe che in precedenza era priva di costruttori *senza* aggiungere il costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="ec03d-165">However, adding a constructor to a class that previously had no constructors *without* adding the parameterless constructor is not allowed.</span></span>

- <span data-ttu-id="ec03d-166">**✔️ Modifica di un membro da [astratto](../../csharp/language-reference/keywords/abstract.md) a [virtuale](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-166">**✔️ Changing a member from [abstract](../../csharp/language-reference/keywords/abstract.md) to [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

- <span data-ttu-id="ec03d-167">**✔️ Modifica da un `ref readonly` a un valore restituito `ref` (ad eccezione dei metodi o delle interfacce virtuali)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-167">**✔️ Changing from a `ref readonly` to a `ref` return value (except for virtual methods or interfaces)**</span></span>

- <span data-ttu-id="ec03d-168">**✔️ Rimozione di [readonly](../../csharp/language-reference/keywords/readonly.md) da un campo, a meno che il tipo statico del campo non sia un tipo di valore modificabile**</span><span class="sxs-lookup"><span data-stu-id="ec03d-168">**✔️ Removing [readonly](../../csharp/language-reference/keywords/readonly.md) from a field, unless the static type of the field is a mutable value type**</span></span>

- <span data-ttu-id="ec03d-169">**✔️ Chiamata di un nuovo evento non definito in precedenza**</span><span class="sxs-lookup"><span data-stu-id="ec03d-169">**✔️ Calling a new event that wasn't previously defined**</span></span>

- <span data-ttu-id="ec03d-170">**❓ Aggiunta del campo di una nuova istanza a un tipo**</span><span class="sxs-lookup"><span data-stu-id="ec03d-170">**❓ Adding a new instance field to a type**</span></span>

   <span data-ttu-id="ec03d-171">Questa modifica ha impatto sulla serializzazione.</span><span class="sxs-lookup"><span data-stu-id="ec03d-171">This change impacts serialization.</span></span>

- <span data-ttu-id="ec03d-172">**❌ la ridenominazione o la rimozione di un membro o un parametro pubblico**</span><span class="sxs-lookup"><span data-stu-id="ec03d-172">**❌ Renaming or removing a public member or parameter**</span></span>

   <span data-ttu-id="ec03d-173">Questa operazione causa l'interruzione di tutto il codice che usa il parametro o il membro rinominato o rimosso.</span><span class="sxs-lookup"><span data-stu-id="ec03d-173">This breaks all code that uses the renamed or removed member, or parameter.</span></span>

   <span data-ttu-id="ec03d-174">Si noti che questo include la rimozione o la ridenominazione di un getter o un setter da una proprietà, nonché la ridenominazione o la rimozione dei membri di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ec03d-174">Note that this includes removing or renaming a getter or setter from a property, as well as renaming or removing enumeration members.</span></span>

- <span data-ttu-id="ec03d-175">**❌ l'aggiunta di un membro a un'interfaccia**</span><span class="sxs-lookup"><span data-stu-id="ec03d-175">**❌ Adding a member to an interface**</span></span>

- <span data-ttu-id="ec03d-176">**❌ la modifica del valore di una costante pubblica o di un membro di enumerazione**</span><span class="sxs-lookup"><span data-stu-id="ec03d-176">**❌ Changing the value of a public constant or enumeration member**</span></span>

- <span data-ttu-id="ec03d-177">**❌ modifica del tipo di una proprietà, un campo, un parametro o un valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ec03d-177">**❌ Changing the type of a property, field, parameter, or return value**</span></span>

- <span data-ttu-id="ec03d-178">**❌ l'aggiunta, la rimozione o la modifica dell'ordine dei parametri**</span><span class="sxs-lookup"><span data-stu-id="ec03d-178">**❌ Adding, removing, or changing the order of parameters**</span></span>

- <span data-ttu-id="ec03d-179">**❌ l'aggiunta o la rimozione della parola chiave [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) o [ref](../../csharp/language-reference/keywords/ref.md) da un parametro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-179">**❌ Adding or removing the [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) , or [ref](../../csharp/language-reference/keywords/ref.md) keyword from a parameter**</span></span>

- <span data-ttu-id="ec03d-180">**❌ la ridenominazione di un parametro (inclusa la modifica del case)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-180">**❌ Renaming a parameter (including changing its case)**</span></span>

  <span data-ttu-id="ec03d-181">Questa viene considerata una modifica che causa un'interruzione per due motivi:</span><span class="sxs-lookup"><span data-stu-id="ec03d-181">This is considered breaking for two reasons:</span></span>

  - <span data-ttu-id="ec03d-182">Interrompe gli scenari con associazione tardiva, ad esempio la funzionalità di associazione tardiva in Visual Basic e [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) in C#.</span><span class="sxs-lookup"><span data-stu-id="ec03d-182">It breaks late-bound scenarios such as the late binding feature in Visual Basic and [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) in C#.</span></span>

  - <span data-ttu-id="ec03d-183">Interrompe la [compatibilità a livello di codice sorgente](categories.md#source-compatibility) quando gli sviluppatori usano [argomenti denominati](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).</span><span class="sxs-lookup"><span data-stu-id="ec03d-183">It breaks [source compatibility](categories.md#source-compatibility) when developers use [named arguments](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).</span></span>

- <span data-ttu-id="ec03d-184">**❌ la modifica da un valore restituito `ref` a un valore restituito `ref readonly`**</span><span class="sxs-lookup"><span data-stu-id="ec03d-184">**❌ Changing from a `ref` return value to a `ref readonly` return value**</span></span>

- <span data-ttu-id="ec03d-185">**❌️ la modifica da un `ref readonly` a un valore restituito `ref` su un metodo o un'interfaccia virtuale**</span><span class="sxs-lookup"><span data-stu-id="ec03d-185">**❌️ Changing from a `ref readonly` to a `ref` return value on a virtual method or interface**</span></span>

- <span data-ttu-id="ec03d-186">**❌ l'aggiunta o la rimozione di un oggetto [abstract](../../csharp/language-reference/keywords/abstract.md) da un membro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-186">**❌ Adding or removing [abstract](../../csharp/language-reference/keywords/abstract.md) from a member**</span></span>

- <span data-ttu-id="ec03d-187">**❌ la rimozione della parola chiave [Virtual](../../csharp/language-reference/keywords/virtual.md) da un membro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-187">**❌ Removing the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword from a member**</span></span>

  <span data-ttu-id="ec03d-188">Anche se spesso questa non è una modifica che causa un'interruzione perché il compilatore C# tende a generare istruzioni [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) in linguaggio intermedio (IL) per chiamare metodi non virtuali (diversamente da una normale chiamata, `callvirt` esegue un controllo null), questo comportamento non è invariabile per diversi motivi:</span><span class="sxs-lookup"><span data-stu-id="ec03d-188">While this often is not a breaking change because the C# compiler tends to emit [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) Intermediate Language (IL) instructions to call non-virtual methods (`callvirt` performs a null check, while a normal call doesn't), this behavior is not invariable for several reasons:</span></span>
  - <span data-ttu-id="ec03d-189">C# non è l'unico linguaggio di destinazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="ec03d-189">C# is not the only language that .NET targets.</span></span>

  - <span data-ttu-id="ec03d-190">Il compilatore C# tenta sempre più di ottimizzare `callvirt` in una normale chiamata ogni volta che il metodo di destinazione non è virtuale e presumibilmente non è null (ad esempio quando si accede a un metodo tramite l'[operatore di propagazione null ?.](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).</span><span class="sxs-lookup"><span data-stu-id="ec03d-190">The C# compiler increasingly tries to optimize `callvirt` to a normal call whenever the target method is non-virtual and is probably not null (such as a method accessed through the [?. null propagation operator](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).</span></span>

  <span data-ttu-id="ec03d-191">Quando un metodo viene impostato come virtuale, spesso il codice consumer finisce per chiamarlo in modo non virtuale.</span><span class="sxs-lookup"><span data-stu-id="ec03d-191">Making a method virtual means that the consumer code would often end up calling it non-virtually.</span></span>

- <span data-ttu-id="ec03d-192">**❌ aggiunta della parola chiave [Virtual](../../csharp/language-reference/keywords/virtual.md) a un membro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-192">**❌ Adding the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword to a member**</span></span>

- <span data-ttu-id="ec03d-193">**❌ rendere astratto un membro virtuale**</span><span class="sxs-lookup"><span data-stu-id="ec03d-193">**❌ Making a virtual member abstract**</span></span>

  <span data-ttu-id="ec03d-194">Un [membro virtuale](../../csharp/language-reference/keywords/virtual.md) fornisce un'implementazione di metodo che *può essere* sottoposta a override da una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="ec03d-194">A [virtual member](../../csharp/language-reference/keywords/virtual.md) provides a method implementation that *can be* overridden by a derived class.</span></span> <span data-ttu-id="ec03d-195">Un [membro astratto](../../csharp/language-reference/keywords/abstract.md) non fornisce alcuna implementazione e *deve essere* sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="ec03d-195">An [abstract member](../../csharp/language-reference/keywords/abstract.md) provides no implementation and *must be* overridden.</span></span>

- <span data-ttu-id="ec03d-196">**❌ l'aggiunta di un membro astratto a un tipo pubblico con costruttori accessibili (pubblici o protetti) e non [sealed](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-196">**❌ Adding an abstract member to a public type that has accessible (public or protected) constructors and that is not [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="ec03d-197">**❌ l'aggiunta o la rimozione della parola chiave [static](../../csharp/language-reference/keywords/static.md) da un membro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-197">**❌ Adding or removing the [static](../../csharp/language-reference/keywords/static.md) keyword from a member**</span></span>

- <span data-ttu-id="ec03d-198">**❌ l'aggiunta di un overload che impedisce un overload esistente e definisce un comportamento diverso**</span><span class="sxs-lookup"><span data-stu-id="ec03d-198">**❌ Adding an overload that precludes an existing overload and defines a different behavior**</span></span>

  <span data-ttu-id="ec03d-199">Questa modifica causa un'interruzione dei client esistenti associati all'overload precedente.</span><span class="sxs-lookup"><span data-stu-id="ec03d-199">This breaks existing clients that were bound to the previous overload.</span></span> <span data-ttu-id="ec03d-200">Se, ad esempio, una classe dispone di una singola versione di un metodo che accetta uno struct <xref:System.UInt32>, un consumer esistente viene correttamente associato a tale overload quando viene passato un valore <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="ec03d-200">For example, if a class has a single version of a method that accepts a <xref:System.UInt32>, an existing consumer will successfully bind to that overload when passing a <xref:System.Int32> value.</span></span> <span data-ttu-id="ec03d-201">Se tuttavia si aggiunge un overload che accetta uno struct <xref:System.Int32>, quando viene eseguita la ricompilazione o viene usata l'associazione tardiva, il compilatore stabilisce l'associazione con il nuovo overload.</span><span class="sxs-lookup"><span data-stu-id="ec03d-201">However, if you add an overload that accepts an <xref:System.Int32>, when recompiling or using late-binding, the compiler now binds to the new overload.</span></span> <span data-ttu-id="ec03d-202">In caso di comportamento diverso, si tratta di una modifica che causa un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="ec03d-202">If different behavior results, this is a breaking change.</span></span>

- <span data-ttu-id="ec03d-203">**❌ l'aggiunta di un costruttore a una classe che in precedenza non aveva alcun costruttore senza aggiungere il costruttore senza parametri**</span><span class="sxs-lookup"><span data-stu-id="ec03d-203">**❌ Adding a constructor to a class that previously had no constructor without adding the parameterless constructor**</span></span>

- <span data-ttu-id="ec03d-204">**❌️ l'aggiunta di [ReadOnly](../../csharp/language-reference/keywords/readonly.md) a un campo**</span><span class="sxs-lookup"><span data-stu-id="ec03d-204">**❌️ Adding [readonly](../../csharp/language-reference/keywords/readonly.md) to a field**</span></span>

- <span data-ttu-id="ec03d-205">**❌ riduzione della visibilità di un membro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-205">**❌ Reducing the visibility of a member**</span></span>

   <span data-ttu-id="ec03d-206">Ciò include la limitazione della visibilità di un membro [protetto](../../csharp/language-reference/keywords/protected.md) quando non sono presenti costruttori *accessibili* (pubblici o protetti) e il tipo *non* è [sealed](../../csharp/language-reference/keywords/sealed.md).</span><span class="sxs-lookup"><span data-stu-id="ec03d-206">This includes reducing the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when there are *accessible* (public or protected) constructors and the type is *not* [sealed](../../csharp/language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="ec03d-207">Se questo non avviene, la limitazione della visibilità di un membro protetto è consentita.</span><span class="sxs-lookup"><span data-stu-id="ec03d-207">If this is not the case, reducing the visibility of a protected member is allowed.</span></span>

   <span data-ttu-id="ec03d-208">L'espansione della visibilità di un membro è tuttavia consentita.</span><span class="sxs-lookup"><span data-stu-id="ec03d-208">Note that increasing the visibility of a member is allowed.</span></span>

- <span data-ttu-id="ec03d-209">**❌ modifica del tipo di un membro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-209">**❌ Changing the type of a member**</span></span>

   <span data-ttu-id="ec03d-210">Il valore restituito di un metodo o il tipo di una proprietà o di un campo non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="ec03d-210">The return value of a method or the type of a property or field cannot be modified.</span></span> <span data-ttu-id="ec03d-211">Ad esempio, la firma di un metodo che restituisce un tipo <xref:System.Object> non può essere modificata in modo da restituire un tipo <xref:System.String> o viceversa.</span><span class="sxs-lookup"><span data-stu-id="ec03d-211">For example, the signature of a method that returns an <xref:System.Object> cannot be changed to return a <xref:System.String>, or vice versa.</span></span>

- <span data-ttu-id="ec03d-212">**❌ l'aggiunta di un campo a uno struct che in precedenza non aveva alcuno stato**</span><span class="sxs-lookup"><span data-stu-id="ec03d-212">**❌ Adding a field to a struct that previously had no state**</span></span>

  <span data-ttu-id="ec03d-213">Determinate regole di assegnazione consentono l'uso di variabili non inizializzate, purché il tipo di variabile sia uno struct senza stato.</span><span class="sxs-lookup"><span data-stu-id="ec03d-213">Definite assignment rules allow the use of uninitialized variables so long as the variable type is a stateless struct.</span></span> <span data-ttu-id="ec03d-214">Se lo struct è definito con stato, può verificarsi un problema di mancata inizializzazione dei dati del codice.</span><span class="sxs-lookup"><span data-stu-id="ec03d-214">If the struct is made stateful, code could end up with uninitialized data.</span></span> <span data-ttu-id="ec03d-215">Si tratta potenzialmente di una modifica che causa un'interruzione a livello di codice sorgente e di codice binario.</span><span class="sxs-lookup"><span data-stu-id="ec03d-215">This is both potentially a source breaking and a binary breaking change.</span></span>

- <span data-ttu-id="ec03d-216">**❌ la generazione di un evento esistente quando non è mai stato generato prima**</span><span class="sxs-lookup"><span data-stu-id="ec03d-216">**❌ Firing an existing event when it was never fired before**</span></span>

## <a name="behavioral-changes"></a><span data-ttu-id="ec03d-217">Modifiche del comportamento</span><span class="sxs-lookup"><span data-stu-id="ec03d-217">Behavioral changes</span></span>

### <a name="assemblies"></a><span data-ttu-id="ec03d-218">Assembly</span><span class="sxs-lookup"><span data-stu-id="ec03d-218">Assemblies</span></span>

- <span data-ttu-id="ec03d-219">**✔️ Rendere portabile un assembly quando le stesse piattaforme sono ancora supportate**</span><span class="sxs-lookup"><span data-stu-id="ec03d-219">**✔️ Making an assembly portable when the same platforms are still supported**</span></span>

- <span data-ttu-id="ec03d-220">**❌ la modifica del nome di un assembly**</span><span class="sxs-lookup"><span data-stu-id="ec03d-220">**❌ Changing the name of an assembly**</span></span>
- <span data-ttu-id="ec03d-221">**❌ la modifica della chiave pubblica di un assembly**</span><span class="sxs-lookup"><span data-stu-id="ec03d-221">**❌ Changing the public key of an assembly**</span></span>

### <a name="properties-fields-parameters-and-return-values"></a><span data-ttu-id="ec03d-222">Proprietà, campi, parametri e valori restituiti</span><span class="sxs-lookup"><span data-stu-id="ec03d-222">Properties, fields, parameters, and return values</span></span>

- <span data-ttu-id="ec03d-223">**✔️ Modifica del valore di una proprietà, di un campo, di un valore restituito o di un parametro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) in un tipo più derivato**</span><span class="sxs-lookup"><span data-stu-id="ec03d-223">**✔️ Changing the value of a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter to a more derived type**</span></span>

  <span data-ttu-id="ec03d-224">Ad esempio, un metodo che restituisce un tipo <xref:System.Object> può restituire un'istanza di <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ec03d-224">For example, a method that returns a type of <xref:System.Object> can return a <xref:System.String> instance.</span></span> <span data-ttu-id="ec03d-225">Non è tuttavia possibile modificare la firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="ec03d-225">(However, the method signature cannot change.)</span></span>

- <span data-ttu-id="ec03d-226">**✔️ Aumento dell'intervallo di valori accettati per una proprietà o un parametro se il membro non è [virtuale](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-226">**✔️ Increasing the range of accepted values for a property or parameter if the member is not [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

  <span data-ttu-id="ec03d-227">Si noti che l'intervallo di valori che possono essere passati al metodo o che vengono restituiti dal membro può essere esteso, ma il tipo di parametro o di membro deve rimanere invariato.</span><span class="sxs-lookup"><span data-stu-id="ec03d-227">Note that while the range of values that can be passed to the method or are returned by the member can expand, the parameter or member type cannot.</span></span> <span data-ttu-id="ec03d-228">Ad esempio, i valori passati a un metodo possono aumentare da 0-124 a 0-255, ma il tipo di parametro non può cambiare da <xref:System.Byte> a <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="ec03d-228">For example, while the values passed to a method can expand from 0-124 to 0-255, the parameter type cannot change from <xref:System.Byte> to <xref:System.Int32>.</span></span>

- <span data-ttu-id="ec03d-229">**❌ aumentare l'intervallo di valori accettati per una proprietà o un parametro se il membro è [virtuale](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-229">**❌ Increasing the range of accepted values for a property or parameter if the member is [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

   <span data-ttu-id="ec03d-230">Questa modifica interrompe i membri sottoposti a override esistenti, che non funzioneranno correttamente per l'intervallo di valori esteso.</span><span class="sxs-lookup"><span data-stu-id="ec03d-230">This change breaks existing overridden members, which will not function correctly for the extended range of values.</span></span>

- <span data-ttu-id="ec03d-231">**❌ la riduzione dell'intervallo di valori accettati per una proprietà o un parametro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-231">**❌ Decreasing the range of accepted values for a property or parameter**</span></span>

- <span data-ttu-id="ec03d-232">**❌ aumentare l'intervallo di valori restituiti per una proprietà, un campo, un valore restituito o un parametro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-232">**❌ Increasing the range of returned values for a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="ec03d-233">**❌ la modifica dei valori restituiti per una proprietà, un campo, un valore restituito di un metodo o un parametro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-233">**❌ Changing the returned values for a property, field, method return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="ec03d-234">**❌ modifica del valore predefinito di una proprietà, un campo o un parametro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-234">**❌ Changing the default value of a property, field, or parameter**</span></span>

- <span data-ttu-id="ec03d-235">**❌ modifica della precisione di un valore restituito numerico**</span><span class="sxs-lookup"><span data-stu-id="ec03d-235">**❌ Changing the precision of a numeric return value**</span></span>

- <span data-ttu-id="ec03d-236">**❓ Modifica nell'analisi dell'input e nella generazione di nuove eccezioni (anche se il comportamento dell'analisi non è specificato nella documentazione**</span><span class="sxs-lookup"><span data-stu-id="ec03d-236">**❓ A change in the parsing of input and throwing new exceptions (even if parsing behavior is not specified in the documentation**</span></span>

### <a name="exceptions"></a><span data-ttu-id="ec03d-237">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="ec03d-237">Exceptions</span></span>

- <span data-ttu-id="ec03d-238">**✔️ Generazione di un'eccezione più derivata rispetto a un'eccezione esistente**</span><span class="sxs-lookup"><span data-stu-id="ec03d-238">**✔️ Throwing a more derived exception than an existing exception**</span></span>

  <span data-ttu-id="ec03d-239">Poiché la nuova eccezione è una sottoclasse di un'eccezione esistente, il codice che gestisce l'eccezione precedente continua a gestire quella nuova.</span><span class="sxs-lookup"><span data-stu-id="ec03d-239">Because the new exception is a subclass of an existing exception, previous exception handling code continues to handle the exception.</span></span> <span data-ttu-id="ec03d-240">In .NET Framework 4, ad esempio, i metodi per la creazione e il recupero delle impostazioni cultura hanno iniziato a generare <xref:System.Globalization.CultureNotFoundException> anziché <xref:System.ArgumentException> in caso di impossibilità di trovare le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="ec03d-240">For example, in .NET Framework 4, culture creation and retrieval methods began to throw a <xref:System.Globalization.CultureNotFoundException> instead of an <xref:System.ArgumentException> if the culture could not be found.</span></span> <span data-ttu-id="ec03d-241">Poiché <xref:System.Globalization.CultureNotFoundException> deriva da <xref:System.ArgumentException>, questa è una modifica accettabile.</span><span class="sxs-lookup"><span data-stu-id="ec03d-241">Because <xref:System.Globalization.CultureNotFoundException> derives from <xref:System.ArgumentException>, this is an acceptable change.</span></span>

- <span data-ttu-id="ec03d-242">**✔️ Generazione di un'eccezione più specifica rispetto a <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span><span class="sxs-lookup"><span data-stu-id="ec03d-242">**✔️ Throwing a more specific exception than <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span></span>

- <span data-ttu-id="ec03d-243">**✔️ Generazione di un'eccezione considerata irreversibile**</span><span class="sxs-lookup"><span data-stu-id="ec03d-243">**✔️ Throwing an exception that is considered unrecoverable**</span></span>

  <span data-ttu-id="ec03d-244">Le eccezioni irreversibili non devono essere intercettate, ma devono essere gestite da un gestore catch-all di alto livello.</span><span class="sxs-lookup"><span data-stu-id="ec03d-244">Unrecoverable exceptions should not be caught but instead should be handled by a high-level catch-all handler.</span></span> <span data-ttu-id="ec03d-245">Non è quindi previsto che gli utenti abbiano codice che intercetta queste eccezioni esplicite.</span><span class="sxs-lookup"><span data-stu-id="ec03d-245">Therefore, users are not expected to have code that catches these explicit exceptions.</span></span> <span data-ttu-id="ec03d-246">Le eccezioni irreversibili comprendono:</span><span class="sxs-lookup"><span data-stu-id="ec03d-246">The unrecoverable exceptions are:</span></span>

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- <span data-ttu-id="ec03d-247">**✔️ Generazione di una nuova eccezione in un nuovo percorso del codice**</span><span class="sxs-lookup"><span data-stu-id="ec03d-247">**✔️ Throwing a new exception in a new code path**</span></span>

  <span data-ttu-id="ec03d-248">L'eccezione deve interessare solo un nuovo percorso del codice che viene eseguito con un nuovo stato o nuovi valori di parametro e non può essere eseguito da codice esistente creato per la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="ec03d-248">The exception must apply only to a new code-path which is executed with new parameter values or state, and that can't be executed by existing code that targets the previous version.</span></span>

- <span data-ttu-id="ec03d-249">**✔️ Rimozione di un'eccezione per abilitare nuovi scenari o un comportamento più efficace**</span><span class="sxs-lookup"><span data-stu-id="ec03d-249">**✔️ Removing an exception to enable more robust behavior or new scenarios**</span></span>

  <span data-ttu-id="ec03d-250">Ad esempio, un metodo `Divide` che in precedenza gestiva solo valori positivi, generando un'eccezione <xref:System.ArgumentOutOfRangeException> negli altri casi, può essere modificato in modo da supportare valori negativi e positivi senza generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ec03d-250">For example, a `Divide` method that previously only handled positive values and threw an <xref:System.ArgumentOutOfRangeException> otherwise can be changed to support both negative and positive values without throwing an exception.</span></span>

- <span data-ttu-id="ec03d-251">**✔️ Modifica del testo di un messaggio di errore**</span><span class="sxs-lookup"><span data-stu-id="ec03d-251">**✔️ Changing the text of an error message**</span></span>

  <span data-ttu-id="ec03d-252">Gli sviluppatori non devono basarsi sul testo dei messaggi di errore, che cambiano anche in base alle impostazioni cultura dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ec03d-252">Developers should not rely on the text of error messages, which also change based on the user's culture.</span></span>

- <span data-ttu-id="ec03d-253">**❌ generata un'eccezione in qualsiasi altro caso non elencato sopra**</span><span class="sxs-lookup"><span data-stu-id="ec03d-253">**❌ Throwing an exception in any other case not listed above**</span></span>

- <span data-ttu-id="ec03d-254">**❌ la rimozione di un'eccezione in altri casi non elencati in precedenza**</span><span class="sxs-lookup"><span data-stu-id="ec03d-254">**❌ Removing an exception in any other case not listed above**</span></span>

### <a name="attributes"></a><span data-ttu-id="ec03d-255">Attributi</span><span class="sxs-lookup"><span data-stu-id="ec03d-255">Attributes</span></span>

- <span data-ttu-id="ec03d-256">**✔️ Modifica del valore di un attributo che *non* è osservabile**</span><span class="sxs-lookup"><span data-stu-id="ec03d-256">**✔️ Changing the value of an attribute that is *not* observable**</span></span>

- <span data-ttu-id="ec03d-257">**❌ modifica del valore di un *attributo osservabile***</span><span class="sxs-lookup"><span data-stu-id="ec03d-257">**❌ Changing the value of an attribute that *is* observable**</span></span>

- <span data-ttu-id="ec03d-258">**❓ Rimozione di un attributo**</span><span class="sxs-lookup"><span data-stu-id="ec03d-258">**❓ Removing an attribute**</span></span>

  <span data-ttu-id="ec03d-259">Nella maggior parte dei casi, la rimozione di un attributo (ad esempio <xref:System.NonSerializedAttribute>) è una modifica che causa un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="ec03d-259">In most cases, removing an attribute (such as <xref:System.NonSerializedAttribute>) is a breaking change.</span></span>

## <a name="platform-support"></a><span data-ttu-id="ec03d-260">Supporto per piattaforme</span><span class="sxs-lookup"><span data-stu-id="ec03d-260">Platform support</span></span>

- <span data-ttu-id="ec03d-261">**✔️ Supporto di un'operazione su una piattaforma che in precedenza non era supportata**</span><span class="sxs-lookup"><span data-stu-id="ec03d-261">**✔️ Supporting an operation on a platform that was previously not supported**</span></span>

- <span data-ttu-id="ec03d-262">**❌ non supporta o che ora richiede un Service Pack specifico per un'operazione supportata in precedenza in una piattaforma**</span><span class="sxs-lookup"><span data-stu-id="ec03d-262">**❌ Not supporting or now requiring a specific service pack for an operation that was previously supported on a platform**</span></span>

## <a name="internal-implementation-changes"></a><span data-ttu-id="ec03d-263">Modifiche all'implementazione interna</span><span class="sxs-lookup"><span data-stu-id="ec03d-263">Internal implementation changes</span></span>

- <span data-ttu-id="ec03d-264">**❓ Modifica della superficie di attacco di un tipo interno**</span><span class="sxs-lookup"><span data-stu-id="ec03d-264">**❓ Changing the surface area of an internal type**</span></span>

   <span data-ttu-id="ec03d-265">Queste modifiche sono in genere consentite, anche se interrompono la reflection privata.</span><span class="sxs-lookup"><span data-stu-id="ec03d-265">Such changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="ec03d-266">È tuttavia possibile che in alcuni casi non lo siano, ad esempio quando le librerie di terze parti più diffuse o numerosi sviluppatori dipendono dalle API interne.</span><span class="sxs-lookup"><span data-stu-id="ec03d-266">In some cases, where popular third-party libraries or a large number of developers depend on the internal APIs, such changes may not be allowed.</span></span>

- <span data-ttu-id="ec03d-267">**❓ Modifica dell'implementazione interna di un membro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-267">**❓ Changing the internal implementation of a member**</span></span>

  <span data-ttu-id="ec03d-268">Queste modifiche sono in genere consentite, anche se interrompono la reflection privata.</span><span class="sxs-lookup"><span data-stu-id="ec03d-268">These changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="ec03d-269">È tuttavia possibile che in alcuni casi non lo siano, ad esempio quando il codice cliente dipende spesso dalla reflection privata o la modifica presenta effetti collaterali imprevisti.</span><span class="sxs-lookup"><span data-stu-id="ec03d-269">In some cases, where customer code frequently depends on private reflection or where the change introduces unintended side effects, these changes may not be allowed.</span></span>

- <span data-ttu-id="ec03d-270">**✔️ Miglioramento delle prestazioni di un'operazione**</span><span class="sxs-lookup"><span data-stu-id="ec03d-270">**✔️ Improving the performance of an operation**</span></span>

   <span data-ttu-id="ec03d-271">La possibilità di modificare le prestazioni di un'operazione è essenziale, ma tali modifiche possono interrompere il codice che si basa la velocità corrente di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="ec03d-271">The ability to modify the performance of an operation is essential, but such changes can break code that relies upon the current speed of an operation.</span></span> <span data-ttu-id="ec03d-272">Questo vale in particolare per il codice che dipende dalla tempistica delle operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="ec03d-272">This is particularly true of code that depends on the timing of asynchronous operations.</span></span> <span data-ttu-id="ec03d-273">Si noti che la modifica delle prestazioni non deve avere alcun effetto su altri comportamenti dell'API in questione. In caso contrario, la modifica causerà un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="ec03d-273">Note that the performance change should have no effect on other behavior of the API in question; otherwise, the change will be breaking.</span></span>

- <span data-ttu-id="ec03d-274">**✔️ Modifica indiretta (e spesso con effetti negativi) delle prestazioni di un'operazione**</span><span class="sxs-lookup"><span data-stu-id="ec03d-274">**✔️ Indirectly (and often adversely) changing the performance of an operation**</span></span>

  <span data-ttu-id="ec03d-275">La modifica in questione è accettabile se non è classificata per altri motivi come modifica che causa un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="ec03d-275">If the change in question is not categorized as breaking for some other reason, this is acceptable.</span></span> <span data-ttu-id="ec03d-276">È spesso necessario eseguire azioni che includono operazioni supplementari o che aggiungono nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ec03d-276">Often, actions need to be taken that may include extra operations or that add new functionality.</span></span> <span data-ttu-id="ec03d-277">Questo ha quasi sempre effetto sulle prestazioni, ma può essere fondamentale per fare in modo che l'API in questione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="ec03d-277">This will almost always affect performance but may be essential to make the API in question function as expected.</span></span>

- <span data-ttu-id="ec03d-278">**❌ la modifica di un'API sincrona in asincrona (e viceversa)**</span><span class="sxs-lookup"><span data-stu-id="ec03d-278">**❌ Changing a synchronous API to asynchronous (and vice versa)**</span></span>

## <a name="code-changes"></a><span data-ttu-id="ec03d-279">Modifiche al codice</span><span class="sxs-lookup"><span data-stu-id="ec03d-279">Code changes</span></span>

- <span data-ttu-id="ec03d-280">**✔️ Aggiunta di [params](../../csharp/language-reference/keywords/params.md) a un parametro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-280">**✔️ Adding [params](../../csharp/language-reference/keywords/params.md) to a parameter**</span></span>

- <span data-ttu-id="ec03d-281">**❌ la modifica di uno [struct](../../csharp/language-reference/keywords/struct.md) in una [classe](../../csharp/language-reference/keywords/class.md) e viceversa**</span><span class="sxs-lookup"><span data-stu-id="ec03d-281">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) to a [class](../../csharp/language-reference/keywords/class.md) and vice versa**</span></span>

- <span data-ttu-id="ec03d-282">**❌ aggiunta della parola chiave [checked](../../csharp/language-reference/keywords/virtual.md) a un blocco di codice**</span><span class="sxs-lookup"><span data-stu-id="ec03d-282">**❌ Adding the [checked](../../csharp/language-reference/keywords/virtual.md) keyword to a code block**</span></span>

   <span data-ttu-id="ec03d-283">Per effetto di questa modifica, il codice eseguito in precedenza può generare un'eccezione <xref:System.OverflowException> e non essere accettabile.</span><span class="sxs-lookup"><span data-stu-id="ec03d-283">This change may cause code that previously executed to throw an <xref:System.OverflowException> and is unacceptable.</span></span>

- <span data-ttu-id="ec03d-284">**❌ la rimozione di [parametri](../../csharp/language-reference/keywords/params.md) da un parametro**</span><span class="sxs-lookup"><span data-stu-id="ec03d-284">**❌ Removing [params](../../csharp/language-reference/keywords/params.md) from a parameter**</span></span>

- <span data-ttu-id="ec03d-285">**❌ modificare l'ordine in cui vengono generati gli eventi**</span><span class="sxs-lookup"><span data-stu-id="ec03d-285">**❌ Changing the order in which events are fired**</span></span>

  <span data-ttu-id="ec03d-286">Gli sviluppatori possono ragionevolmente aspettarsi che gli eventi vengano generati nello stesso ordine e il codice degli sviluppatori spesso dipende dall'ordine di generazione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="ec03d-286">Developers can reasonably expect events to fire in the same order, and developer code frequently depends on the order in which events are fired.</span></span>

- <span data-ttu-id="ec03d-287">**❌ la rimozione della generazione di un evento in un'azione specificata**</span><span class="sxs-lookup"><span data-stu-id="ec03d-287">**❌ Removing the raising of an event on a given action**</span></span>

- <span data-ttu-id="ec03d-288">**❌ la modifica del numero di volte in cui vengono chiamati gli eventi specificati**</span><span class="sxs-lookup"><span data-stu-id="ec03d-288">**❌ Changing the number of times given events are called**</span></span>

- <span data-ttu-id="ec03d-289">**❌ l'aggiunta del <xref:System.FlagsAttribute> a un tipo di enumerazione**</span><span class="sxs-lookup"><span data-stu-id="ec03d-289">**❌ Adding the <xref:System.FlagsAttribute> to an enumeration type**</span></span>
