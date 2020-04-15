---
title: 'Attributi riservati di C: rilevamento delle informazioni sul chiamante'
ms.date: 04/09/2020
description: Questi attributi indicano al compilatore di generare informazioni sul codice che chiama un membro. Utilizzare CallerFilePath, CallerLineNumber e CallerMemberName per fornire informazioni di traccia dettagliate
ms.openlocfilehash: ee061d4cae35bdcc0b89007e360e94fee8c5f87c
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389877"
---
# <a name="reserved-attributes-determine-caller-information"></a><span data-ttu-id="6eafa-104">Attributi riservati: determinare le informazioni sul chiamante</span><span class="sxs-lookup"><span data-stu-id="6eafa-104">Reserved attributes: Determine caller information</span></span>

<span data-ttu-id="6eafa-105">Utilizzando gli attributi info, si ottengono informazioni sul chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="6eafa-105">Using info attributes, you obtain information about the caller to a method.</span></span> <span data-ttu-id="6eafa-106">Ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del membro del chiamante.</span><span class="sxs-lookup"><span data-stu-id="6eafa-106">You obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="6eafa-107">È possibile ottenere informazioni sul chiamante usando gli attributi applicati ai parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="6eafa-107">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="6eafa-108">Ogni parametro facoltativo specifica un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="6eafa-108">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="6eafa-109">Nella tabella seguente sono elencati gli attributi di informazioni sul chiamante definiti nello spazio dei nomi <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="6eafa-109">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="6eafa-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="6eafa-110">Attribute</span></span>|<span data-ttu-id="6eafa-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6eafa-111">Description</span></span>|<span data-ttu-id="6eafa-112">Type</span><span class="sxs-lookup"><span data-stu-id="6eafa-112">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="6eafa-113">Percorso completo del file di origine contenente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="6eafa-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="6eafa-114">Il percorso completo è il percorso in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6eafa-114">The full path is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="6eafa-115">Numero di riga nel file di origine da cui viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="6eafa-115">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="6eafa-116">Nome di una proprietà o di un metodo del chiamante.</span><span class="sxs-lookup"><span data-stu-id="6eafa-116">Method name or property name of the caller.</span></span>|`String`|

<span data-ttu-id="6eafa-117">Queste informazioni consentono di scrivere l'analisi, il debug e la creazione di strumenti di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="6eafa-117">This information helps you write tracing, debugging, and create diagnostic tools.</span></span> <span data-ttu-id="6eafa-118">Nell'esempio seguente viene illustrato come utilizzare gli attributi di informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="6eafa-118">The following example shows how to use caller info attributes.</span></span> <span data-ttu-id="6eafa-119">Per ogni chiamata al metodo `TraceMessage`, le informazioni sul chiamante vengono sostituite come argomenti dei parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="6eafa-119">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [CallerMemberName] string memberName = "",
        [CallerFilePath] string sourceFilePath = "",
        [CallerLineNumber] int sourceLineNumber = 0)
{
    Trace.WriteLine("message: " + message);
    Trace.WriteLine("member name: " + memberName);
    Trace.WriteLine("source file path: " + sourceFilePath);
    Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

<span data-ttu-id="6eafa-120">Specificare un valore predefinito esplicito per ogni parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6eafa-120">You specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="6eafa-121">Non è possibile applicare gli attributi di informazioni del chiamante a parametri non specificati come facoltativi.</span><span class="sxs-lookup"><span data-stu-id="6eafa-121">You can't apply caller info attributes to parameters that aren't specified as optional.</span></span> <span data-ttu-id="6eafa-122">Gli attributi info del chiamante non rendono un parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6eafa-122">The caller info attributes don't make a parameter optional.</span></span> <span data-ttu-id="6eafa-123">ma influiscono sul valore predefinito passato quando l'argomento è omesso.</span><span class="sxs-lookup"><span data-stu-id="6eafa-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span> <span data-ttu-id="6eafa-124">I valori delle informazioni del chiamante vengono generati come valori letterali nel linguaggio intermedio (IL) in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6eafa-124">Caller info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="6eafa-125">A differenza dei risultati della proprietà <xref:System.Exception.StackTrace%2A> per le eccezioni, i risultati non sono interessati da offuscamento.</span><span class="sxs-lookup"><span data-stu-id="6eafa-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span> <span data-ttu-id="6eafa-126">È possibile fornire esplicitamente gli argomenti facoltativi per esaminare o nascondere le informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="6eafa-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

### <a name="member-names"></a><span data-ttu-id="6eafa-127">Nomi dei membri</span><span class="sxs-lookup"><span data-stu-id="6eafa-127">Member names</span></span>

<span data-ttu-id="6eafa-128">È possibile utilizzare l'attributo `CallerMemberName` per specificare il nome del membro come argomento `String` al metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="6eafa-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="6eafa-129">Usando questa tecnica, si evita il problema per cui il **refactoring di ridenominazione** non modifica i valori `String`.</span><span class="sxs-lookup"><span data-stu-id="6eafa-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="6eafa-130">Questo vantaggio è particolarmente utile per le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="6eafa-130">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="6eafa-131">Utilizzo della tracciatura e delle routine di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="6eafa-131">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="6eafa-132">Implementazione dell'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> durante l'associazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="6eafa-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="6eafa-133">Questa interfaccia consente alla proprietà di un oggetto di notificare a un controllo associato la modifica della proprietà stessa in modo che il controllo possa visualizzare le informazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="6eafa-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="6eafa-134">Senza l'attributo `CallerMemberName`, è necessario specificare il nome della proprietà come valore letterale.</span><span class="sxs-lookup"><span data-stu-id="6eafa-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="6eafa-135">Nel grafico seguente vengono mostrati i nomi dei membri restituiti quando si utilizza l'attributo `CallerMemberName`.</span><span class="sxs-lookup"><span data-stu-id="6eafa-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>

|<span data-ttu-id="6eafa-136">Le chiamate avvengono entro</span><span class="sxs-lookup"><span data-stu-id="6eafa-136">Calls occur within</span></span>|<span data-ttu-id="6eafa-137">Nome del membro restituito</span><span class="sxs-lookup"><span data-stu-id="6eafa-137">Member name result</span></span>|
|-|-|
|<span data-ttu-id="6eafa-138">Metodo, proprietà o evento</span><span class="sxs-lookup"><span data-stu-id="6eafa-138">Method, property, or event</span></span>|<span data-ttu-id="6eafa-139">Nome del metodo, della proprietà o dell'evento da cui la chiamata ha avuto origine.</span><span class="sxs-lookup"><span data-stu-id="6eafa-139">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="6eafa-140">Costruttore</span><span class="sxs-lookup"><span data-stu-id="6eafa-140">Constructor</span></span>|<span data-ttu-id="6eafa-141">Stringa ".ctor"</span><span class="sxs-lookup"><span data-stu-id="6eafa-141">The string ".ctor"</span></span>|
|<span data-ttu-id="6eafa-142">Costruttore statico</span><span class="sxs-lookup"><span data-stu-id="6eafa-142">Static constructor</span></span>|<span data-ttu-id="6eafa-143">Stringa ".cctor"</span><span class="sxs-lookup"><span data-stu-id="6eafa-143">The string ".cctor"</span></span>|
|<span data-ttu-id="6eafa-144">Distruttore</span><span class="sxs-lookup"><span data-stu-id="6eafa-144">Destructor</span></span>|<span data-ttu-id="6eafa-145">Stringa "Finalize"</span><span class="sxs-lookup"><span data-stu-id="6eafa-145">The string "Finalize"</span></span>|
|<span data-ttu-id="6eafa-146">Operatori o conversioni definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="6eafa-146">User-defined operators or conversions</span></span>|<span data-ttu-id="6eafa-147">Nome generato per il membro, ad esempio "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="6eafa-147">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="6eafa-148">Costruttore dell'attributo</span><span class="sxs-lookup"><span data-stu-id="6eafa-148">Attribute constructor</span></span>|<span data-ttu-id="6eafa-149">Nome del metodo o della proprietà cui viene applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="6eafa-149">The name of the method or property to which the attribute is applied.</span></span> <span data-ttu-id="6eafa-150">Se l'attributo è un qualsiasi elemento in un membro (ad esempio un parametro, un valore restituito o un parametro di tipo generico), il risultato è il nome del membro associato a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="6eafa-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="6eafa-151">Nessun membro contenitore (ad esempio a livello di assembly o attributi applicati a tipi)</span><span class="sxs-lookup"><span data-stu-id="6eafa-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="6eafa-152">Valore predefinito del parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6eafa-152">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="6eafa-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6eafa-153">See also</span></span>

- [<span data-ttu-id="6eafa-154">Argomenti denominati e facoltativi</span><span class="sxs-lookup"><span data-stu-id="6eafa-154">Named and Optional Arguments</span></span>](../../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="6eafa-155">Attributi</span><span class="sxs-lookup"><span data-stu-id="6eafa-155">Attributes</span></span>](../../../standard/attributes/index.md)
