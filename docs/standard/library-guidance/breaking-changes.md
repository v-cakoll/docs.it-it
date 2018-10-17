---
title: Modifiche di rilievo apportate e librerie .NET
description: Le procedure consigliate per lo spostamento delle modifiche di rilievo durante la creazione di librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 83c01fdad7d836877bf692b87eeb0230219ded36
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370062"
---
# <a name="breaking-changes"></a><span data-ttu-id="d5138-103">Modifiche di rilievo</span><span class="sxs-lookup"><span data-stu-id="d5138-103">Breaking changes</span></span>

<span data-ttu-id="d5138-104">È importante per una libreria .NET trovare un equilibrio tra la stabilità per gli utenti esistenti e l'innovazione per il futuro.</span><span class="sxs-lookup"><span data-stu-id="d5138-104">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="d5138-105">Gli autori di libreria fare affidamento a refactoring e rethinking codice fino a quando non è perfetto, ma gli utenti esistenti di rilievo ha un impatto negativo, in particolare per le librerie di basso livello.</span><span class="sxs-lookup"><span data-stu-id="d5138-105">Library authors lean towards refactoring and rethinking code until it's perfect, but breaking your existing users has a negative impact, especially for low-level libraries.</span></span>

## <a name="project-types-and-breaking-changes"></a><span data-ttu-id="d5138-106">Tipi di progetto e le modifiche di rilievo</span><span class="sxs-lookup"><span data-stu-id="d5138-106">Project types and breaking changes</span></span>

<span data-ttu-id="d5138-107">Utilizzo di una libreria dalla community .NET cambia l'effetto delle modifiche di rilievo per sviluppatori di dati gestito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d5138-107">How a library is used by the .NET community changes the effect of breaking changes on end-user developers.</span></span>

* <span data-ttu-id="d5138-108">**Basso e medio livello librerie** come un serializzatore, il parser HTML, mapper relazionale a oggetti di database o framework web sono i più interessati da modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="d5138-108">**Low and middle-level libraries** like a serializer, HTML parser, database object-relational mapper, or web framework are the most affected by breaking changes.</span></span>

  <span data-ttu-id="d5138-109">Blocchi predefiniti vengono utilizzati dagli sviluppatori per l'utente finale per compilare applicazioni e da altre librerie come dipendenze di NuGet.</span><span class="sxs-lookup"><span data-stu-id="d5138-109">Building block packages are used by end-user developers to build applications, and by other libraries as NuGet dependencies.</span></span> <span data-ttu-id="d5138-110">Ad esempio, si sta creando un'applicazione e si usa un client open source per chiamare un servizio web.</span><span class="sxs-lookup"><span data-stu-id="d5138-110">For example, you're building an application and are using an open-source client to call a web service.</span></span> <span data-ttu-id="d5138-111">Un aggiornamento di rilievo a una dipendenza che usa il client non che è possibile risolvere.</span><span class="sxs-lookup"><span data-stu-id="d5138-111">A breaking update to a dependency the client uses isn't something you can fix.</span></span> <span data-ttu-id="d5138-112">Questo è il client open source che deve essere modificato e si ha alcun controllo su di esso.</span><span class="sxs-lookup"><span data-stu-id="d5138-112">It's the open-source client that needs to be changed and you have no control over it.</span></span> <span data-ttu-id="d5138-113">È necessario trovare versioni compatibili di librerie o inviare una correzione per la libreria client e attendere una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="d5138-113">You have to find compatible versions of the libraries or submit a fix to the client library and wait for a new version.</span></span> <span data-ttu-id="d5138-114">La situazione peggiore è se si desidera utilizzare due librerie che dipendono dalle versioni incompatibili di una libreria di terza.</span><span class="sxs-lookup"><span data-stu-id="d5138-114">The worst-case situation is if you want to use two libraries that depend on mutually incompatible versions of a third library.</span></span>

* <span data-ttu-id="d5138-115">**Librerie di alto livello** come una suite di interfaccia utente sono meno sensibili alle modifiche di rilievo controlli.</span><span class="sxs-lookup"><span data-stu-id="d5138-115">**High-level libraries** like a suite of UI controls are less sensitive to breaking changes.</span></span>

  <span data-ttu-id="d5138-116">Librerie di alto livello vengono fatto riferimento diretto in un'applicazione dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="d5138-116">High-level libraries are directly referenced in an end-user application.</span></span> <span data-ttu-id="d5138-117">Se si verificano modifiche di rilievo, lo sviluppatore può scegliere di aggiornare la versione più recente oppure può modificare l'applicazione per lavorare con le modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="d5138-117">If breaking changes occur, the developer can choose to update to the latest version, or can modify their application to work with the breaking change.</span></span>

<span data-ttu-id="d5138-118">**Eseguire operazioni ✔️** considerare come verrà usata la libreria.</span><span class="sxs-lookup"><span data-stu-id="d5138-118">**✔️ DO** think about how your library will be used.</span></span> <span data-ttu-id="d5138-119">Quale effetto avrà le modifiche di rilievo su applicazioni e librerie che usano?</span><span class="sxs-lookup"><span data-stu-id="d5138-119">What effect will breaking changes have on applications and libraries that use it?</span></span>

<span data-ttu-id="d5138-120">**Eseguire operazioni ✔️** ridurre al minimo le modifiche di rilievo quando si sviluppa una libreria .NET di basso livello.</span><span class="sxs-lookup"><span data-stu-id="d5138-120">**✔️ DO** minimize breaking changes when developing a low-level .NET library.</span></span>

<span data-ttu-id="d5138-121">**Provare a ✔️** pubblicazione principale riscrittura di una raccolta come un nuovo pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="d5138-121">**✔️ CONSIDER** publishing a major rewrite of a library as a new NuGet package.</span></span>

## <a name="types-of-breaking-changes"></a><span data-ttu-id="d5138-122">Tipi di modifiche di rilievo</span><span class="sxs-lookup"><span data-stu-id="d5138-122">Types of breaking changes</span></span>

<span data-ttu-id="d5138-123">Modifiche di rilievo apportate possono essere suddivise in categorie diverse e non sono altrettanto con impatto elevati.</span><span class="sxs-lookup"><span data-stu-id="d5138-123">Breaking changes fall into different categories and aren't equally impactful.</span></span>

### <a name="source-breaking-change"></a><span data-ttu-id="d5138-124">Modifica di rilievo di origine</span><span class="sxs-lookup"><span data-stu-id="d5138-124">Source breaking change</span></span>

<span data-ttu-id="d5138-125">Un'origine di modifica di rilievo non influisce sull'esecuzione del programma ma causerà errori di compilazione la volta successiva che l'applicazione viene ricompilata.</span><span class="sxs-lookup"><span data-stu-id="d5138-125">A source breaking change doesn't affect program execution but will cause compilation errors the next time the application is recompiled.</span></span> <span data-ttu-id="d5138-126">Ad esempio, un nuovo overload può creare ambiguità nelle chiamate al metodo che erano in precedenza non ambigue, o un parametro rinominato interromperà i chiamanti che utilizzano parametri denominati.</span><span class="sxs-lookup"><span data-stu-id="d5138-126">For example, a new overload can create an ambiguity in method calls that were unambiguous previously, or a renamed parameter will break callers that use named parameters.</span></span>

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

<span data-ttu-id="d5138-127">Poiché un'origine di modifica di rilievo è dannosa solo quando gli sviluppatori di compilare nuovamente le proprie applicazioni, è meno dirompenti modifica di rilievo.</span><span class="sxs-lookup"><span data-stu-id="d5138-127">Because a source breaking change is only harmful when developers recompile their applications, it's the least disruptive breaking change.</span></span> <span data-ttu-id="d5138-128">Gli sviluppatori possono risolvere facilmente il proprio codice di origine interrotto.</span><span class="sxs-lookup"><span data-stu-id="d5138-128">Developers can fix their own broken source code easily.</span></span>

### <a name="behavior-breaking-change"></a><span data-ttu-id="d5138-129">Modifica di rilievo di comportamento</span><span class="sxs-lookup"><span data-stu-id="d5138-129">Behavior breaking change</span></span>

<span data-ttu-id="d5138-130">Modifiche del comportamento sono il tipo più comune di modifica di rilievo: quasi qualsiasi modifica nel comportamento è stato possibile interrompere un utente.</span><span class="sxs-lookup"><span data-stu-id="d5138-130">Behavior changes are the most common type of breaking change: almost any change in behavior could break someone.</span></span> <span data-ttu-id="d5138-131">Modifiche alla raccolta, ad esempio le firme di metodo, le eccezioni generate o di input o output formati di dati, tutto da influire negativamente sui consumer della libreria.</span><span class="sxs-lookup"><span data-stu-id="d5138-131">Changes to your library, such as method signatures, exceptions thrown or input or output data formats, could all negatively impact your library consumers.</span></span> <span data-ttu-id="d5138-132">Anche una correzione di bug può qualificare modifiche a posteriori se gli utenti si basavano sui comportamenti interrotti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d5138-132">Even a bug fix can qualify as a breaking change if users relied on the previously broken behavior.</span></span>

<span data-ttu-id="d5138-133">Aggiunta di funzionalità e comportamenti non corretti di miglioramento è positivo, ma senza care può risultare molto difficile per gli utenti esistenti eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d5138-133">Adding features and improving bad behaviors is a good thing, but without care it can make it very hard for existing users to upgrade.</span></span> <span data-ttu-id="d5138-134">Uno degli approcci per aiutare gli sviluppatori di affrontare comportamento modifiche di rilievo è per nasconderle dietro le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d5138-134">One approach to helping developers deal with behavior breaking changes is to hide them behind settings.</span></span> <span data-ttu-id="d5138-135">Le impostazioni consentono agli sviluppatori di aggiornare la versione più recente della libreria allo stesso tempo scelta acconsentire o rifiutare le modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="d5138-135">Settings let developers update to the latest version of your library while at the same time choosing to opt in or opt out of breaking changes.</span></span> <span data-ttu-id="d5138-136">Questa strategia consente agli sviluppatori di rimanere aggiornati, consentendo al contempo il proprio codice dispendiosa in termini di adattare nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="d5138-136">This strategy lets developers stay up to date while letting their consuming code adapt over time.</span></span>

<span data-ttu-id="d5138-137">Ad esempio, ASP.NET Core MVC include il concetto di una [versione di compatibilità](/aspnet/core/mvc/compatibility-version) che consente di modificare la funzionalità abilitata e disabilitata in `MvcOptions`.</span><span class="sxs-lookup"><span data-stu-id="d5138-137">For example, ASP.NET Core MVC has the concept of a [compatibility version](/aspnet/core/mvc/compatibility-version) that modifies the features enabled and disabled on `MvcOptions`.</span></span>

<span data-ttu-id="d5138-138">**Provare a ✔️** lasciando le nuove funzionalità per impostazione predefinita, se interessa gli utenti esistenti e consentono agli sviluppatori di acconsentire esplicitamente alla funzionalità con un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="d5138-138">**✔️ CONSIDER** leaving new features off by default, if they affect existing users, and let developers opt in to the feature with a setting.</span></span>

### <a name="binary-breaking-change"></a><span data-ttu-id="d5138-139">Modifica di rilievo binario</span><span class="sxs-lookup"><span data-stu-id="d5138-139">Binary breaking change</span></span>

<span data-ttu-id="d5138-140">Un file binario modifica di rilievo accade quando si modifica l'API pubblica della libreria, in modo che gli assembly compilati con le versioni precedenti della libreria non sono più in grado di chiamare l'API.</span><span class="sxs-lookup"><span data-stu-id="d5138-140">A binary breaking change happens when you change the public API of your library, so assemblies compiled against older versions of your library are no longer able to call the API.</span></span> <span data-ttu-id="d5138-141">Ad esempio, la modifica di firma del metodo aggiungendo un nuovo parametro causa gli assembly compilati con la versione meno recente della libreria generare un <xref:System.MissingMethodException>.</span><span class="sxs-lookup"><span data-stu-id="d5138-141">For example, changing a method's signature by adding a new parameter will cause assemblies compiled against the older version of the library to throw a <xref:System.MissingMethodException>.</span></span>

<span data-ttu-id="d5138-142">Un file binario modifica di rilievo consentono inoltre di suddividere un' **intero assembly**.</span><span class="sxs-lookup"><span data-stu-id="d5138-142">A binary breaking change can also break an **entire assembly**.</span></span> <span data-ttu-id="d5138-143">Ridenominazione di un assembly con `AssemblyName` modificheranno l'identità dell'assembly, verrà aggiunta, rimozione o Modifica chiave denominazione sicuro dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d5138-143">Renaming an assembly with `AssemblyName` will change the assembly's identity, as will adding, removing, or changing the assembly's strong naming key.</span></span> <span data-ttu-id="d5138-144">Una modifica di identità di un assembly può compromettere tutto il codice compilato che lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="d5138-144">A change of an assembly's identity will break all compiled code that uses it.</span></span>

<span data-ttu-id="d5138-145">**NON ❌** cambiare un nome di assembly.</span><span class="sxs-lookup"><span data-stu-id="d5138-145">**❌ DO NOT** change an assembly name.</span></span>

<span data-ttu-id="d5138-146">**NON ❌** aggiungere, rimuovere o modificare la chiave di denominazione intenso.</span><span class="sxs-lookup"><span data-stu-id="d5138-146">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

<span data-ttu-id="d5138-147">**Provare a ✔️** usando le classi base astratte anziché le interfacce.</span><span class="sxs-lookup"><span data-stu-id="d5138-147">**✔️ CONSIDER** using abstract base classes instead of interfaces.</span></span>

> <span data-ttu-id="d5138-148">Aggiunta di qualsiasi elemento a un'interfaccia causerà esistenti i tipi che implementano l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d5138-148">Adding anything to an interface will cause existing types that implement it to fail.</span></span> <span data-ttu-id="d5138-149">Una classe base astratta consente di aggiungere un'implementazione virtuale predefinito.</span><span class="sxs-lookup"><span data-stu-id="d5138-149">An abstract base class allows you to add a default virtual implementation.</span></span>

<span data-ttu-id="d5138-150">**✔️ si consiglia** posizionare il <xref:System.ObsoleteAttribute> su tipi e membri che si intendono rimuovere.</span><span class="sxs-lookup"><span data-stu-id="d5138-150">**✔️ CONSIDER** placing the <xref:System.ObsoleteAttribute> on types and members that you intend to remove.</span></span> <span data-ttu-id="d5138-151">L'attributo deve avere le istruzioni per l'aggiornamento del codice non è più usare l'API obsoleta.</span><span class="sxs-lookup"><span data-stu-id="d5138-151">The attribute should have instructions for updating code to no longer use the obsolete API.</span></span>

> <span data-ttu-id="d5138-152">Il codice che chiama i tipi e metodi con il <xref:System.ObsoleteAttribute> genererà un avviso di compilazione con il messaggio fornito all'attributo.</span><span class="sxs-lookup"><span data-stu-id="d5138-152">Code that calls types and methods with the <xref:System.ObsoleteAttribute> will generate a build warning with the message supplied to the attribute.</span></span> <span data-ttu-id="d5138-153">Gli avvisi consentono di chi utilizza il tempo di superficie API obsoleto per eseguire la migrazione in modo che quando viene rimossa l'API obsoleta, la maggior parte non sono più usarlo.</span><span class="sxs-lookup"><span data-stu-id="d5138-153">The warnings give people who use the obsolete API surface time to migrate so that when the obsolete API is removed, most are no longer using it.</span></span>

```csharp
public class Document
{
    [Obsolete("LoadDocument(string) is obsolete. Use LoadDocument(Uri) instead.")]
    public static Document LoadDocument(string uri)
    {
        return LoadDocument(new Uri(uri));
    }

    public static Document LoadDocument(Uri uri)
    {
        // Load the document
    }
}
```

## <a name="see-also"></a><span data-ttu-id="d5138-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5138-154">See also</span></span>

* [<span data-ttu-id="d5138-155">Considerazioni sulla versione e aggiornamento per gli sviluppatori c#</span><span class="sxs-lookup"><span data-stu-id="d5138-155">Version and update considerations for C# developers</span></span>](../../csharp/whats-new/version-update-considerations.md)
* [<span data-ttu-id="d5138-156">Una Guida definitiva per API-ultime modifiche in .NET</span><span class="sxs-lookup"><span data-stu-id="d5138-156">A definitive guide to API-breaking changes in .NET</span></span>](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
* [<span data-ttu-id="d5138-157">Regole di modifica di rilievo CoreFX</span><span class="sxs-lookup"><span data-stu-id="d5138-157">CoreFX Breaking Change Rules</span></span>](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
[<span data-ttu-id="d5138-158">Precedente</span><span class="sxs-lookup"><span data-stu-id="d5138-158">Previous</span></span>](./versioning.md)
