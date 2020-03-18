---
title: Progettazione di costruttori
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400603"
---
# <a name="constructor-design"></a><span data-ttu-id="690c7-102">Progettazione di costruttori</span><span class="sxs-lookup"><span data-stu-id="690c7-102">Constructor Design</span></span>

<span data-ttu-id="690c7-103">Esistono due tipi di costruttori: costruttori di tipo e costruttori di istanza.</span><span class="sxs-lookup"><span data-stu-id="690c7-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="690c7-104">I costruttori di tipo sono statici e vengono eseguiti da CLR prima dell'utilizzo del tipo.</span><span class="sxs-lookup"><span data-stu-id="690c7-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="690c7-105">I costruttori di istanza vengono eseguiti quando viene creata un'istanza di un tipo.</span><span class="sxs-lookup"><span data-stu-id="690c7-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="690c7-106">I costruttori di tipo non possono accettare parametri.</span><span class="sxs-lookup"><span data-stu-id="690c7-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="690c7-107">I costruttori di istanza possono.</span><span class="sxs-lookup"><span data-stu-id="690c7-107">Instance constructors can.</span></span> <span data-ttu-id="690c7-108">I costruttori di istanza che non accettano parametri sono spesso denominati costruttori senza parametri.</span><span class="sxs-lookup"><span data-stu-id="690c7-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="690c7-109">I costruttori sono il modo più naturale per creare istanze di un tipo.</span><span class="sxs-lookup"><span data-stu-id="690c7-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="690c7-110">La maggior parte degli sviluppatori cercherà e tenterà di utilizzare un costruttore prima di prendere in considerazione modi alternativi di creazione di istanze (ad esempio metodi factory).</span><span class="sxs-lookup"><span data-stu-id="690c7-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="690c7-111">✔️ CONSIDER che fornisce costruttori semplici e idealmente predefiniti.</span><span class="sxs-lookup"><span data-stu-id="690c7-111">✔️ CONSIDER providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="690c7-112">Un costruttore semplice ha un numero molto ridotto di parametri e tutti i parametri sono primitive o enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="690c7-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="690c7-113">Tali costruttori semplici aumentano l'usabilità del framework.</span><span class="sxs-lookup"><span data-stu-id="690c7-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="690c7-114">✔️ CONSIDER utilizzando un metodo factory statico anziché un costruttore se la semantica dell'operazione desiderata non esegue direttamente il mapping alla costruzione di una nuova istanza o se le linee guida di progettazione del costruttore non sono innaturali.</span><span class="sxs-lookup"><span data-stu-id="690c7-114">✔️ CONSIDER using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="690c7-115">✔️ utilizzare i parametri del costruttore come tasti di scelta rapida per l'impostazione delle proprietà principali.</span><span class="sxs-lookup"><span data-stu-id="690c7-115">✔️ DO use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="690c7-116">Non dovrebbe esserci alcuna differenza nella semantica tra l'utilizzo del costruttore vuoto seguito da alcuni insiemi di proprietà e l'utilizzo di un costruttore con più argomenti.</span><span class="sxs-lookup"><span data-stu-id="690c7-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="690c7-117">✔️ utilizzare lo stesso nome per i parametri del costruttore e una proprietà se i parametri del costruttore vengono utilizzati per impostare semplicemente la proprietà.</span><span class="sxs-lookup"><span data-stu-id="690c7-117">✔️ DO use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="690c7-118">L'unica differenza tra tali parametri e le proprietà dovrebbe essere maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="690c7-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="690c7-119">✔️ lavoro minimo nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="690c7-119">✔️ DO minimal work in the constructor.</span></span>

<span data-ttu-id="690c7-120">I costruttori non devono eseguire molte operazioni diverse dall'acquisizione dei parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="690c7-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="690c7-121">Il costo di qualsiasi altra elaborazione deve essere ritardato fino a quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="690c7-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="690c7-122">✔️ generare eccezioni dai costruttori di istanza, se appropriato.</span><span class="sxs-lookup"><span data-stu-id="690c7-122">✔️ DO throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="690c7-123">✔️ dichiarare in modo esplicito il costruttore pubblico senza parametri nelle classi, se tale costruttore è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="690c7-123">✔️ DO explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="690c7-124">Se non si dichiarain modo esplicito i costruttori in un tipo, molti linguaggi (ad esempio, c'è) aggiungerà automaticamente un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="690c7-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="690c7-125">Le classi astratte ottengono un costruttore protetto.</span><span class="sxs-lookup"><span data-stu-id="690c7-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="690c7-126">L'aggiunta di un costruttore con parametri a una classe impedisce al compilatore di aggiungere il costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="690c7-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="690c7-127">Questo spesso provoca modifiche accidentali di rilievo.</span><span class="sxs-lookup"><span data-stu-id="690c7-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="690c7-128">❌AVOID definire in modo esplicito i costruttori senza parametri sugli struct.</span><span class="sxs-lookup"><span data-stu-id="690c7-128">❌ AVOID explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="690c7-129">In questo modo la creazione di matrici più veloce, perché se il costruttore senza parametri non è definito, non deve essere eseguito in ogni slot della matrice.</span><span class="sxs-lookup"><span data-stu-id="690c7-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="690c7-130">Si noti che molti compilatori, tra cui C , non consentono agli struct di avere costruttori senza parametri per questo motivo.</span><span class="sxs-lookup"><span data-stu-id="690c7-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="690c7-131">❌AVOID chiamando membri virtuali su un oggetto all'interno del relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="690c7-131">❌ AVOID calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="690c7-132">La chiamata a un membro virtuale causerà la chiamata dell'override più derivato, anche se il costruttore del tipo più derivato non è ancora stato eseguito completamente.</span><span class="sxs-lookup"><span data-stu-id="690c7-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="690c7-133">Linee guida per i costruttori di tipoType Constructor Guidelines</span><span class="sxs-lookup"><span data-stu-id="690c7-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="690c7-134">✔️ rendere privati i costruttori statici.</span><span class="sxs-lookup"><span data-stu-id="690c7-134">✔️ DO make static constructors private.</span></span>

<span data-ttu-id="690c7-135">Un costruttore statico, denominato anche costruttore di classe, viene utilizzato per inizializzare un tipo.</span><span class="sxs-lookup"><span data-stu-id="690c7-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="690c7-136">CLR chiama il costruttore statico prima che venga creata la prima istanza del tipo o vengano chiamati tutti i membri statici su tale tipo.</span><span class="sxs-lookup"><span data-stu-id="690c7-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="690c7-137">L'utente non ha alcun controllo su quando viene chiamato il costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="690c7-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="690c7-138">Se un costruttore statico non è privato, può essere chiamato da codice diverso da CLR.</span><span class="sxs-lookup"><span data-stu-id="690c7-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="690c7-139">A seconda delle operazioni eseguite nel costruttore, ciò può causare un comportamento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="690c7-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="690c7-140">Il compilatore di C'è forza i costruttori statici per essere privati.</span><span class="sxs-lookup"><span data-stu-id="690c7-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="690c7-141">❌DO NOT generare eccezioni da costruttori statici.</span><span class="sxs-lookup"><span data-stu-id="690c7-141">❌ DO NOT throw exceptions from static constructors.</span></span>

<span data-ttu-id="690c7-142">Se viene generata un'eccezione da un costruttore di tipo, il tipo non è utilizzabile nel dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="690c7-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="690c7-143">✔️ CONSIDER inizializzare i campi statici inline anziché utilizzare in modo esplicito i costruttori statici, perché il runtime è in grado di ottimizzare le prestazioni dei tipi che non dispongono di un costruttore statico definito in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="690c7-143">✔️ CONSIDER initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="690c7-144">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="690c7-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="690c7-145">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="690c7-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="690c7-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="690c7-146">See also</span></span>

- [<span data-ttu-id="690c7-147">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="690c7-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="690c7-148">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="690c7-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
