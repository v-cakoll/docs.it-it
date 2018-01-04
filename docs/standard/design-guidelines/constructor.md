---
title: Progettazione di costruttori
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 66a297ed035f5afde06913b89f1f92dee5745f48
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="constructor-design"></a><span data-ttu-id="3cdfe-102">Progettazione di costruttori</span><span class="sxs-lookup"><span data-stu-id="3cdfe-102">Constructor Design</span></span>
<span data-ttu-id="3cdfe-103">Esistono due tipi di costruttori: tipo di costruttori e dei costruttori di istanza.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="3cdfe-104">Costruttori di tipo sono statici e vengono eseguiti da CLR prima che venga utilizzato il tipo.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="3cdfe-105">Costruttori di istanza eseguire quando viene creata un'istanza di un tipo.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="3cdfe-106">Costruttori di tipo non possono accettare parametri.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="3cdfe-107">Costruttori di istanza possono.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-107">Instance constructors can.</span></span> <span data-ttu-id="3cdfe-108">Costruttori di istanza che non accettano parametri vengono chiamati i costruttori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-108">Instance constructors that don’t take any parameters are often called default constructors.</span></span>  
  
 <span data-ttu-id="3cdfe-109">I costruttori sono il modo più semplice per creare istanze di un tipo.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="3cdfe-110">La maggior parte degli sviluppatori verranno cercare e tenta di utilizzare un costruttore prima ritengano modi alternativi per la creazione di istanze (ad esempio i metodi factory).</span><span class="sxs-lookup"><span data-stu-id="3cdfe-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="3cdfe-111">**Provare a ✓** fornendo semplice, in teoria predefiniti, costruttori.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="3cdfe-112">Un costruttore semplice dispone di un numero molto ridotto di parametri e tutti i parametri sono primitive o enum.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="3cdfe-113">Tali costruttori semplici aumentano l'utilizzabilità di framework.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="3cdfe-114">**Provare a ✓** utilizzando un metodo factory statico invece di un costruttore se la semantica dell'operazione desiderata non eseguano il mapping direttamente per la costruzione di una nuova istanza o seguendo le linee guida progettazione costruttore abbia non naturale.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="3cdfe-115">**✓ SI** utilizzare i parametri del costruttore come tasti di scelta rapida per l'impostazione delle proprietà principali.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="3cdfe-116">Non deve esistere alcuna differenza nella semantica tra utilizzando il costruttore vuoto seguito da un set di proprietà e l'utilizzo di un costruttore con più argomenti.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="3cdfe-117">**✓ SI** utilizzare lo stesso nome per i parametri del costruttore e una proprietà, se vengono utilizzati i parametri del costruttore è sufficiente impostare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="3cdfe-118">L'unica differenza tra tali parametri e le proprietà debba essere maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="3cdfe-119">**✓ SI** lavoro minimo nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="3cdfe-120">I costruttori non memorizzare la quantità di lavoro diverso da acquisizione i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="3cdfe-121">Il costo di qualsiasi altra elaborazione deve essere ritardato fino a quando non necessaria.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="3cdfe-122">**✓ SI** generare eccezioni da costruttori di istanza, se appropriato.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="3cdfe-123">**✓ SI** dichiarare in modo esplicito il costruttore predefinito pubblico nelle classi, se tale costruttore è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-123">**✓ DO** explicitly declare the public default constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="3cdfe-124">Se si non dichiarano costruttori in modo esplicito su un tipo, molti linguaggi (ad esempio c#) aggiungerà automaticamente un costruttore predefinito pubblico.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public default constructor.</span></span> <span data-ttu-id="3cdfe-125">(Le classi astratte ottenere un costruttore protetto).</span><span class="sxs-lookup"><span data-stu-id="3cdfe-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="3cdfe-126">Aggiunta di un costruttore con parametri a una classe impedisce al compilatore di aggiungere il costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-126">Adding a parameterized constructor to a class prevents the compiler from adding the default constructor.</span></span> <span data-ttu-id="3cdfe-127">In questo modo spesso modifiche accidentali.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="3cdfe-128">**X evitare** definire in modo esplicito i costruttori predefiniti sulle strutture.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-128">**X AVOID** explicitly defining default constructors on structs.</span></span>  
  
 <span data-ttu-id="3cdfe-129">In questo modo la creazione della matrice più velocemente, in quanto se non è definito il costruttore predefinito, non deve essere eseguito su ogni slot nella matrice.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-129">This makes array creation faster, because if the default constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="3cdfe-130">Si noti che molti compilatori, inclusi c#, non consentano strutture possono contenere costruttori senza parametri per questo motivo.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="3cdfe-131">**X evitare** chiamando i membri virtuali su un oggetto all'interno di costruttore.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="3cdfe-132">La chiamata a un membro virtuale causerà la sostituzione più derivata da chiamare, anche se il costruttore del tipo più derivato non è stato completamente eseguito ancora.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="3cdfe-133">Linee guida di costruttore di tipo</span><span class="sxs-lookup"><span data-stu-id="3cdfe-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="3cdfe-134">**✓ SI** rendere privato costruttori statici.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="3cdfe-135">Un costruttore statico, denominato anche costruttore di classe, viene utilizzato per inizializzare un tipo.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="3cdfe-136">CLR chiama il costruttore statico prima viene creata la prima istanza del tipo o i membri statici su tale tipo sono chiamati.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="3cdfe-137">L'utente non dispone di alcun controllo sulla quando viene chiamato il costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="3cdfe-138">Se un costruttore statico non è privato, può essere chiamato da codice diverso da CLR.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="3cdfe-139">A seconda delle operazioni eseguite nel costruttore, questo può causare comportamenti imprevisti.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="3cdfe-140">Il compilatore c# forza costruttori statici come privato.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="3cdfe-141">**X non** generare eccezioni da costruttori statici.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="3cdfe-142">Se viene generata un'eccezione da un costruttore di tipo, il tipo non è utilizzabile nel dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="3cdfe-143">**Provare a ✓** inizializzare i campi statici inline anziché in modo esplicito i costruttori statici, perché il runtime è in grado di ottimizzare le prestazioni dei tipi che non dispongono di un costruttore statico definito in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="3cdfe-144">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="3cdfe-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3cdfe-145">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="3cdfe-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cdfe-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cdfe-146">See Also</span></span>  
 [<span data-ttu-id="3cdfe-147">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="3cdfe-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="3cdfe-148">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="3cdfe-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
