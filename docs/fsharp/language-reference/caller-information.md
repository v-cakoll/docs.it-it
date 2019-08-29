---
title: Informazioni sul chiamante
description: Viene descritto come usare gli attributi degli argomenti delle informazioni sul chiamante per ottenere informazioni sul chiamante da un metodo.
ms.date: 04/25/2017
ms.openlocfilehash: e7bbc3830a95bd25cfc2fb369b204d367b775815
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106590"
---
# <a name="caller-information"></a><span data-ttu-id="55e19-103">Informazioni sul chiamante</span><span class="sxs-lookup"><span data-stu-id="55e19-103">Caller information</span></span>

<span data-ttu-id="55e19-104">Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="55e19-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="55e19-105">È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante.</span><span class="sxs-lookup"><span data-stu-id="55e19-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="55e19-106">Queste informazioni sono utili per la tracciatura, il debug e la creazione di strumenti diagnostici.</span><span class="sxs-lookup"><span data-stu-id="55e19-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="55e19-107">Per ottenere queste informazioni, utilizzare gli attributi applicati ai parametri facoltativi, a ognuno dei quali è associato un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="55e19-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="55e19-108">La tabella seguente elenca gli attributi delle informazioni sul chiamante definiti nello spazio dei nomi [System. Runtime. CompilerServices](/dotnet/api/system.runtime.compilerservices) :</span><span class="sxs-lookup"><span data-stu-id="55e19-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="55e19-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="55e19-109">Attribute</span></span>|<span data-ttu-id="55e19-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55e19-110">Description</span></span>|<span data-ttu-id="55e19-111">Type</span><span class="sxs-lookup"><span data-stu-id="55e19-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="55e19-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="55e19-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="55e19-113">Percorso completo del file di origine contenente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="55e19-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="55e19-114">Si tratta del percorso del file al momento della compilazione.</span><span class="sxs-lookup"><span data-stu-id="55e19-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="55e19-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="55e19-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="55e19-116">Numero di riga nel file di origine in cui viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="55e19-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="55e19-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="55e19-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="55e19-118">Nome di una proprietà o di un metodo del chiamante.</span><span class="sxs-lookup"><span data-stu-id="55e19-118">Method or property name of the caller.</span></span> <span data-ttu-id="55e19-119">Vedere la sezione nomi dei membri più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="55e19-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="55e19-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="55e19-120">Example</span></span>

<span data-ttu-id="55e19-121">Nell'esempio seguente viene illustrato come è possibile utilizzare questi attributi per tracciare un chiamante.</span><span class="sxs-lookup"><span data-stu-id="55e19-121">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member __.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        Trace.WriteLine(sprintf "Member name: %s" memberName)
        Trace.WriteLine(sprintf "Source file path: %s" path)
        Trace.WriteLine(sprintf "Source line number: %d" line)
```

## <a name="remarks"></a><span data-ttu-id="55e19-122">Note</span><span class="sxs-lookup"><span data-stu-id="55e19-122">Remarks</span></span>

<span data-ttu-id="55e19-123">Gli attributi delle informazioni sul chiamante possono essere applicati solo ai parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="55e19-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="55e19-124">Gli attributi delle informazioni sul chiamante fanno sì che il compilatore scriva il valore appropriato per ogni parametro facoltativo decorato con un attributo info del chiamante.</span><span class="sxs-lookup"><span data-stu-id="55e19-124">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="55e19-125">I valori delle informazioni sul chiamante vengono generati come valori letterali in Intermediate Language (IL) in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="55e19-125">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="55e19-126">A differenza dei risultati della proprietà [StackTrace](/dotnet/api/system.diagnostics.stacktrace) per le eccezioni, i risultati non sono interessati dall'offuscamento.</span><span class="sxs-lookup"><span data-stu-id="55e19-126">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="55e19-127">È possibile fornire esplicitamente gli argomenti facoltativi per esaminare o nascondere le informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="55e19-127">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="55e19-128">Nomi dei membri</span><span class="sxs-lookup"><span data-stu-id="55e19-128">Member names</span></span>

<span data-ttu-id="55e19-129">È possibile utilizzare l' [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attributo per evitare di specificare il nome del membro `String` come argomento del metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="55e19-129">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="55e19-130">Utilizzando questa tecnica, si evita il problema che il refactoring di ridenominazione non `String` modifica i valori.</span><span class="sxs-lookup"><span data-stu-id="55e19-130">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="55e19-131">Questo vantaggio è particolarmente utile per le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="55e19-131">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="55e19-132">Utilizzo della tracciatura e delle routine di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="55e19-132">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="55e19-133">Implementazione dell'interfaccia [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) durante l'associazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="55e19-133">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="55e19-134">Questa interfaccia consente alla proprietà di un oggetto di notificare a un controllo associato la modifica della proprietà stessa in modo che il controllo possa visualizzare le informazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="55e19-134">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="55e19-135">Senza l' [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attributo, è necessario specificare il nome della proprietà come valore letterale.</span><span class="sxs-lookup"><span data-stu-id="55e19-135">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="55e19-136">Nel grafico seguente vengono illustrati i nomi dei membri restituiti quando si utilizza l'attributo CallerMemberName.</span><span class="sxs-lookup"><span data-stu-id="55e19-136">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="55e19-137">Elemento in cui si verificano le chiamate</span><span class="sxs-lookup"><span data-stu-id="55e19-137">Calls occurs within</span></span>|<span data-ttu-id="55e19-138">Nome del membro restituito</span><span class="sxs-lookup"><span data-stu-id="55e19-138">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="55e19-139">Metodo, proprietà o evento</span><span class="sxs-lookup"><span data-stu-id="55e19-139">Method, property, or event</span></span>|<span data-ttu-id="55e19-140">Nome del metodo, della proprietà o dell'evento da cui la chiamata ha avuto origine.</span><span class="sxs-lookup"><span data-stu-id="55e19-140">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="55e19-141">Costruttore</span><span class="sxs-lookup"><span data-stu-id="55e19-141">Constructor</span></span>|<span data-ttu-id="55e19-142">Stringa ".ctor"</span><span class="sxs-lookup"><span data-stu-id="55e19-142">The string ".ctor"</span></span>|
|<span data-ttu-id="55e19-143">Costruttore statico</span><span class="sxs-lookup"><span data-stu-id="55e19-143">Static constructor</span></span>|<span data-ttu-id="55e19-144">Stringa ".cctor"</span><span class="sxs-lookup"><span data-stu-id="55e19-144">The string ".cctor"</span></span>|
|<span data-ttu-id="55e19-145">Distruttore</span><span class="sxs-lookup"><span data-stu-id="55e19-145">Destructor</span></span>|<span data-ttu-id="55e19-146">Stringa "Finalize"</span><span class="sxs-lookup"><span data-stu-id="55e19-146">The string "Finalize"</span></span>|
|<span data-ttu-id="55e19-147">Operatori o conversioni definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="55e19-147">User-defined operators or conversions</span></span>|<span data-ttu-id="55e19-148">Nome generato per il membro, ad esempio "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="55e19-148">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="55e19-149">Costruttore dell'attributo</span><span class="sxs-lookup"><span data-stu-id="55e19-149">Attribute constructor</span></span>|<span data-ttu-id="55e19-150">Nome del membro a cui viene applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="55e19-150">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="55e19-151">Se l'attributo è un qualsiasi elemento in un membro (ad esempio un parametro, un valore restituito o un parametro di tipo generico), il risultato è il nome del membro associato a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="55e19-151">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="55e19-152">Nessun membro contenitore (ad esempio a livello di assembly o attributi applicati a tipi)</span><span class="sxs-lookup"><span data-stu-id="55e19-152">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="55e19-153">Valore predefinito del parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="55e19-153">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="55e19-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55e19-154">See also</span></span>

- [<span data-ttu-id="55e19-155">Attributi</span><span class="sxs-lookup"><span data-stu-id="55e19-155">Attributes</span></span>](attributes.md)
- [<span data-ttu-id="55e19-156">Argomenti denominati</span><span class="sxs-lookup"><span data-stu-id="55e19-156">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)
- [<span data-ttu-id="55e19-157">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="55e19-157">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)
