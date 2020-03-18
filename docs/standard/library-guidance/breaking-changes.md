---
title: Modifiche di rilievo e librerie .NET
description: Procedure consigliate per esplorare le modifiche di rilievo durante la creazione di librerie .NET.
ms.date: 10/02/2018
ms.openlocfilehash: 2cbd9e0a818b52aede6c9b1f60fdf52dcbd7b96f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79400421"
---
# <a name="breaking-changes"></a><span data-ttu-id="2dbd7-103">Modifiche di rilievo</span><span class="sxs-lookup"><span data-stu-id="2dbd7-103">Breaking changes</span></span>

<span data-ttu-id="2dbd7-104">Per una libreria .NET è importante trovare un equilibrio tra la stabilità per gli utenti esistenti e l'innovazione per il futuro.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-104">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="2dbd7-105">Gli autori di libreria effettuano il refactoring e rielaborano il codice finché non è perfetto. Interrompere gli utenti esistenti ha tuttavia un impatto negativo, soprattutto per le librerie di basso livello.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-105">Library authors lean towards refactoring and rethinking code until it's perfect, but breaking your existing users has a negative impact, especially for low-level libraries.</span></span>

## <a name="project-types-and-breaking-changes"></a><span data-ttu-id="2dbd7-106">Tipi di progetto e modifiche di rilievo</span><span class="sxs-lookup"><span data-stu-id="2dbd7-106">Project types and breaking changes</span></span>

<span data-ttu-id="2dbd7-107">A seconda di come una libreria viene usata dalla community .NET, cambia l'effetto delle modifiche di rilievo sullo sviluppo per utenti finali.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-107">How a library is used by the .NET community changes the effect of breaking changes on end-user developers.</span></span>

- <span data-ttu-id="2dbd7-108">Le **librerie di basso e medio livello**, ad esempio un serializzatore, il parser HTML, un Object-Relational Mapper (ORM) di database o un framework Web, sono gli elementi che più risentono delle modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-108">**Low and middle-level libraries** like a serializer, HTML parser, database object-relational mapper, or web framework are the most affected by breaking changes.</span></span>

  <span data-ttu-id="2dbd7-109">I pacchetti di blocchi predefiniti sono usati dagli sviluppatori per utenti finali per compilare le applicazioni, e da altre librerie come dipendenze NuGet.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-109">Building block packages are used by end-user developers to build applications, and by other libraries as NuGet dependencies.</span></span> <span data-ttu-id="2dbd7-110">Ad esempio, un'applicazione viene compilata usando un client open source per chiamare un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-110">For example, you're building an application and are using an open-source client to call a web service.</span></span> <span data-ttu-id="2dbd7-111">Un aggiornamento di rilievo a una dipendenza usata dal client non è un'operazione possibile.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-111">A breaking update to a dependency the client uses isn't something you can fix.</span></span> <span data-ttu-id="2dbd7-112">È il client open source che deve essere modificato, sul quale non si ha controllo.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-112">It's the open-source client that needs to be changed and you have no control over it.</span></span> <span data-ttu-id="2dbd7-113">È necessario trovare versioni compatibili di librerie o inviare una correzione alla libreria client e attendere una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-113">You have to find compatible versions of the libraries or submit a fix to the client library and wait for a new version.</span></span> <span data-ttu-id="2dbd7-114">Il caso peggiore è quando si vogliono usare due librerie che dipendono reciprocamente da versioni incompatibili di una terza libreria.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-114">The worst-case situation is if you want to use two libraries that depend on mutually incompatible versions of a third library.</span></span>

- <span data-ttu-id="2dbd7-115">Le **librerie di alto livello**, ad esempio una suite di controlli dell'interfaccia utente, sono meno sensibili alle modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-115">**High-level libraries** like a suite of UI controls are less sensitive to breaking changes.</span></span>

  <span data-ttu-id="2dbd7-116">Le librerie di alto livello hanno un riferimento diretto all'interno di un'applicazione per utenti finali.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-116">High-level libraries are directly referenced in an end-user application.</span></span> <span data-ttu-id="2dbd7-117">In caso di modifiche di rilievo, lo sviluppatore può scegliere di eseguire l'aggiornamento alla versione più recente oppure può modificare l'applicazione per accettare le modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-117">If breaking changes occur, the developer can choose to update to the latest version, or can modify their application to work with the breaking change.</span></span>

<span data-ttu-id="2dbd7-118">✔️ CONSIDERARE quale sarà l'uso della libreria.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-118">✔️ DO think about how your library will be used.</span></span> <span data-ttu-id="2dbd7-119">Valutare l'effetto che le modifiche di rilievo avranno sulle applicazioni e sulle librerie in cui è usata la libreria.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-119">What effect will breaking changes have on applications and libraries that use it?</span></span>

<span data-ttu-id="2dbd7-120">✔️ RIDURRE AL MINIMO le modifiche di rilievo quando si sviluppa una libreria .NET di basso livello.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-120">✔️ DO minimize breaking changes when developing a low-level .NET library.</span></span>

<span data-ttu-id="2dbd7-121">✔️CONSIDERARE  la possibilità di pubblicare una riscrittura principale di una libreria come nuovo pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-121">✔️ CONSIDER publishing a major rewrite of a library as a new NuGet package.</span></span>

## <a name="types-of-breaking-changes"></a><span data-ttu-id="2dbd7-122">Tipi di modifiche di rilievo</span><span class="sxs-lookup"><span data-stu-id="2dbd7-122">Types of breaking changes</span></span>

<span data-ttu-id="2dbd7-123">Le modifiche di rilievo vengono classificate in categorie diverse e non hanno tutte lo stesso impatto.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-123">Breaking changes fall into different categories and aren't equally impactful.</span></span>

### <a name="source-breaking-change"></a><span data-ttu-id="2dbd7-124">Modifica dell'origine</span><span class="sxs-lookup"><span data-stu-id="2dbd7-124">Source breaking change</span></span>

<span data-ttu-id="2dbd7-125">Una modifica dell'origine non ha effetto sull'esecuzione del programma, ma genererà errori di compilazione quando l'applicazione sarà ricompilata.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-125">A source breaking change doesn't affect program execution but will cause compilation errors the next time the application is recompiled.</span></span> <span data-ttu-id="2dbd7-126">Ad esempio, un nuovo overload può creare ambiguità nelle chiamate al metodo che non erano precedentemente ambigue, oppure un parametro rinominato interromperà i chiamanti che usano parametri denominati.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-126">For example, a new overload can create an ambiguity in method calls that were unambiguous previously, or a renamed parameter will break callers that use named parameters.</span></span>

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

<span data-ttu-id="2dbd7-127">Poiché la modifica dell'origine è dannosa solo quando gli sviluppatori ricompilano le applicazioni, è il tipo di modifica che comporta meno problemi.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-127">Because a source breaking change is only harmful when developers recompile their applications, it's the least disruptive breaking change.</span></span> <span data-ttu-id="2dbd7-128">Gli sviluppatori possono risolvere facilmente il codice di origine interrotto.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-128">Developers can fix their own broken source code easily.</span></span>

### <a name="behavior-breaking-change"></a><span data-ttu-id="2dbd7-129">Modifica del comportamento</span><span class="sxs-lookup"><span data-stu-id="2dbd7-129">Behavior breaking change</span></span>

<span data-ttu-id="2dbd7-130">Le modifiche del comportamento sono i tipi di modifica più comuni. Quasi tutte le modifiche del comportamento possono creare un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-130">Behavior changes are the most common type of breaking change: almost any change in behavior could break someone.</span></span> <span data-ttu-id="2dbd7-131">Le modifiche alla libreria, ad esempio firme del metodo, eccezioni generate o formati di dati di input o output, possono avere tutte un effetto negativo sui consumer della libreria.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-131">Changes to your library, such as method signatures, exceptions thrown or input or output data formats, could all negatively impact your library consumers.</span></span> <span data-ttu-id="2dbd7-132">Perfino la correzione di un bug può essere considerata una modifica di rilievo se gli utenti si basavano sul comportamento precedentemente interrotto.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-132">Even a bug fix can qualify as a breaking change if users relied on the previously broken behavior.</span></span>

<span data-ttu-id="2dbd7-133">È una buona soluzione aggiungere funzionalità e migliorare i comportamenti non corretti. Tuttavia è consigliabile fare molta attenzione, poiché gli utenti esistenti potrebbero riscontrare difficoltà a eseguire l'upgrade.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-133">Adding features and improving bad behaviors is a good thing, but without care it can make it very hard for existing users to upgrade.</span></span> <span data-ttu-id="2dbd7-134">Per aiutare gli sviluppatori a gestire le modifiche del comportamento, è consigliabile nascondere tali modifiche nelle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-134">One approach to helping developers deal with behavior breaking changes is to hide them behind settings.</span></span> <span data-ttu-id="2dbd7-135">Le impostazioni consentono agli sviluppatori di eseguire l'aggiornamento alla versione più recente della libreria e al tempo stesso scegliere se accettare o rifiutare esplicitamente le modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-135">Settings let developers update to the latest version of your library while at the same time choosing to opt in or opt out of breaking changes.</span></span> <span data-ttu-id="2dbd7-136">Questa strategia consente agli sviluppatori di rimanere aggiornati, consentendo al codice usato di adattarsi nel tempo.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-136">This strategy lets developers stay up to date while letting their consuming code adapt over time.</span></span>

<span data-ttu-id="2dbd7-137">Ad esempio, ASP.NET Core MVC include il concetto di una [versione di compatibilità](/aspnet/core/mvc/compatibility-version) che consente di modificare la funzionalità abilitate e disabilitate in `MvcOptions`.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-137">For example, ASP.NET Core MVC has the concept of a [compatibility version](/aspnet/core/mvc/compatibility-version) that modifies the features enabled and disabled on `MvcOptions`.</span></span>

<span data-ttu-id="2dbd7-138">✔️ CONSIDERARE di lasciare disabilitate le nuove funzionalità per impostazione predefinita qualora abbiano effetto sugli utenti esistenti, e consentire agli sviluppatori di accettare esplicitamente la funzionalità con un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-138">✔️ CONSIDER leaving new features off by default, if they affect existing users, and let developers opt in to the feature with a setting.</span></span>

### <a name="binary-breaking-change"></a><span data-ttu-id="2dbd7-139">Modifica di tipo binario</span><span class="sxs-lookup"><span data-stu-id="2dbd7-139">Binary breaking change</span></span>

<span data-ttu-id="2dbd7-140">Una modifica di tipo binario si verifica quando viene modificata l'API pubblica della libreria. In questo caso gli assembly compilati sulla base delle versioni precedenti della libreria non possono più chiamare l'API.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-140">A binary breaking change happens when you change the public API of your library, so assemblies compiled against older versions of your library are no longer able to call the API.</span></span> <span data-ttu-id="2dbd7-141">Ad esempio, se si modifica la firma del metodo aggiungendo una nuovo parametro, gli assembly compilati sulla base delle versioni precedenti della libreria genereranno un'eccezione di tipo <xref:System.MissingMethodException>.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-141">For example, changing a method's signature by adding a new parameter will cause assemblies compiled against the older version of the library to throw a <xref:System.MissingMethodException>.</span></span>

<span data-ttu-id="2dbd7-142">Una modifica di tipo binario può interrompere anche un **intero assembly**.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-142">A binary breaking change can also break an **entire assembly**.</span></span> <span data-ttu-id="2dbd7-143">La rinomina di un assembly con `AssemblyName` modificherà l'identità dell'assembly, esattamente come succede se si aggiunge, rimuove o modifica la chiave per la creazione di nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-143">Renaming an assembly with `AssemblyName` will change the assembly's identity, as will adding, removing, or changing the assembly's strong naming key.</span></span> <span data-ttu-id="2dbd7-144">La modifica di un'identità dell'assembly interrompe l'intero codice compilato in cui viene usata.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-144">A change of an assembly's identity will break all compiled code that uses it.</span></span>

<span data-ttu-id="2dbd7-145">❌NON modificare il nome di un assembly.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-145">❌ DO NOT change an assembly name.</span></span>

<span data-ttu-id="2dbd7-146">❌NON aggiungere, rimuovere o modificare la chiave di denominazione sicura.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-146">❌ DO NOT add, remove, or change the strong naming key.</span></span>

<span data-ttu-id="2dbd7-147">✔️ CONSIDERARE l'uso di classi di base astratte al posto di interfacce.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-147">✔️ CONSIDER using abstract base classes instead of interfaces.</span></span>

> <span data-ttu-id="2dbd7-148">Se si aggiunge un qualsiasi elemento a un'interfaccia, i tipi esistenti che la implementano non saranno eseguiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-148">Adding anything to an interface will cause existing types that implement it to fail.</span></span> <span data-ttu-id="2dbd7-149">Una classe di base astratta consente di aggiungere un'impostazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-149">An abstract base class allows you to add a default virtual implementation.</span></span>

<span data-ttu-id="2dbd7-150">✔️ CONSIDERARE di posizionare la classe <xref:System.ObsoleteAttribute> su tipi e membri che non saranno rimossi.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-150">✔️ CONSIDER placing the <xref:System.ObsoleteAttribute> on types and members that you intend to remove.</span></span> <span data-ttu-id="2dbd7-151">L'attributo deve avere istruzioni per l'aggiornamento del codice affinché non sia più usata l'API obsoleta.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-151">The attribute should have instructions for updating code to no longer use the obsolete API.</span></span>

> <span data-ttu-id="2dbd7-152">Il codice che chiama i tipi e i metodi con la classe <xref:System.ObsoleteAttribute> genererà un avviso di compilazione con il messaggio specificato per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-152">Code that calls types and methods with the <xref:System.ObsoleteAttribute> will generate a build warning with the message supplied to the attribute.</span></span> <span data-ttu-id="2dbd7-153">Gli avvisi consentono a chi usa la superficie dell'API obsoleta di avere il tempo necessario per eseguire la migrazione. In questo modo, al momento della rimozione dell'API obsoleta, non sarà più usata da molti.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-153">The warnings give people who use the obsolete API surface time to migrate so that when the obsolete API is removed, most are no longer using it.</span></span>

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

<span data-ttu-id="2dbd7-154">✔️ CONSIDERARE di mantenere tipi e metodi con la classe <xref:System.ObsoleteAttribute> in modo illimitato nelle librerie di livello medio e basso.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-154">✔️ CONSIDER keeping types and methods with the <xref:System.ObsoleteAttribute> indefinitely in low and middle-level libraries.</span></span>

> <span data-ttu-id="2dbd7-155">La rimozione delle API è considerata una modifica di tipo binario.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-155">Removing APIs is a binary breaking change.</span></span> <span data-ttu-id="2dbd7-156">Valutare di mantenere tipi e metodi obsoleti se i costi di manutenzione sono bassi e non si richiedono interventi tecnici importanti alla libreria.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-156">Considering keeping obsolete types and methods if maintaining them is low cost and doesn't add lot of technical debt to your library.</span></span> <span data-ttu-id="2dbd7-157">Se i tipi e i metodi non vengono rimossi, si evita di assistere agli scenari peggiori descritti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-157">Not removing types and methods can help avoid the worst-case scenarios mentioned above.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dbd7-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dbd7-158">See also</span></span>

- [<span data-ttu-id="2dbd7-159">Considerazioni su versione e aggiornamento per gli sviluppatori C#</span><span class="sxs-lookup"><span data-stu-id="2dbd7-159">Version and update considerations for C# developers</span></span>](../../csharp/whats-new/version-update-considerations.md)
- <span data-ttu-id="2dbd7-160">[A definitive guide to API-breaking changes in .NET](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net) (Ottima guida alle modifiche di rilievo delle API in .NET)</span><span class="sxs-lookup"><span data-stu-id="2dbd7-160">[A definitive guide to API-breaking changes in .NET](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)</span></span>
- [<span data-ttu-id="2dbd7-161">Regole di modifica di rilievo .NET</span><span class="sxs-lookup"><span data-stu-id="2dbd7-161">.NET breaking change rules</span></span>](https://github.com/dotnet/runtime/blob/master/docs/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="2dbd7-162">Indietro</span><span class="sxs-lookup"><span data-stu-id="2dbd7-162">Previous</span></span>](versioning.md)
