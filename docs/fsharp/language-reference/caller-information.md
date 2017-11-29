---
title: 'Informazioni sul chiamante (F #)'
description: Viene descritto come utilizzare attributi di argomento di informazioni sul chiamante per ottenere informazioni sul chiamante da un metodo.
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 04/25/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 533d2f0429ddb31e6d1dd7efca2f0760069a2945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information"></a><span data-ttu-id="89e98-104">Informazioni sul chiamante</span><span class="sxs-lookup"><span data-stu-id="89e98-104">Caller information</span></span>

<span data-ttu-id="89e98-105">Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="89e98-105">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="89e98-106">È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante.</span><span class="sxs-lookup"><span data-stu-id="89e98-106">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="89e98-107">Queste informazioni sono utili per la tracciatura, il debug e la creazione di strumenti diagnostici.</span><span class="sxs-lookup"><span data-stu-id="89e98-107">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="89e98-108">Per ottenere queste informazioni, utilizzare gli attributi applicati ai parametri facoltativi, a ognuno dei quali è associato un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="89e98-108">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="89e98-109">Nella tabella seguente vengono elencati gli attributi di informazioni sul chiamante definiti nel [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) dello spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="89e98-109">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="89e98-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="89e98-110">Attribute</span></span>|<span data-ttu-id="89e98-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89e98-111">Description</span></span>|<span data-ttu-id="89e98-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="89e98-112">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="89e98-113">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="89e98-113">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="89e98-114">Percorso completo del file di origine contenente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="89e98-114">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="89e98-115">Si tratta del percorso del file al momento della compilazione.</span><span class="sxs-lookup"><span data-stu-id="89e98-115">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="89e98-116">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="89e98-116">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="89e98-117">Numero di riga nel file di origine in cui viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="89e98-117">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="89e98-118">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="89e98-118">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="89e98-119">Nome di una proprietà o di un metodo del chiamante.</span><span class="sxs-lookup"><span data-stu-id="89e98-119">Method or property name of the caller.</span></span> <span data-ttu-id="89e98-120">Vedere la sezione i nomi dei membri più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="89e98-120">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="89e98-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="89e98-121">Example</span></span>

<span data-ttu-id="89e98-122">Nell'esempio seguente viene illustrato come è possibile utilizzare questi attributi per tracciare un chiamante.</span><span class="sxs-lookup"><span data-stu-id="89e98-122">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a><span data-ttu-id="89e98-123">Note</span><span class="sxs-lookup"><span data-stu-id="89e98-123">Remarks</span></span>

<span data-ttu-id="89e98-124">Attributi informativi sul chiamante possono essere applicati solo a parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="89e98-124">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="89e98-125">È necessario fornire un valore esplicito per ogni parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="89e98-125">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="89e98-126">Gli attributi di informazioni sul chiamante che il compilatore scrivere il valore corretto per ciascun parametro facoltativo decorato con un attributo di informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="89e98-126">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="89e98-127">I valori delle informazioni sul chiamante vengono generati come valori letterali in Intermediate Language (IL) in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="89e98-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="89e98-128">A differenza dei risultati del [StackTrace](/dotnet/api/system.diagnostics.stacktrace) proprietà per le eccezioni, i risultati non sono interessati da offuscamento.</span><span class="sxs-lookup"><span data-stu-id="89e98-128">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="89e98-129">È possibile fornire esplicitamente gli argomenti facoltativi per esaminare o nascondere le informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="89e98-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="89e98-130">Nomi dei membri</span><span class="sxs-lookup"><span data-stu-id="89e98-130">Member names</span></span>

<span data-ttu-id="89e98-131">È possibile utilizzare il [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attributo per evitare di specificare il nome del membro come un `String` argomento al metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="89e98-131">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="89e98-132">Utilizzando questa tecnica, si evita il problema che Refactoring di ridenominazione non viene modificato il `String` valori.</span><span class="sxs-lookup"><span data-stu-id="89e98-132">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="89e98-133">Questo vantaggio è particolarmente utile per le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="89e98-133">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="89e98-134">Utilizzo della tracciatura e delle routine di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="89e98-134">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="89e98-135">Implementazione di [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) durante l'associazione di dati.</span><span class="sxs-lookup"><span data-stu-id="89e98-135">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="89e98-136">Questa interfaccia consente alla proprietà di un oggetto di notificare a un controllo associato la modifica della proprietà stessa in modo che il controllo possa visualizzare le informazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="89e98-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="89e98-137">Senza il [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attributo, è necessario specificare il nome della proprietà come valore letterale.</span><span class="sxs-lookup"><span data-stu-id="89e98-137">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="89e98-138">Il grafico seguente mostra il membro nomi che vengono restituiti quando si utilizza l'attributo CallerMemberName.</span><span class="sxs-lookup"><span data-stu-id="89e98-138">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="89e98-139">Elemento in cui si verificano le chiamate</span><span class="sxs-lookup"><span data-stu-id="89e98-139">Calls occurs within</span></span>|<span data-ttu-id="89e98-140">Nome del membro restituito</span><span class="sxs-lookup"><span data-stu-id="89e98-140">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="89e98-141">Metodo, proprietà o evento</span><span class="sxs-lookup"><span data-stu-id="89e98-141">Method, property, or event</span></span>|<span data-ttu-id="89e98-142">Nome del metodo, della proprietà o dell'evento da cui la chiamata ha avuto origine.</span><span class="sxs-lookup"><span data-stu-id="89e98-142">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="89e98-143">Costruttore</span><span class="sxs-lookup"><span data-stu-id="89e98-143">Constructor</span></span>|<span data-ttu-id="89e98-144">Stringa ".ctor"</span><span class="sxs-lookup"><span data-stu-id="89e98-144">The string ".ctor"</span></span>|
|<span data-ttu-id="89e98-145">Costruttore statico</span><span class="sxs-lookup"><span data-stu-id="89e98-145">Static constructor</span></span>|<span data-ttu-id="89e98-146">Stringa ".cctor"</span><span class="sxs-lookup"><span data-stu-id="89e98-146">The string ".cctor"</span></span>|
|<span data-ttu-id="89e98-147">Distruttore</span><span class="sxs-lookup"><span data-stu-id="89e98-147">Destructor</span></span>|<span data-ttu-id="89e98-148">Stringa "Finalize"</span><span class="sxs-lookup"><span data-stu-id="89e98-148">The string "Finalize"</span></span>|
|<span data-ttu-id="89e98-149">Operatori o conversioni definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="89e98-149">User-defined operators or conversions</span></span>|<span data-ttu-id="89e98-150">Nome generato per il membro, ad esempio "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="89e98-150">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="89e98-151">Costruttore dell'attributo</span><span class="sxs-lookup"><span data-stu-id="89e98-151">Attribute constructor</span></span>|<span data-ttu-id="89e98-152">Nome del membro a cui viene applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="89e98-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="89e98-153">Se l'attributo è un qualsiasi elemento in un membro (ad esempio un parametro, un valore restituito o un parametro di tipo generico), il risultato è il nome del membro associato a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="89e98-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="89e98-154">Nessun membro contenitore (ad esempio a livello di assembly o attributi applicati a tipi)</span><span class="sxs-lookup"><span data-stu-id="89e98-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="89e98-155">Valore predefinito del parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="89e98-155">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="89e98-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89e98-156">See also</span></span>
 [<span data-ttu-id="89e98-157">Attributi</span><span class="sxs-lookup"><span data-stu-id="89e98-157">Attributes</span></span>](attributes.md)  
 [<span data-ttu-id="89e98-158">Argomenti denominati</span><span class="sxs-lookup"><span data-stu-id="89e98-158">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
 [<span data-ttu-id="89e98-159">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="89e98-159">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
