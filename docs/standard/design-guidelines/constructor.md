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
author: KrzysztofCwalina
ms.openlocfilehash: 074aa391b71257584a01171e95da7472354cdc2c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746785"
---
# <a name="constructor-design"></a><span data-ttu-id="24cdf-102">Progettazione di costruttori</span><span class="sxs-lookup"><span data-stu-id="24cdf-102">Constructor Design</span></span>
<span data-ttu-id="24cdf-103">Esistono due tipi di costruttori: digitare costruttori e i costruttori di istanza.</span><span class="sxs-lookup"><span data-stu-id="24cdf-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="24cdf-104">I costruttori di tipi sono statici e vengono eseguiti da CLR prima che venga utilizzato il tipo.</span><span class="sxs-lookup"><span data-stu-id="24cdf-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="24cdf-105">Costruttori di istanza eseguire quando viene creata un'istanza di un tipo.</span><span class="sxs-lookup"><span data-stu-id="24cdf-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="24cdf-106">I costruttori di tipi non accettano alcun parametro.</span><span class="sxs-lookup"><span data-stu-id="24cdf-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="24cdf-107">Costruttori di istanza possono.</span><span class="sxs-lookup"><span data-stu-id="24cdf-107">Instance constructors can.</span></span> <span data-ttu-id="24cdf-108">Costruttori di istanze che non accettano alcun parametro vengono spesso definiti costruttori senza parametri.</span><span class="sxs-lookup"><span data-stu-id="24cdf-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>  
  
 <span data-ttu-id="24cdf-109">I costruttori sono il modo più semplice per creare istanze di un tipo.</span><span class="sxs-lookup"><span data-stu-id="24cdf-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="24cdf-110">La maggior parte degli sviluppatori saranno ricerca e provare a usare un costruttore prima che essi prendere in considerazione modi alternativi per la creazione di istanze (ad esempio, metodi factory).</span><span class="sxs-lookup"><span data-stu-id="24cdf-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="24cdf-111">**✓ CONSIDER** fornendo semplice, in teoria predefiniti, costruttori.</span><span class="sxs-lookup"><span data-stu-id="24cdf-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="24cdf-112">Un costruttore semplice ha un numero molto ridotto di parametri e tutti i parametri sono primitive o enum.</span><span class="sxs-lookup"><span data-stu-id="24cdf-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="24cdf-113">Questi costruttori semplici aumentano l'utilizzabilità del framework.</span><span class="sxs-lookup"><span data-stu-id="24cdf-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="24cdf-114">**✓ CONSIDER** utilizzando un metodo factory statico invece di un costruttore se la semantica dell'operazione desiderata non eseguano il mapping direttamente per la costruzione di una nuova istanza o seguendo le linee guida progettazione costruttore ritiene non naturale.</span><span class="sxs-lookup"><span data-stu-id="24cdf-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="24cdf-115">**✓ DO** utilizzare i parametri del costruttore come tasti di scelta rapida per l'impostazione delle proprietà principali.</span><span class="sxs-lookup"><span data-stu-id="24cdf-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="24cdf-116">Non vi sarà alcuna differenza semantica tra usando il costruttore vuoto seguito da alcuni set di proprietà e usando un costruttore con più argomenti.</span><span class="sxs-lookup"><span data-stu-id="24cdf-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="24cdf-117">**✓ DO** utilizzare lo stesso nome per i parametri del costruttore e una proprietà, se vengono utilizzati i parametri del costruttore è sufficiente impostare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="24cdf-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="24cdf-118">L'unica differenza tra tali parametri e le proprietà debba essere maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="24cdf-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="24cdf-119">**✓ DO** lavoro minimo nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="24cdf-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="24cdf-120">I costruttori non occorre eseguire la quantità di lavoro diverso da acquisizione i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="24cdf-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="24cdf-121">Il costo di qualsiasi altra elaborazione dovrebbe risultare ritardato fino al necessario.</span><span class="sxs-lookup"><span data-stu-id="24cdf-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="24cdf-122">**✓ DO** generare eccezioni da costruttori di istanza, se appropriato.</span><span class="sxs-lookup"><span data-stu-id="24cdf-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="24cdf-123">**Segno di spunta si** dichiarare in modo esplicito il costruttore pubblico senza parametri nelle classi, se tale costruttore è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="24cdf-123">**✓ DO** explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="24cdf-124">Se si non dichiarare costruttori in modo esplicito su un tipo, molti linguaggi (ad esempio C#) verrà aggiunto automaticamente un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="24cdf-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="24cdf-125">(Le classi astratte ottenere un costruttore protetto).</span><span class="sxs-lookup"><span data-stu-id="24cdf-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="24cdf-126">Aggiunta di un costruttore con parametri a una classe impedisce al compilatore di aggiungere il costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="24cdf-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="24cdf-127">Ciò spesso causa modifiche di rilievo accidentale.</span><span class="sxs-lookup"><span data-stu-id="24cdf-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="24cdf-128">**X evitare** definirne esplicitamente costruttori senza parametri in struct.</span><span class="sxs-lookup"><span data-stu-id="24cdf-128">**X AVOID** explicitly defining parameterless constructors on structs.</span></span>  
  
 <span data-ttu-id="24cdf-129">In questo modo la creazione della matrice meno tempo, in quanto se non è definito il costruttore senza parametri, non deve essere eseguito su ogni slot nella matrice.</span><span class="sxs-lookup"><span data-stu-id="24cdf-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="24cdf-130">Si noti che molti compilatori, tra cui c#, non consentano strutture possono avere costruttori senza parametri per questo motivo.</span><span class="sxs-lookup"><span data-stu-id="24cdf-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="24cdf-131">**X AVOID** chiamare membri virtuali su un oggetto all'interno di relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="24cdf-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="24cdf-132">La chiamata a un membro virtuale provocherà la sostituzione più derivata da chiamare, anche se il costruttore del tipo più derivato non è stato completamente eseguito ancora.</span><span class="sxs-lookup"><span data-stu-id="24cdf-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="24cdf-133">Linee guida di costruttore di tipo</span><span class="sxs-lookup"><span data-stu-id="24cdf-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="24cdf-134">**✓ DO** rendere privato costruttori statici.</span><span class="sxs-lookup"><span data-stu-id="24cdf-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="24cdf-135">Un costruttore statico, denominato anche costruttore di classe, viene utilizzato per inizializzare un tipo.</span><span class="sxs-lookup"><span data-stu-id="24cdf-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="24cdf-136">CLR chiama il costruttore statico prima che venga creata la prima istanza del tipo o qualsiasi membro statico sul quel tipo viene chiamati.</span><span class="sxs-lookup"><span data-stu-id="24cdf-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="24cdf-137">L'utente non ha alcun controllo su quando viene chiamato il costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="24cdf-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="24cdf-138">Se un costruttore statico non è privato, può essere chiamata dal codice diverso da CLR.</span><span class="sxs-lookup"><span data-stu-id="24cdf-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="24cdf-139">A seconda delle operazioni eseguite nel costruttore, ciò può provocare comportamenti imprevisti.</span><span class="sxs-lookup"><span data-stu-id="24cdf-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="24cdf-140">Il compilatore C# forza i costruttori statici come privato.</span><span class="sxs-lookup"><span data-stu-id="24cdf-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="24cdf-141">**X DO NOT** generare eccezioni da costruttori statici.</span><span class="sxs-lookup"><span data-stu-id="24cdf-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="24cdf-142">Se viene generata un'eccezione da un costruttore di tipo, il tipo non è utilizzabile nel dominio dell'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="24cdf-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="24cdf-143">**✓ CONSIDER** inizializzando i campi statici inline anziché in modo esplicito i costruttori statici, perché il runtime è in grado di ottimizzare le prestazioni dei tipi che non dispongono di un costruttore statico definito in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="24cdf-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="24cdf-144">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="24cdf-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="24cdf-145">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="24cdf-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24cdf-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24cdf-146">See also</span></span>

- [<span data-ttu-id="24cdf-147">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="24cdf-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="24cdf-148">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="24cdf-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
