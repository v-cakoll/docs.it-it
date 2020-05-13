---
title: Risolvere i caricamenti di assembly
description: Questo articolo descrive l'evento .NET AppDomain. AssemblyResolve. Utilizzare questo evento per le applicazioni che richiedono il controllo del caricamento degli assembly.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], resolving loads
- application domains, loading assemblies
- resolving assembly loads
- assemblies [.NET Framework], loading
- application domains, resolving assembly loads
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 36f36b60a3a113c6b020cc1042c786c4091e567b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378672"
---
# <a name="resolve-assembly-loads"></a><span data-ttu-id="0ec0a-104">Risolvere i caricamenti di assembly</span><span class="sxs-lookup"><span data-stu-id="0ec0a-104">Resolve assembly loads</span></span>
<span data-ttu-id="0ec0a-105">.NET fornisce l' <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento per le applicazioni che richiedono un maggiore controllo sul caricamento degli assembly.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-105">.NET provides the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event for applications that require greater control over assembly loading.</span></span> <span data-ttu-id="0ec0a-106">Con questo evento, l'applicazione può caricare un assembly nel contesto di caricamento dall'esterno di percorsi di sondaggio normale, selezionare la versione di assembly da caricare, creare e restituire un assembly dinamico e così via.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-106">By handling this event, your application can load an assembly into the load context from outside the normal probing paths, select which of several assembly versions to load, emit a dynamic assembly and return it, and so on.</span></span> <span data-ttu-id="0ec0a-107">Questo argomento illustra il materiale sussidiario per la gestione dell'evento <xref:System.AppDomain.AssemblyResolve>.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-107">This topic provides guidance for handling the <xref:System.AppDomain.AssemblyResolve> event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ec0a-108">Per la risoluzione di caricamenti di assembly nel solo contesto di reflection, usare invece l'evento <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-108">For resolving assembly loads in the reflection-only context, use the <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType> event instead.</span></span>  
  
## <a name="how-the-assemblyresolve-event-works"></a><span data-ttu-id="0ec0a-109">Funzionamento dell'evento AssemblyResolve</span><span class="sxs-lookup"><span data-stu-id="0ec0a-109">How the AssemblyResolve event works</span></span>  
 <span data-ttu-id="0ec0a-110">Quando si registra un gestore per l'evento <xref:System.AppDomain.AssemblyResolve>, il gestore viene richiamato ogni volta che il runtime non riesce ad associarlo a un assembly in base al nome.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-110">When you register a handler for the <xref:System.AppDomain.AssemblyResolve> event, the handler is invoked whenever the runtime fails to bind to an assembly by name.</span></span> <span data-ttu-id="0ec0a-111">Ad esempio, la chiamata dei metodi seguenti dal codice utente può causare l'evento <xref:System.AppDomain.AssemblyResolve>:</span><span class="sxs-lookup"><span data-stu-id="0ec0a-111">For example, calling the following methods from user code can cause the <xref:System.AppDomain.AssemblyResolve> event to be raised:</span></span>  
  
- <span data-ttu-id="0ec0a-112">Un overload del metodo <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, il cui primo argomento è una stringa che rappresenta il nome visualizzato dell'assembly da caricare (ovvero, la stringa restituita dalla proprietà <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="0ec0a-112">An <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method overload or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overload whose first argument is a string that represents the display name of the assembly to load (that is, the string returned by the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property).</span></span>  
  
- <span data-ttu-id="0ec0a-113">Un overload del metodo <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, il cui primo argomento è un oggetto <xref:System.Reflection.AssemblyName> che identifica l'assembly da caricare.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-113">An <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method overload or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overload whose first argument is an <xref:System.Reflection.AssemblyName> object that identifies the assembly to load.</span></span>  
  
- <span data-ttu-id="0ec0a-114">Un overload del metodo <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-114">An <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> method overload.</span></span>  
  
- <span data-ttu-id="0ec0a-115">Un overload del metodo <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> che crea un'istanza di un oggetto in un altro dominio di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-115">An <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> method overload that instantiates an object in another application domain.</span></span>  
  
### <a name="what-the-event-handler-does"></a><span data-ttu-id="0ec0a-116">Funzione del gestore eventi</span><span class="sxs-lookup"><span data-stu-id="0ec0a-116">What the event handler does</span></span>  
 <span data-ttu-id="0ec0a-117">Il gestore per l'evento <xref:System.AppDomain.AssemblyResolve> riceve il nome visualizzato dell'assembly da caricare nella proprietà <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-117">The handler for the <xref:System.AppDomain.AssemblyResolve> event receives the display name of the assembly to be loaded, in the <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0ec0a-118">Se il gestore non riconosce il nome dell'assembly, restituisce `null` (C#), `Nothing` (Visual Basic) o `nullptr` (Visual C++).</span><span class="sxs-lookup"><span data-stu-id="0ec0a-118">If the handler does not recognize the assembly name, it returns `null` (C#), `Nothing` (Visual Basic), or `nullptr` (Visual C++).</span></span>  
  
 <span data-ttu-id="0ec0a-119">Se il gestore riconosce il nome dell'assembly, può caricare e restituire un assembly che soddisfi la richiesta.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-119">If the handler recognizes the assembly name, it can load and return an assembly that satisfies the request.</span></span> <span data-ttu-id="0ec0a-120">Nell'elenco seguente vengono illustrati alcuni scenari di esempio.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-120">The following list describes some sample scenarios.</span></span>  
  
- <span data-ttu-id="0ec0a-121">Se il gestore conosce il percorso di una versione dell'assembly, può caricare l'assembly usando il metodo <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> e può restituire l'assembly caricato, se ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-121">If the handler knows the location of a version of the assembly, it can load the assembly by using the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> method, and can return the loaded assembly if successful.</span></span>  
  
- <span data-ttu-id="0ec0a-122">Se il gestore ha accesso a un database di assembly archiviati come matrici di byte, può caricare una matrice di byte usando uno degli overload del metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> che accetta una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-122">If the handler has access to a database of assemblies stored as byte arrays, it can load a byte array by using one of the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overloads that take a byte array.</span></span>  
  
- <span data-ttu-id="0ec0a-123">Il gestore può generare e restituire un assembly dinamico.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-123">The handler can generate a dynamic assembly and return it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ec0a-124">Il gestore deve caricare l'assembly nel contesto di caricamento di provenienza, nel contesto di caricamento o in nessun contesto. Se il gestore carica l'assembly nel contesto di reflection solo usando il metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType>, il tentativo di caricamento che ha generato l'evento <xref:System.AppDomain.AssemblyResolve> ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-124">The handler must load the assembly into the load-from context, into the load context, or without context.If the handler loads the assembly into the reflection-only context by using the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> method, the load attempt that raised the <xref:System.AppDomain.AssemblyResolve> event fails.</span></span>  
  
 <span data-ttu-id="0ec0a-125">È compito del gestore eventi restituire un assembly appropriato.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-125">It is the responsibility of the event handler to return a suitable assembly.</span></span> <span data-ttu-id="0ec0a-126">Il gestore può analizzare il nome visualizzato dell'assembly richiesto passando il valore della proprietà <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> al costruttore <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-126">The handler can parse the display name of the requested assembly by passing the <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> property value to the <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29> constructor.</span></span> <span data-ttu-id="0ec0a-127">A partire da .NET Framework 4, il gestore può usare la proprietà <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> per determinare se la richiesta corrente è una dipendenza di un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-127">Beginning with the .NET Framework 4, the handler can use the <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property to determine whether the current request is a dependency of another assembly.</span></span> <span data-ttu-id="0ec0a-128">Questa informazione può aiutare a identificare un assembly che soddisferà la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-128">This information can help identify an assembly that will satisfy the dependency.</span></span>  
  
 <span data-ttu-id="0ec0a-129">Il gestore eventi può restituire una versione diversa dell'assembly rispetto alla versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-129">The event handler can return a different version of the assembly than the version that was requested.</span></span>  
  
 <span data-ttu-id="0ec0a-130">Nella maggior parte dei casi, l'assembly restituito dal gestore viene visualizzato nel contesto di caricamento, indipendentemente dal contesto in cui lo carica il gestore.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-130">In most cases, the assembly that is returned by the handler appears in the load context, regardless of the context the handler loads it into.</span></span> <span data-ttu-id="0ec0a-131">Ad esempio, se il gestore usa il metodo <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> per caricare un assembly nel contesto di caricamento di provenienza, l'assembly viene visualizzato nel contesto di caricamento quando viene restituito dal gestore.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-131">For example, if the handler uses the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method to load an assembly into the load-from context, the assembly appears in the load context when the handler returns it.</span></span> <span data-ttu-id="0ec0a-132">Tuttavia, nel caso seguente l'assembly viene visualizzato senza contesto quando viene restituito dal gestore:</span><span class="sxs-lookup"><span data-stu-id="0ec0a-132">However, in the following case the assembly appears without context when the handler returns it:</span></span>  
  
- <span data-ttu-id="0ec0a-133">Il gestore carica un assembly senza contesto.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-133">The handler loads an assembly without context.</span></span>  
  
- <span data-ttu-id="0ec0a-134">La proprietà <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> non è Null.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-134">The <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property is not null.</span></span>  
  
- <span data-ttu-id="0ec0a-135">L'assembly richiedente (vale a dire l'assembly restituito dalla proprietà <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>) è stato caricato senza contesto.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-135">The requesting assembly (that is, the assembly that is returned by the <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property) was loaded without context.</span></span>  
  
 <span data-ttu-id="0ec0a-136">Per informazioni sui contesti, vedere l'overload del metodo <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-136">For information about contexts, see the <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType> method overload.</span></span>  
  
 <span data-ttu-id="0ec0a-137">È possibile caricare più versioni dello stesso assembly nello stesso dominio di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-137">Multiple versions of the same assembly can be loaded into the same application domain.</span></span> <span data-ttu-id="0ec0a-138">Questa pratica non è consigliata, perché può causare problemi di assegnazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-138">This practice is not recommended, because it can lead to type assignment problems.</span></span> <span data-ttu-id="0ec0a-139">Vedere le [procedure consigliate per il caricamento di assembly](../../framework/deployment/best-practices-for-assembly-loading.md).</span><span class="sxs-lookup"><span data-stu-id="0ec0a-139">See [Best practices for assembly loading](../../framework/deployment/best-practices-for-assembly-loading.md).</span></span>  
  
### <a name="what-the-event-handler-should-not-do"></a><span data-ttu-id="0ec0a-140">Cosa non deve fare il gestore eventi</span><span class="sxs-lookup"><span data-stu-id="0ec0a-140">What the event handler should not do</span></span>  
<span data-ttu-id="0ec0a-141">La regola principale nella gestione di eventi <xref:System.AppDomain.AssemblyResolve> è che non si deve provare a restituire un assembly non riconosciuta.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-141">The primary rule for handling the <xref:System.AppDomain.AssemblyResolve> event is that you should not try to return an assembly you do not recognize.</span></span> <span data-ttu-id="0ec0a-142">Quando si scrive il gestore, è necessario conoscere gli assembly che potrebbero causare la generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-142">When you write the handler, you should know which assemblies might cause the event to be raised.</span></span> <span data-ttu-id="0ec0a-143">Il gestore deve restituire Null per gli altri assembly.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-143">Your handler should return null for other assemblies.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="0ec0a-144">A partire da .NET Framework 4, l'evento <xref:System.AppDomain.AssemblyResolve> viene generato per gli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-144">Beginning with the .NET Framework 4, the <xref:System.AppDomain.AssemblyResolve> event is raised for satellite assemblies.</span></span> <span data-ttu-id="0ec0a-145">Questa modifica interessa un gestore eventi scritto per una versione precedente di .NET Framework, se il gestore proverà a risolvere tutte le richieste di caricamento di assembly.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-145">This change affects an event handler that was written for an earlier version of the .NET Framework, if the handler tries to resolve all assembly load requests.</span></span> <span data-ttu-id="0ec0a-146">I gestori di eventi, che ignorano gli assembly non riconosciuti, non sono interessati da questa modifica. Infatti restituiscono Null e seguono i normali meccanismi di fallback.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-146">Event handlers that ignore assemblies they do not recognize are not affected by this change: They return null, and normal fallback mechanisms are followed.</span></span>  

<span data-ttu-id="0ec0a-147">Quando si carica un assembly, il gestore eventi non deve usare nessun overload del metodo <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> che può causare la generazione dell'evento <xref:System.AppDomain.AssemblyResolve> in modo ricorsivo, poiché questo può causare un overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-147">When loading an assembly, the event handler must not use any of the <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overloads that can cause the <xref:System.AppDomain.AssemblyResolve> event to be raised recursively, because this can lead to a stack overflow.</span></span> <span data-ttu-id="0ec0a-148">Vedere l'elenco fornito in precedenza in questo argomento. Ciò si verifica anche se si fornisce la gestione delle eccezioni per la richiesta di caricamento, perché non viene generata alcuna eccezione fino a quando non vengono restituiti tutti i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="0ec0a-148">(See the list provided earlier in this topic.) This happens even if you provide exception handling for the load request, because no exception is thrown until all event handlers have returned.</span></span> <span data-ttu-id="0ec0a-149">Di conseguenza, il codice seguente causa un overflow dello stack se `MyAssembly` non viene trovato:</span><span class="sxs-lookup"><span data-stu-id="0ec0a-149">Thus, the following code results in a stack overflow if `MyAssembly` is not found:</span></span>  

```cpp
using namespace System;
using namespace System::Reflection;

ref class Example
{
internal:
    static Assembly^ MyHandler(Object^ source, ResolveEventArgs^ e)
    {
        Console::WriteLine("Resolving {0}", e->Name);
        return Assembly::Load(e->Name);
    }
};

void main()
{
    AppDomain^ ad = AppDomain::CreateDomain("Test");
    ad->AssemblyResolve += gcnew ResolveEventHandler(&Example::MyHandler);

    try
    {
        Object^ obj = ad->CreateInstanceAndUnwrap(
            "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
            "MyType");
    }
    catch (Exception^ ex)
    {
        Console::WriteLine(ex->Message);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```csharp
using System;
using System.Reflection;

class BadExample
{
    static void Main()
    {
        AppDomain ad = AppDomain.CreateDomain("Test");
        ad.AssemblyResolve += MyHandler;

        try
        {
            object obj = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType");
        }
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static Assembly MyHandler(object source, ResolveEventArgs e)
    {
        Console.WriteLine("Resolving {0}", e.Name);
        return Assembly.Load(e.Name);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```vb
Imports System.Reflection

Class BadExample

    Shared Sub Main()

        Dim ad As AppDomain = AppDomain.CreateDomain("Test")
        AddHandler ad.AssemblyResolve, AddressOf MyHandler

        Try
            Dim obj As object = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType")
        Catch ex As Exception
            Console.WriteLine(ex.Message)
        End Try
    End Sub

    Shared Function MyHandler(ByVal source As Object, _
                              ByVal e As ResolveEventArgs) As Assembly
        Console.WriteLine("Resolving {0}", e.Name)
        Return Assembly.Load(e.Name)
    End Function
End Class

' This example produces output similar to the following:
'
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'...
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'
'Process is terminated due to StackOverflowException.
```

## <a name="see-also"></a><span data-ttu-id="0ec0a-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ec0a-150">See also</span></span>

- [<span data-ttu-id="0ec0a-151">Procedure consigliate per il caricamento di assembly</span><span class="sxs-lookup"><span data-stu-id="0ec0a-151">Best practices for assembly loading</span></span>](../../framework/deployment/best-practices-for-assembly-loading.md)
- [<span data-ttu-id="0ec0a-152">Usare i domini applicazione</span><span class="sxs-lookup"><span data-stu-id="0ec0a-152">Use application domains</span></span>](../../framework/app-domains/use.md)
