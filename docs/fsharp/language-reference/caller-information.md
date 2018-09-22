---
title: 'Informazioni sul chiamante (F #)'
description: Viene descritto come utilizzare attributi di argomenti informativi sul chiamante per ottenere informazioni sul chiamante da un metodo.
ms.date: 04/25/2017
ms.openlocfilehash: 0f2f4b16804d9156d234cc29d1f72ebe80a5b556
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46577571"
---
# <a name="caller-information"></a><span data-ttu-id="f2974-103">Informazioni sul chiamante</span><span class="sxs-lookup"><span data-stu-id="f2974-103">Caller information</span></span>

<span data-ttu-id="f2974-104">Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="f2974-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="f2974-105">È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f2974-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="f2974-106">Queste informazioni sono utili per la tracciatura, il debug e la creazione di strumenti diagnostici.</span><span class="sxs-lookup"><span data-stu-id="f2974-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="f2974-107">Per ottenere queste informazioni, utilizzare gli attributi applicati ai parametri facoltativi, a ognuno dei quali è associato un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f2974-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="f2974-108">Nella tabella seguente elenca gli attributi di informazioni sul chiamante definiti nel [CompilerServices](/dotnet/api/system.runtime.compilerservices) dello spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="f2974-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="f2974-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="f2974-109">Attribute</span></span>|<span data-ttu-id="f2974-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2974-110">Description</span></span>|<span data-ttu-id="f2974-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="f2974-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="f2974-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="f2974-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="f2974-113">Percorso completo del file di origine contenente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="f2974-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="f2974-114">Si tratta del percorso del file al momento della compilazione.</span><span class="sxs-lookup"><span data-stu-id="f2974-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="f2974-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="f2974-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="f2974-116">Numero di riga nel file di origine in cui viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="f2974-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="f2974-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="f2974-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="f2974-118">Nome di una proprietà o di un metodo del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f2974-118">Method or property name of the caller.</span></span> <span data-ttu-id="f2974-119">Vedere la sezione di nomi di membri più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f2974-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="f2974-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2974-120">Example</span></span>

<span data-ttu-id="f2974-121">Nell'esempio seguente viene illustrato come è possibile usare questi attributi per tracciare un chiamante.</span><span class="sxs-lookup"><span data-stu-id="f2974-121">The following example shows how you might use these attributes to trace a caller.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="f2974-122">Note</span><span class="sxs-lookup"><span data-stu-id="f2974-122">Remarks</span></span>

<span data-ttu-id="f2974-123">Attributi informativi sul chiamante possono essere applicati solo a parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="f2974-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="f2974-124">È necessario fornire un valore esplicito per ciascun parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f2974-124">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="f2974-125">Gli attributi di informazioni sul chiamante che il compilatore scrivere il valore appropriato per ciascun parametro facoltativo dotato di un attributo di informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="f2974-125">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="f2974-126">I valori delle informazioni sul chiamante vengono generati come valori letterali in Intermediate Language (IL) in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f2974-126">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="f2974-127">A differenza dei risultati del [StackTrace](/dotnet/api/system.diagnostics.stacktrace) proprietà per le eccezioni, i risultati non sono interessati da offuscamento.</span><span class="sxs-lookup"><span data-stu-id="f2974-127">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="f2974-128">È possibile fornire esplicitamente gli argomenti facoltativi per esaminare o nascondere le informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="f2974-128">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="f2974-129">Nomi dei membri</span><span class="sxs-lookup"><span data-stu-id="f2974-129">Member names</span></span>

<span data-ttu-id="f2974-130">È possibile usare la [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attributo per evitare di specificare il nome del membro come un `String` argomento al metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="f2974-130">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="f2974-131">Utilizzando questa tecnica, si evita il problema che Refactoring di ridenominazione non cambia il `String` valori.</span><span class="sxs-lookup"><span data-stu-id="f2974-131">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="f2974-132">Questo vantaggio è particolarmente utile per le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2974-132">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="f2974-133">Utilizzo della tracciatura e delle routine di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="f2974-133">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="f2974-134">Implementa il [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interfaccia durante l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="f2974-134">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="f2974-135">Questa interfaccia consente alla proprietà di un oggetto di notificare a un controllo associato la modifica della proprietà stessa in modo che il controllo possa visualizzare le informazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="f2974-135">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="f2974-136">Senza il [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attributo, è necessario specificare il nome della proprietà come valore letterale.</span><span class="sxs-lookup"><span data-stu-id="f2974-136">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="f2974-137">Il grafico seguente mostra il membro nomi che vengono restituiti quando si usa l'attributo CallerMemberName.</span><span class="sxs-lookup"><span data-stu-id="f2974-137">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="f2974-138">Elemento in cui si verificano le chiamate</span><span class="sxs-lookup"><span data-stu-id="f2974-138">Calls occurs within</span></span>|<span data-ttu-id="f2974-139">Nome del membro restituito</span><span class="sxs-lookup"><span data-stu-id="f2974-139">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="f2974-140">Metodo, proprietà o evento</span><span class="sxs-lookup"><span data-stu-id="f2974-140">Method, property, or event</span></span>|<span data-ttu-id="f2974-141">Nome del metodo, della proprietà o dell'evento da cui la chiamata ha avuto origine.</span><span class="sxs-lookup"><span data-stu-id="f2974-141">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="f2974-142">Costruttore</span><span class="sxs-lookup"><span data-stu-id="f2974-142">Constructor</span></span>|<span data-ttu-id="f2974-143">Stringa ".ctor"</span><span class="sxs-lookup"><span data-stu-id="f2974-143">The string ".ctor"</span></span>|
|<span data-ttu-id="f2974-144">Costruttore statico</span><span class="sxs-lookup"><span data-stu-id="f2974-144">Static constructor</span></span>|<span data-ttu-id="f2974-145">Stringa ".cctor"</span><span class="sxs-lookup"><span data-stu-id="f2974-145">The string ".cctor"</span></span>|
|<span data-ttu-id="f2974-146">Distruttore</span><span class="sxs-lookup"><span data-stu-id="f2974-146">Destructor</span></span>|<span data-ttu-id="f2974-147">Stringa "Finalize"</span><span class="sxs-lookup"><span data-stu-id="f2974-147">The string "Finalize"</span></span>|
|<span data-ttu-id="f2974-148">Operatori o conversioni definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="f2974-148">User-defined operators or conversions</span></span>|<span data-ttu-id="f2974-149">Nome generato per il membro, ad esempio "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="f2974-149">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="f2974-150">Costruttore dell'attributo</span><span class="sxs-lookup"><span data-stu-id="f2974-150">Attribute constructor</span></span>|<span data-ttu-id="f2974-151">Nome del membro a cui viene applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="f2974-151">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="f2974-152">Se l'attributo è un qualsiasi elemento in un membro (ad esempio un parametro, un valore restituito o un parametro di tipo generico), il risultato è il nome del membro associato a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="f2974-152">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="f2974-153">Nessun membro contenitore (ad esempio a livello di assembly o attributi applicati a tipi)</span><span class="sxs-lookup"><span data-stu-id="f2974-153">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="f2974-154">Valore predefinito del parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f2974-154">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f2974-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2974-155">See also</span></span>

- [<span data-ttu-id="f2974-156">Attributi</span><span class="sxs-lookup"><span data-stu-id="f2974-156">Attributes</span></span>](attributes.md)  
- [<span data-ttu-id="f2974-157">Argomenti denominati</span><span class="sxs-lookup"><span data-stu-id="f2974-157">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
- [<span data-ttu-id="f2974-158">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="f2974-158">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
