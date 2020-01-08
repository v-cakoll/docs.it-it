---
title: Panoramica sul modello di programmazione con attributi (MEF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MEF, attributed programming model
- attributed programming model [MEF]
ms.assetid: 49b787ff-2741-4836-ad51-c3017dc592d4
ms.openlocfilehash: c6b1093d2e821a55cc5513b077a270748a780b71
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347633"
---
# <a name="attributed-programming-model-overview-mef"></a><span data-ttu-id="c28d5-102">Panoramica sul modello di programmazione con attributi (MEF)</span><span class="sxs-lookup"><span data-stu-id="c28d5-102">Attributed Programming Model Overview (MEF)</span></span>

<span data-ttu-id="c28d5-103">In Managed Extensibility Framework (MEF) un *modello di programmazione* è un metodo particolare per definire l'insieme di oggetti concettuali su cui opera MEF,</span><span class="sxs-lookup"><span data-stu-id="c28d5-103">In the Managed Extensibility Framework (MEF), a *programming model* is a particular method of defining the set of conceptual objects on which MEF operates.</span></span> <span data-ttu-id="c28d5-104">incluse le parti, le importazioni e le esportazioni.</span><span class="sxs-lookup"><span data-stu-id="c28d5-104">These conceptual objects include parts, imports, and exports.</span></span> <span data-ttu-id="c28d5-105">MEF usa questi oggetti, ma non specifica il modo in cui devono essere rappresentati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-105">MEF uses these objects, but does not specify how they should be represented.</span></span> <span data-ttu-id="c28d5-106">È quindi possibile usare una vasta gamma di modelli di programmazione, inclusi i modelli di programmazione personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-106">Therefore, a wide variety of programming models are possible, including customized programming models.</span></span>

<span data-ttu-id="c28d5-107">Il modello di programmazione predefinito usato in MEF è il *modello di programmazione con attributi*.</span><span class="sxs-lookup"><span data-stu-id="c28d5-107">The default programming model used in MEF is the *attributed programming model*.</span></span> <span data-ttu-id="c28d5-108">Nel modello di programmazione con attributi le parti, le importazioni, le esportazioni e gli altri oggetti sono definiti con attributi che decorano le classi normali di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c28d5-108">In the attributed programming model parts, imports, exports, and other objects are defined with attributes that decorate ordinary .NET Framework classes.</span></span> <span data-ttu-id="c28d5-109">Questo argomento illustra come usare gli attributi forniti dal modello di programmazione con attributi per creare un'applicazione MEF.</span><span class="sxs-lookup"><span data-stu-id="c28d5-109">This topic explains how to use the attributes provided by the attributed programming model to create a MEF application.</span></span>

<a name="import_and_export_basics"></a>

## <a name="import-and-export-basics"></a><span data-ttu-id="c28d5-110">Nozioni fondamentali su importazione ed esportazione</span><span class="sxs-lookup"><span data-stu-id="c28d5-110">Import and Export Basics</span></span>

<span data-ttu-id="c28d5-111">Un' *esportazione* è un valore fornito da una parte ad altre parti di un contenitore e un' *importazione* è un requisito espresso da una parte al contenitore, da soddisfare con le esportazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="c28d5-111">An *export* is a value that a part provides to other parts in the container, and an *import* is a requirement that a part expresses to the container, to be filled from the available exports.</span></span> <span data-ttu-id="c28d5-112">Nel modello di programmazione con attributi le importazioni e le esportazioni sono dichiarate tramite la decorazione di classi o membri con gli attributi `Import` e `Export` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-112">In the attributed programming model, imports and exports are declared by decorating classes or members with the `Import` and `Export` attributes.</span></span> <span data-ttu-id="c28d5-113">L'attributo `Export` può decorare una classe, un campo, una proprietà o un metodo, mentre l'attributo `Import` può decorare un campo, una proprietà o un parametro di costruttore.</span><span class="sxs-lookup"><span data-stu-id="c28d5-113">The `Export` attribute can decorate a class, field, property, or method, while the `Import` attribute can decorate a field, property, or constructor parameter.</span></span>

<span data-ttu-id="c28d5-114">Per associare un'importazione a un'esportazione, è necessario che l'importazione e l'esportazione abbiano lo stesso *contratto*.</span><span class="sxs-lookup"><span data-stu-id="c28d5-114">In order for an import to be matched with an export, the import and export must have the same *contract*.</span></span> <span data-ttu-id="c28d5-115">Il contratto è costituito da una stringa, definita *nome contratto*, e dal tipo dell'oggetto esportato o importato, definito *tipo di contratto*.</span><span class="sxs-lookup"><span data-stu-id="c28d5-115">The contract consists of a string, called the *contract name*, and the type of the exported or imported object, called the *contract type*.</span></span> <span data-ttu-id="c28d5-116">Un'esportazione è in grado di soddisfare un'importazione specifica solo se il nome e il tipo di contratto corrispondono.</span><span class="sxs-lookup"><span data-stu-id="c28d5-116">Only if both the contract name and contract type match is an export considered to fulfill a particular import.</span></span>

<span data-ttu-id="c28d5-117">Uno o entrambi i parametri del contratto possono essere impliciti o espliciti.</span><span class="sxs-lookup"><span data-stu-id="c28d5-117">Either or both of the contract parameters can be implicit or explicit.</span></span> <span data-ttu-id="c28d5-118">Il codice seguente mostra una classe che dichiara un'importazione di base.</span><span class="sxs-lookup"><span data-stu-id="c28d5-118">The following code shows a class that declares a basic import.</span></span>

```vb
Public Class MyClass1
    <Import()>
    Public Property MyAddin As IMyAddin
End Class
```

```csharp
public class MyClass
{
    [Import]
    public IMyAddin MyAddin { get; set; }
}
```

<span data-ttu-id="c28d5-119">In questa importazione all'attributo `Import` non è associato alcun parametro nome contratto o tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="c28d5-119">In this import, the `Import` attribute has neither a contract type nor a contract name parameter attached.</span></span> <span data-ttu-id="c28d5-120">Entrambi i parametri saranno quindi dedotti dalla proprietà decorata.</span><span class="sxs-lookup"><span data-stu-id="c28d5-120">Therefore, both will be inferred from the decorated property.</span></span> <span data-ttu-id="c28d5-121">In questo caso il tipo di contratto sarà `IMyAddin`e il nome del contratto sarà una stringa univoca creata dal tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="c28d5-121">In this case, the contract type will be `IMyAddin`, and the contract name will be a unique string created from the contract type.</span></span> <span data-ttu-id="c28d5-122">In altri termini, il nome del contratto corrisponderà solo alle esportazioni i cui nomi sono stati dedotti dal tipo `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-122">(In other words, the contract name will match only exports whose names are also inferred from the type `IMyAddin`.)</span></span>

<span data-ttu-id="c28d5-123">Di seguito è illustrata un'esportazione corrispondente all'importazione precedente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-123">The following shows an export that matches the previous import.</span></span>

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="c28d5-124">In questa esportazione il tipo di contratto è `IMyAddin` poiché è specificato come parametro dell'attributo `Export` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-124">In this export, the contract type is `IMyAddin` because it is specified as a parameter of the `Export` attribute.</span></span> <span data-ttu-id="c28d5-125">Il tipo esportato deve essere uguale al tipo di contratto, deve derivare dal tipo di contratto o deve implementare il tipo di contratto come se fosse un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c28d5-125">The exported type must be either the same as the contract type, derive from the contract type, or implement the contract type if it is an interface.</span></span> <span data-ttu-id="c28d5-126">In questa esportazione il tipo effettivo `MyLogger` implementa l'interfaccia `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-126">In this export, the actual type `MyLogger` implements the interface `IMyAddin`.</span></span> <span data-ttu-id="c28d5-127">Il nome del contratto è dedotto dal tipo di contratto. Questa esportazione corrisponderà quindi all'importazione precedente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-127">The contract name is inferred from the contract type, which means that this export will match the previous import.</span></span>

> [!NOTE]
> <span data-ttu-id="c28d5-128">Le esportazioni e le importazioni devono essere in genere dichiarate nelle classi o nei membri pubblici.</span><span class="sxs-lookup"><span data-stu-id="c28d5-128">Exports and imports should usually be declared on public classes or members.</span></span> <span data-ttu-id="c28d5-129">Sono supportate altre dichiarazioni, ma l'esportazione o l'importazione di un membro privato, protetto o interno influisce negativamente sul modello di isolamento per la parte e non è quindi consigliata.</span><span class="sxs-lookup"><span data-stu-id="c28d5-129">Other declarations are supported, but exporting or importing a private, protected, or internal member breaks the isolation model for the part and is therefore not recommended.</span></span>

<span data-ttu-id="c28d5-130">Per fare in modo che l'esportazione e l'importazione siano considerate corrispondenti, il tipo di contratto deve corrispondere esattamente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-130">The contract type must match exactly for the export and import to be considered a match.</span></span> <span data-ttu-id="c28d5-131">Esaminare l'esportazione seguente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-131">Consider the following export.</span></span>

```vb
<Export()> 'WILL NOT match the previous import!
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export] //WILL NOT match the previous import!
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="c28d5-132">In questa esportazione il tipo di contratto è `MyLogger` invece di `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-132">In this export, the contract type is `MyLogger` instead of `IMyAddin`.</span></span> <span data-ttu-id="c28d5-133">Anche se `MyLogger` implementa `IMyAddin`ed è quindi possibile eseguirne il casting in un oggetto `IMyAddin` , questa esportazione non corrisponderà all'importazione precedente perché i tipi di contratto non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="c28d5-133">Even though `MyLogger` implements `IMyAddin`, and therefore could be cast to an `IMyAddin` object, this export will not match the previous import because the contract types are not the same.</span></span>

<span data-ttu-id="c28d5-134">In genere, non è necessario specificare il nome del contratto e la maggior parte dei contratti dovrebbe essere definita in termini di tipo di contratto e metadati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-134">In general, it is not necessary to specify the contract name, and most contracts should be defined in terms of the contract type and metadata.</span></span> <span data-ttu-id="c28d5-135">In alcune circostanze, tuttavia, è importante specificare direttamente il nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="c28d5-135">However, under certain circumstances, it is important to specify the contract name directly.</span></span> <span data-ttu-id="c28d5-136">Il caso più comune consiste nell'esportazione di alcuni valori che condividono un tipo comune, ad esempio le primitive, da parte di una classe.</span><span class="sxs-lookup"><span data-stu-id="c28d5-136">The most common case is when a class exports several values that share a common type, such as primitives.</span></span> <span data-ttu-id="c28d5-137">Il nome del contratto può essere specificato come primo parametro dell'attributo `Import` o `Export` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-137">The contract name can be specified as the first parameter of the `Import` or `Export` attribute.</span></span> <span data-ttu-id="c28d5-138">Il codice seguente mostra un'importazione e un'esportazione con un nome contratto specificato `MajorRevision`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-138">The following code shows an import and an export with a specified contract name of `MajorRevision`.</span></span>

```vb
Public Class MyExportClass

    'This one will match
    <Export("MajorRevision")>
    Public ReadOnly Property MajorRevision As Integer
        Get
            Return 4
        End Get
    End Property

    <Export("MinorRevision")>
    Public ReadOnly Property MinorRevision As Integer
        Get
            Return 16
        End Get
    End Property
End Class
```

```csharp
public class MyClass
{
    [Import("MajorRevision")]
    public int MajorRevision { get; set; }
}

public class MyExportClass
{
    [Export("MajorRevision")] //This one will match.
    public int MajorRevision = 4;

    [Export("MinorRevision")]
    public int MinorRevision = 16;
}
```

<span data-ttu-id="c28d5-139">Se il tipo di contratto non è specificato, sarà comunque dedotto dal tipo di importazione o esportazione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-139">If the contract type is not specified, it will still be inferred from the type of the import or export.</span></span> <span data-ttu-id="c28d5-140">Anche se il nome del contratto è specificato in modo esplicito, tuttavia, anche il tipo di contratto deve corrispondere esattamente per fare in modo che l'importazione e l'esportazione siano considerate corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c28d5-140">However, even if the contract name is specified explicitly, the contract type must also match exactly for the import and export to be considered a match.</span></span> <span data-ttu-id="c28d5-141">Ad esempio, se il campo `MajorRevision` fosse una stringa, i tipi di contratto dedotti non corrisponderebbero e l'esportazione non corrisponderebbe all'importazione, nonostante entrambe abbiano lo stesso nome di contratto.</span><span class="sxs-lookup"><span data-stu-id="c28d5-141">For example, if the `MajorRevision` field was a string, the inferred contract types would not match and the export would not match the import, despite having the same contract name.</span></span>

### <a name="importing-and-exporting-a-method"></a><span data-ttu-id="c28d5-142">Importazione ed esportazione di un metodo</span><span class="sxs-lookup"><span data-stu-id="c28d5-142">Importing and Exporting a Method</span></span>

<span data-ttu-id="c28d5-143">L'attributo `Export` può anche decorare un metodo, in modo analogo a una classe, una proprietà o una funzione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-143">The `Export` attribute can also decorate a method, in the same way as a class, property, or function.</span></span> <span data-ttu-id="c28d5-144">Le esportazioni di metodi devono specificare un tipo o un nome di contratto, poiché il tipo non può essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="c28d5-144">Method exports must specify a contract type or contract name, as the type cannot be inferred.</span></span> <span data-ttu-id="c28d5-145">Il tipo specificato può essere un delegato personalizzato o un tipo generico, ad esempio `Func`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-145">The specified type can be either a custom delegate or a generic type, such as `Func`.</span></span> <span data-ttu-id="c28d5-146">La classe seguente esporta un metodo denominato `DoSomething`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-146">The following class exports a method named `DoSomething`.</span></span>

```vb
Public Class MyAddin

    'Explicitly specifying a generic type
    <Export(GetType(Func(Of Integer, String)))>
    Public Function DoSomething(ByVal TheParam As Integer) As String
        Return Nothing 'Function body goes here
    End Function

End Class
```

```csharp
public class MyAddin
{
    //Explicitly specifying a generic type.
    [Export(typeof(Func<int, string>))]
    public string DoSomething(int TheParam);
}
```

<span data-ttu-id="c28d5-147">In questa classe il metodo `DoSomething` accetta un singolo parametro `int` e restituisce un oggetto `string`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-147">In this class, the `DoSomething` method takes a single `int` parameter and returns a `string`.</span></span> <span data-ttu-id="c28d5-148">Per corrispondere a questa esportazione, la parte che esegue l'importazione deve dichiarare un membro appropriato.</span><span class="sxs-lookup"><span data-stu-id="c28d5-148">To match this export, the importing part must declare an appropriate member.</span></span> <span data-ttu-id="c28d5-149">La classe seguente importa il metodo `DoSomething` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-149">The following class imports the `DoSomething` method.</span></span>

```vb
Public Class MyClass1

    'Contract name must match!
    <Import()>
    Public Property MajorRevision As Func(Of Integer, String)
End Class
```

```csharp
public class MyClass
{
    [Import] //Contract name must match!
    public Func<int, string> DoSomething { get; set; }
}
```

<span data-ttu-id="c28d5-150">Per altre informazioni su come usare l'oggetto `Func<T, T>` , vedere <xref:System.Func%602>.</span><span class="sxs-lookup"><span data-stu-id="c28d5-150">For more information about how to use of the `Func<T, T>` object, see <xref:System.Func%602>.</span></span>

<a name="types_of_imports"></a>

## <a name="types-of-imports"></a><span data-ttu-id="c28d5-151">Tipi di importazioni</span><span class="sxs-lookup"><span data-stu-id="c28d5-151">Types of Imports</span></span>

<span data-ttu-id="c28d5-152">MEF supporta diversi tipi di importazione, tra cui l'importazione dinamica, differita, essenziale o facoltativa.</span><span class="sxs-lookup"><span data-stu-id="c28d5-152">MEF support several import types, including dynamic, lazy, prerequisite, and optional.</span></span>

### <a name="dynamic-imports"></a><span data-ttu-id="c28d5-153">Importazioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="c28d5-153">Dynamic Imports</span></span>

<span data-ttu-id="c28d5-154">In alcuni casi è possibile che la classe che esegue l'importazione voglia corrispondere a esportazioni di qualsiasi tipo con un nome di contratto specifico.</span><span class="sxs-lookup"><span data-stu-id="c28d5-154">In some cases, the importing class may want to match exports of any type that have a particular contract name.</span></span> <span data-ttu-id="c28d5-155">In questo scenario la classe può dichiarare una *importazione dinamica*.</span><span class="sxs-lookup"><span data-stu-id="c28d5-155">In this scenario, the class can declare a *dynamic import*.</span></span> <span data-ttu-id="c28d5-156">L'importazione seguente corrisponde a qualsiasi esportazione con nome contratto "TheString".</span><span class="sxs-lookup"><span data-stu-id="c28d5-156">The following import matches any export with contract name "TheString".</span></span>

```vb
Public Class MyClass1

    <Import("TheString")>
    Public Property MyAddin

End Class
```

```csharp
public class MyClass
{
    [Import("TheString")]
    public dynamic MyAddin { get; set; }
}
```

<span data-ttu-id="c28d5-157">Quando il tipo di contratto è dedotto dalla parola chiave `dynamic` , corrisponderà a qualsiasi tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="c28d5-157">When the contract type is inferred from the `dynamic` keyword, it will match any contract type.</span></span> <span data-ttu-id="c28d5-158">In questo caso un'importazione deve **sempre** specificare un nome di contratto a cui corrispondere.</span><span class="sxs-lookup"><span data-stu-id="c28d5-158">In this case, an import should **always** specify a contract name to match on.</span></span> <span data-ttu-id="c28d5-159">Se non viene specificato alcun nome di contratto, l'importazione verrà considerata non corrispondente ad alcuna esportazione. Entrambe le esportazioni seguenti corrisponderanno all'importazione precedente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-159">(If no contract name is specified, the import will be considered to match no exports.) Both of the following exports would match the previous import.</span></span>

```vb
<Export("TheString", GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class

<Export("TheString")>
Public Class MyToolbar

End Class
```

```csharp
[Export("TheString", typeof(IMyAddin))]
public class MyLogger : IMyAddin { }

[Export("TheString")]
public class MyToolbar { }
```

<span data-ttu-id="c28d5-160">La classe che esegue l'importazione deve essere ovviamente preparata per la gestione di un oggetto di tipo arbitrario.</span><span class="sxs-lookup"><span data-stu-id="c28d5-160">Obviously, the importing class must be prepared to deal with an object of arbitrary type.</span></span>

### <a name="lazy-imports"></a><span data-ttu-id="c28d5-161">Importazioni differite</span><span class="sxs-lookup"><span data-stu-id="c28d5-161">Lazy Imports</span></span>

<span data-ttu-id="c28d5-162">In alcuni casi è possibile che la classe che esegue l'importazione necessiti di un riferimento indiretto all'oggetto importato, in modo che non siano create immediatamente istanze dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c28d5-162">In some cases, the importing class may require an indirect reference to the imported object, so that the object is not instantiated immediately.</span></span> <span data-ttu-id="c28d5-163">In questo scenario la classe può dichiarare un' *importazione differita* usando un tipo di contratto `Lazy<T>`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-163">In this scenario, the class can declare a *lazy import* by using a contract type of `Lazy<T>`.</span></span> <span data-ttu-id="c28d5-164">La proprietà di importazione seguente dichiara un'importazione differita.</span><span class="sxs-lookup"><span data-stu-id="c28d5-164">The following importing property declares a lazy import.</span></span>

```vb
Public Class MyClass1

    <Import()>
    Public Property MyAddin As Lazy(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [Import]
    public Lazy<IMyAddin> MyAddin { get; set; }
}
```

<span data-ttu-id="c28d5-165">Dal punto di vista del motore della composizione, un tipo di contratto `Lazy<T>` è considerato identico al tipo di contratto `T`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-165">From the point of view of the composition engine, a contract type of `Lazy<T>` is considered identical to contract type of `T`.</span></span> <span data-ttu-id="c28d5-166">L'importazione precedente, quindi, corrisponderebbe all'esportazione seguente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-166">Therefore, the previous import would match the following export.</span></span>

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="c28d5-167">Il nome e il tipo di contratto possono essere specificati nell'attributo `Import` per un'importazione differita, come illustrato in precedenza nella sezione "Nozioni fondamentali su importazione ed esportazione".</span><span class="sxs-lookup"><span data-stu-id="c28d5-167">The contract name and contract type can be specified in the `Import` attribute for a lazy import, as described earlier in the "Basic Imports and Exports" section.</span></span>

### <a name="prerequisite-imports"></a><span data-ttu-id="c28d5-168">Importazioni essenziali</span><span class="sxs-lookup"><span data-stu-id="c28d5-168">Prerequisite Imports</span></span>

<span data-ttu-id="c28d5-169">Le parti MEF esportate sono in genere create dal motore della composizione, in risposta a una richiesta diretta o alla necessità di soddisfare un'importazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-169">Exported MEF parts are typically created by the composition engine, in response to a direct request or the need to fill a matched import.</span></span> <span data-ttu-id="c28d5-170">Per impostazione predefinita, quando si crea una parte, il motore della composizione usa il costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="c28d5-170">By default, when creating a part, the composition engine uses the parameter-less constructor.</span></span> <span data-ttu-id="c28d5-171">Per fare in modo che il motore usi un costruttore diverso, è possibile contrassegnarlo con l'attributo `ImportingConstructor` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-171">To make the engine use a different constructor, you can mark it with the `ImportingConstructor` attribute.</span></span>

<span data-ttu-id="c28d5-172">Ogni parte può avere solo un costruttore per l'uso da parte del motore della composizione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-172">Each part may have only one constructor for use by the composition engine.</span></span> <span data-ttu-id="c28d5-173">Se non si specifica alcun costruttore senza parametri e alcun attributo `ImportingConstructor` o se si specifica più di un attributo `ImportingConstructor`, si verificherà un errore.</span><span class="sxs-lookup"><span data-stu-id="c28d5-173">Providing no parameterless constructor and no `ImportingConstructor` attribute, or providing more than one `ImportingConstructor` attribute, will produce an error.</span></span>

<span data-ttu-id="c28d5-174">Per compilare i parametri di un costruttore contrassegnato con l'attributo `ImportingConstructor` , tutti questi parametri sono dichiarati automaticamente come importazioni.</span><span class="sxs-lookup"><span data-stu-id="c28d5-174">To fill the parameters of a constructor marked with the `ImportingConstructor` attribute, all of those parameters are automatically declared as imports.</span></span> <span data-ttu-id="c28d5-175">Si tratta di una soluzione utile per dichiarare importazioni usate durante l'inizializzazione delle parti.</span><span class="sxs-lookup"><span data-stu-id="c28d5-175">This is a convenient way to declare imports that are used during part initialization.</span></span> <span data-ttu-id="c28d5-176">La classe seguente usa `ImportingConstructor` per dichiarare un'importazione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-176">The following class uses `ImportingConstructor` to declare an import.</span></span>

```vb
Public Class MyClass1

    Private _theAddin As IMyAddin

    'Parameterless constructor will NOT be used
    'because the ImportingConstructor
    'attribute is present.
    Public Sub New()

    End Sub

    'This constructor will be used.
    'An import with contract type IMyAddin
    'is declared automatically.
    <ImportingConstructor()>
    Public Sub New(ByVal MyAddin As IMyAddin)
        _theAddin = MyAddin
    End Sub

End Class
```

```csharp
public class MyClass
{
    private IMyAddin _theAddin;

    //Parameterless constructor will NOT be
    //used because the ImportingConstructor
    //attribute is present.
    public MyClass() { }

    //This constructor will be used.
    //An import with contract type IMyAddin is
    //declared automatically.
    [ImportingConstructor]
    public MyClass(IMyAddin MyAddin)
    {
        _theAddin = MyAddin;
    }
}
```

<span data-ttu-id="c28d5-177">Per impostazione predefinita, l'attributo `ImportingConstructor` usa i tipi e nomi di contratto dedotti per tutte le importazioni di parametri.</span><span class="sxs-lookup"><span data-stu-id="c28d5-177">By default, the `ImportingConstructor` attribute uses inferred contract types and contract names for all of the parameter imports.</span></span> <span data-ttu-id="c28d5-178">È possibile eseguire l'override di questa procedura dichiarando i parametri con gli attributi `Import` , che possono quindi definire in modo esplicito il tipo e il nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="c28d5-178">It is possible to override this by decorating the parameters with `Import` attributes, which can then define the contract type and contract name explicitly.</span></span> <span data-ttu-id="c28d5-179">Il codice seguente illustra un costruttore che usa questa sintassi per importare una classe derivata invece di una classe padre.</span><span class="sxs-lookup"><span data-stu-id="c28d5-179">The following code demonstrates a constructor that uses this syntax to import a derived class instead of a parent class.</span></span>

```vb
<ImportingConstructor()>
Public Sub New(<Import(GetType(IMySubAddin))> ByVal MyAddin As IMyAddin)

End Sub
```

```csharp
[ImportingConstructor]
public MyClass([Import(typeof(IMySubAddin))]IMyAddin MyAddin)
{
    _theAddin = MyAddin;
}
```

<span data-ttu-id="c28d5-180">In particolare, occorre prestare attenzione ai parametri di raccolta.</span><span class="sxs-lookup"><span data-stu-id="c28d5-180">In particular, you should be careful with collection parameters.</span></span> <span data-ttu-id="c28d5-181">Se, ad esempio, si specifica `ImportingConstructor` su un costruttore con parametro di tipo `IEnumerable<int>`, l'importazione corrisponderà a una esportazione di tipo `IEnumerable<int>`, invece che a un insieme di esportazioni di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-181">For example, if you specify `ImportingConstructor` on a constructor with a parameter of type `IEnumerable<int>`, the import will match a single export of type `IEnumerable<int>`, instead of a set of exports of type `int`.</span></span> <span data-ttu-id="c28d5-182">Per ottenere la corrispondenza a un insieme di esportazioni di tipo `int`, è necessario decorare il parametro con l'attributo `ImportMany` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-182">To match a set of exports of type `int`, you have to decorate the parameter with the `ImportMany` attribute.</span></span>

<span data-ttu-id="c28d5-183">I parametri dichiarati come importazioni dall'attributo `ImportingConstructor` sono contrassegnati anche come *importazioni essenziali*.</span><span class="sxs-lookup"><span data-stu-id="c28d5-183">Parameters declared as imports by the `ImportingConstructor` attribute are also marked as *prerequisite imports*.</span></span> <span data-ttu-id="c28d5-184">MEF permette in genere a esportazioni e importazioni di formare un *ciclo*.</span><span class="sxs-lookup"><span data-stu-id="c28d5-184">MEF normally allows exports and imports to form a *cycle*.</span></span> <span data-ttu-id="c28d5-185">Ad esempio, un ciclo è rappresentato dall'oggetto A che importa l'oggetto B, che a sua volta importa l'oggetto A. In circostanze normali un ciclo non rappresenta un problema e il contenitore di composizione costruisce normalmente entrambi gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="c28d5-185">For example, a cycle is where object A imports object B, which in turn imports object A. Under ordinary circumstances, a cycle is not a problem, and the composition container constructs both objects normally.</span></span>

<span data-ttu-id="c28d5-186">Se il costruttore di una parte necessita di un valore importato, tale oggetto non può essere incluso in un ciclo.</span><span class="sxs-lookup"><span data-stu-id="c28d5-186">When an imported value is required by the constructor of a part, that object cannot participate in a cycle.</span></span> <span data-ttu-id="c28d5-187">Se per la costruzione dell'oggetto A è necessaria prima di tutto la costruzione dell'oggetto B e l'oggetto B importa l'oggetto A, il ciclo non potrà essere risolto e si verificherà un errore di composizione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-187">If object A requires that object B be constructed before it can be constructed itself, and object B imports object A, then the cycle will be unable to resolve and a composition error will occur.</span></span> <span data-ttu-id="c28d5-188">Le importazioni dichiarate nei parametri del costruttore sono quindi importazioni essenziali, che devono essere completate prima che sia possibile usare qualsiasi esportazione dall'oggetto che le richiede.</span><span class="sxs-lookup"><span data-stu-id="c28d5-188">Imports declared on constructor parameters are therefore prerequisite imports, which must all be filled before any of the exports from the object that requires them can be used.</span></span>

### <a name="optional-imports"></a><span data-ttu-id="c28d5-189">Importazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="c28d5-189">Optional Imports</span></span>

<span data-ttu-id="c28d5-190">L'attributo `Import` specifica un requisito necessario per il funzionamento della parte.</span><span class="sxs-lookup"><span data-stu-id="c28d5-190">The `Import` attribute specifies a requirement for the part to function.</span></span> <span data-ttu-id="c28d5-191">Se non è possibile soddisfare un'importazione, la composizione della parte avrà esito negativo e la parte non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="c28d5-191">If an import cannot be fulfilled, the composition of that part will fail and the part will not be available.</span></span>

<span data-ttu-id="c28d5-192">È possibile specificare che un'importazione è *facoltativa* usando la proprietà `AllowDefault` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-192">You can specify that an import is *optional* by using the `AllowDefault` property.</span></span> <span data-ttu-id="c28d5-193">In questo caso, la composizione avrà esito positivo anche se l'importazione non corrisponde ad alcuna esportazione disponibile e la proprietà importata verrà impostata sul valore predefinito per il tipo di proprietà (`null` per le proprietà dell'oggetto, `false` per i valori booleani o zero per le proprietà numeriche). La classe seguente usa un'importazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="c28d5-193">In this case, the composition will succeed even if the import does not match any available exports, and the importing property will be set to the default for its property type (`null` for object properties, `false` for Booleans, or zero for numeric properties.) The following class uses an optional import.</span></span>

```vb
Public Class MyClass1

    <Import(AllowDefault:=True)>
    Public Property thePlugin As Plugin

    'If no matching export is available,
    'thePlugin will be set to null.
End Class
```

```csharp
public class MyClass
{
    [Import(AllowDefault = true)]
    public Plugin thePlugin { get; set; }

    //If no matching export is available,
    //thePlugin will be set to null.
}
```

### <a name="importing-multiple-objects"></a><span data-ttu-id="c28d5-194">Importazione di più oggetti</span><span class="sxs-lookup"><span data-stu-id="c28d5-194">Importing Multiple Objects</span></span>

<span data-ttu-id="c28d5-195">La composizione dell'attributo `Import` avrà esito positivo solo se corrisponde a una sola esportazione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-195">The `Import` attribute will only be successfully composed when it matches one and only one export.</span></span> <span data-ttu-id="c28d5-196">Gli altri casi provocheranno un errore di composizione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-196">Other cases will produce a composition error.</span></span> <span data-ttu-id="c28d5-197">Per importare più di un'esportazione che corrisponde allo stesso contratto, usare l'attributo `ImportMany` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-197">To import more than one export that matches the same contract, use the `ImportMany` attribute.</span></span> <span data-ttu-id="c28d5-198">Le importazioni contrassegnate con questo attributo sono sempre facoltative.</span><span class="sxs-lookup"><span data-stu-id="c28d5-198">Imports marked with this attribute are always optional.</span></span> <span data-ttu-id="c28d5-199">Ad esempio, la composizione avrà esito positivo se non sono presenti esportazioni corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c28d5-199">For example, composition will not fail if no matching exports are present.</span></span> <span data-ttu-id="c28d5-200">La classe seguente importa qualsiasi numero di esportazioni di tipo `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-200">The following class imports any number of exports of type `IMyAddin`.</span></span>

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<IMyAddin> MyAddin { get; set; }
}
```

<span data-ttu-id="c28d5-201">È possibile accedere alla matrice importata usando la normale sintassi e i normali metodi di `IEnumerable<T>` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-201">The imported array can be accessed by using ordinary `IEnumerable<T>` syntax and methods.</span></span> <span data-ttu-id="c28d5-202">È anche possibile usare invece una matrice normale (`IMyAddin[]`).</span><span class="sxs-lookup"><span data-stu-id="c28d5-202">It is also possible to use an ordinary array (`IMyAddin[]`) instead.</span></span>

<span data-ttu-id="c28d5-203">Questo modello può risultare molto importante se lo si usa insieme alla sintassi `Lazy<T>` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-203">This pattern can be very important when you use it in combination with the `Lazy<T>` syntax.</span></span> <span data-ttu-id="c28d5-204">Ad esempio, se si usa `ImportMany`, `IEnumerable<T>`e `Lazy<T>`, sarà possibile importare riferimenti indiretti a qualsiasi numero di oggetti e creare istanze solo degli oggetti che diventano necessari.</span><span class="sxs-lookup"><span data-stu-id="c28d5-204">For example, by using `ImportMany`, `IEnumerable<T>`, and `Lazy<T>`, you can import indirect references to any number of objects and only instantiate the ones that become necessary.</span></span> <span data-ttu-id="c28d5-205">Questo modello è illustrato dalla classe seguente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-205">The following class shows this pattern.</span></span>

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of Lazy(Of IMyAddin))

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<Lazy<IMyAddin>> MyAddin { get; set; }
}
```

<a name="avoiding_discovery"></a>

## <a name="avoiding-discovery"></a><span data-ttu-id="c28d5-206">Evitare l'individuazione</span><span class="sxs-lookup"><span data-stu-id="c28d5-206">Avoiding Discovery</span></span>

<span data-ttu-id="c28d5-207">In alcuni casi è possibile che si voglia evitare l'individuazione di una parte come parte di un catalogo.</span><span class="sxs-lookup"><span data-stu-id="c28d5-207">In some cases, you may want to prevent a part from being discovered as part of a catalog.</span></span> <span data-ttu-id="c28d5-208">Ad esempio, è possibile che la parte sia una classe di base da cui ereditare, ma da non usare.</span><span class="sxs-lookup"><span data-stu-id="c28d5-208">For example, the part may be a base class intended to be inherited from, but not used.</span></span> <span data-ttu-id="c28d5-209">È possibile ottenere questo risultato in due modi.</span><span class="sxs-lookup"><span data-stu-id="c28d5-209">There are two ways to accomplish this.</span></span> <span data-ttu-id="c28d5-210">Si può prima di tutto usare la parola chiave `abstract` nella classe della parte.</span><span class="sxs-lookup"><span data-stu-id="c28d5-210">First, you can use the `abstract` keyword on the part class.</span></span> <span data-ttu-id="c28d5-211">Le classi astratte non forniscono mai esportazioni, anche se possono fornire esportazioni ereditate alle classi da esse derivate.</span><span class="sxs-lookup"><span data-stu-id="c28d5-211">Abstract classes never provide exports, although they can provide inherited exports to classes that derive from them.</span></span>

<span data-ttu-id="c28d5-212">Se non è possibile rendere astratta la classe, sarà possibile decorarla con l'attributo `PartNotDiscoverable` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-212">If the class cannot be made abstract, you can decorate it with the `PartNotDiscoverable` attribute.</span></span> <span data-ttu-id="c28d5-213">Una parte decorata con questo attributo non sarà inclusa in alcun catalogo.</span><span class="sxs-lookup"><span data-stu-id="c28d5-213">A part decorated with this attribute will not be included in any catalogs.</span></span> <span data-ttu-id="c28d5-214">L'esempio seguente illustra questi modelli.</span><span class="sxs-lookup"><span data-stu-id="c28d5-214">The following example demonstrates these patterns.</span></span> <span data-ttu-id="c28d5-215">`DataOne` sarà individuata dal catalogo.</span><span class="sxs-lookup"><span data-stu-id="c28d5-215">`DataOne` will be discovered by the catalog.</span></span> <span data-ttu-id="c28d5-216">Poiché `DataTwo` è astratta, non sarà individuata.</span><span class="sxs-lookup"><span data-stu-id="c28d5-216">Since `DataTwo` is abstract, it will not be discovered.</span></span> <span data-ttu-id="c28d5-217">Poiché `DataThree` ha usato l'attributo `PartNotDiscoverable` , non sarà individuata.</span><span class="sxs-lookup"><span data-stu-id="c28d5-217">Since `DataThree` used the `PartNotDiscoverable` attribute, it will not be discovered.</span></span>

```vb
<Export()>
Public Class DataOne
    'This part will be discovered
    'as normal by the catalog.
End Class

<Export()>
Public MustInherit Class DataTwo
    'This part will not be discovered
    'by the catalog.
End Class

<PartNotDiscoverable()>
<Export()>
Public Class DataThree
    'This part will also not be discovered
    'by the catalog.
End Class
```

```csharp
[Export]
public class DataOne
{
    //This part will be discovered
    //as normal by the catalog.
}

[Export]
public abstract class DataTwo
{
    //This part will not be discovered
    //by the catalog.
}

[PartNotDiscoverable]
[Export]
public class DataThree
{
    //This part will also not be discovered
    //by the catalog.
}
```

<a name="metadata_and_metadata_views"></a>

## <a name="metadata-and-metadata-views"></a><span data-ttu-id="c28d5-218">Metadati e viste dei metadati</span><span class="sxs-lookup"><span data-stu-id="c28d5-218">Metadata and Metadata Views</span></span>

<span data-ttu-id="c28d5-219">Le esportazioni possono fornire informazioni aggiuntive su se stesse, definite *metadati*.</span><span class="sxs-lookup"><span data-stu-id="c28d5-219">Exports can provide additional information about themselves known as *metadata*.</span></span> <span data-ttu-id="c28d5-220">I metadati possono essere usati per trasmettere le proprietà dell'oggetto esportato alla parte che esegue l'importazione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-220">Metadata can be used to convey properties of the exported object to the importing part.</span></span> <span data-ttu-id="c28d5-221">La parte che esegue l'importazione può usare questi dati per decidere quali esportazioni usare oppure per ottenere informazioni su un'esportazione senza doverla costruire.</span><span class="sxs-lookup"><span data-stu-id="c28d5-221">The importing part can use this data to decide which exports to use, or to gather information about an export without having to construct it.</span></span> <span data-ttu-id="c28d5-222">Per questo motivo, un'importazione deve essere differita per usare i metadati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-222">For this reason, an import must be lazy to use metadata.</span></span>

<span data-ttu-id="c28d5-223">Per usare i metadati si dichiara in genere un'interfaccia definita *vista dei metadati*, in cui sono dichiarati i metadati che saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="c28d5-223">To use metadata, you typically declare an interface known as a *metadata view*, which declares what metadata will be available.</span></span> <span data-ttu-id="c28d5-224">L'interfaccia della vista dei metadati deve includere solo proprietà e queste proprietà devono avere `get` funzioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="c28d5-224">The metadata view interface must have only properties, and those properties must have `get` accessors.</span></span> <span data-ttu-id="c28d5-225">L'interfaccia seguente è un esempio di vista dei metadati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-225">The following interface is an example metadata view.</span></span>

```vb
Public Interface IPluginMetadata

    ReadOnly Property Name As String

    <DefaultValue(1)>
    ReadOnly Property Version As Integer

End Interface
```

```csharp
public interface IPluginMetadata
{
    string Name { get; }

    [DefaultValue(1)]
    int Version { get; }
}
```

<span data-ttu-id="c28d5-226">È anche possibile usare una raccolta generica, `IDictionary<string, object>`, come vista dei metadati, ma in questo modo non saranno disponibili i vantaggi correlati alla verifica dei tipi e questa procedura è quindi sconsigliata.</span><span class="sxs-lookup"><span data-stu-id="c28d5-226">It is also possible to use a generic collection, `IDictionary<string, object>`, as a metadata view, but this forfeits the benefits of type checking and should be avoided.</span></span>

<span data-ttu-id="c28d5-227">In genere, tutte le proprietà indicate nella vista dei metadati sono necessarie ed eventuali esportazioni che non le forniscono non saranno considerate come corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="c28d5-227">Ordinarily, all of the properties named in the metadata view are required, and any exports that do not provide them will not be considered a match.</span></span> <span data-ttu-id="c28d5-228">L'attributo `DefaultValue` specifica che una proprietà è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="c28d5-228">The `DefaultValue` attribute specifies that a property is optional.</span></span> <span data-ttu-id="c28d5-229">Se non è inclusa, alla proprietà sarà assegnato il valore predefinito specificato come parametro di `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-229">If the property is not included, it will be assigned the default value specified as a parameter of `DefaultValue`.</span></span> <span data-ttu-id="c28d5-230">Di seguito sono riportate due classi diverse decorate con metadati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-230">The following are two different classes decorated with metadata.</span></span> <span data-ttu-id="c28d5-231">Entrambe le classi corrisponderebbero alla vista dei metadati precedente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-231">Both of these classes would match the previous metadata view.</span></span>

```vb
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class MyLogger
    Implements IPlugin

End Class

'Version is not required because of the DefaultValue
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Disk Writer")>
Public Class DWriter
    Implements IPlugin

End Class
```

```csharp
[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
}

[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Disk Writer")]
    //Version is not required because of the DefaultValue
public class DWriter : IPlugin
{
}
```

<span data-ttu-id="c28d5-232">I metadati sono espressi dopo l'attributo `Export` tramite l'attributo `ExportMetadata` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-232">Metadata is expressed after the `Export` attribute by using the `ExportMetadata` attribute.</span></span> <span data-ttu-id="c28d5-233">Ogni elemento di metadati è costituito da una coppia nome/valore.</span><span class="sxs-lookup"><span data-stu-id="c28d5-233">Each piece of metadata is composed of a name/value pair.</span></span> <span data-ttu-id="c28d5-234">La parte relativa al nome dei metadati deve corrispondere al nome della proprietà appropriata nella vista dei metadati e il valore sarà assegnato a tale proprietà.</span><span class="sxs-lookup"><span data-stu-id="c28d5-234">The name portion of the metadata must match the name of the appropriate property in the metadata view, and the value will be assigned to that property.</span></span>

<span data-ttu-id="c28d5-235">L'utilità di importazione specifica l'eventuale vista dei metadati che sarà usata.</span><span class="sxs-lookup"><span data-stu-id="c28d5-235">It is the importer that specifies what metadata view, if any, will be in use.</span></span> <span data-ttu-id="c28d5-236">Un'importazione con metadati è dichiarata come importazione differita, con l'interfaccia dei metadati come parametro di secondo tipo per `Lazy<T,T>`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-236">An import with metadata is declared as a lazy import, with the metadata interface as the second type parameter to `Lazy<T,T>`.</span></span> <span data-ttu-id="c28d5-237">La classe seguente importa la parte precedente con i metadati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-237">The following class imports the previous part with metadata.</span></span>

```vb
Public Class Addin

    <Import()>
    Public Property plugin As Lazy(Of IPlugin, IPluginMetadata)
End Class
```

```csharp
public class Addin
{
    [Import]
    public Lazy<IPlugin, IPluginMetadata> plugin;
}
```

<span data-ttu-id="c28d5-238">In molti casi è consigliabile combinare i metadati con l'attributo `ImportMany` , in modo da analizzare le importazioni disponibili e scegliere e creare istanze di una sola importazione oppure per filtrare una raccolta in modo che corrisponda a una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-238">In many cases, you will want to combine metadata with the `ImportMany` attribute, in order to parse through the available imports and choose and instantiate only one, or filter a collection to match a certain condition.</span></span> <span data-ttu-id="c28d5-239">La classe seguente crea istanze dei soli oggetti `IPlugin` con valore `Name` impostato su "Logger".</span><span class="sxs-lookup"><span data-stu-id="c28d5-239">The following class instantiates only `IPlugin` objects that have the `Name` value "Logger".</span></span>

```vb
Public Class User

    <ImportMany()>
    Public Property plugins As IEnumerable(Of Lazy(Of IPlugin, IPluginMetadata))

    Public Function InstantiateLogger() As IPlugin

        Dim logger As IPlugin
        logger = Nothing

        For Each Plugin As Lazy(Of IPlugin, IPluginMetadata) In plugins
            If Plugin.Metadata.Name = "Logger" Then
                logger = Plugin.Value
            End If
        Next
        Return logger
    End Function

End Class
```

```csharp
public class User
{
    [ImportMany]
    public IEnumerable<Lazy<IPlugin, IPluginMetadata>> plugins;

    public IPlugin InstantiateLogger()
    {
        IPlugin logger = null;

        foreach (Lazy<IPlugin, IPluginMetadata> plugin in plugins)
        {
            if (plugin.Metadata.Name == "Logger")
                logger = plugin.Value;
        }
        return logger;
    }
}
```

<a name="import_and_export_inheritance"></a>

## <a name="import-and-export-inheritance"></a><span data-ttu-id="c28d5-240">Eredità di importazione ed esportazione</span><span class="sxs-lookup"><span data-stu-id="c28d5-240">Import and Export Inheritance</span></span>

<span data-ttu-id="c28d5-241">Se una classe eredita da una parte, anche tale classe può diventare una parte.</span><span class="sxs-lookup"><span data-stu-id="c28d5-241">If a class inherits from a part, that class may also become a part.</span></span> <span data-ttu-id="c28d5-242">Le importazioni sono sempre ereditate dalle sottoclassi.</span><span class="sxs-lookup"><span data-stu-id="c28d5-242">Imports are always inherited by subclasses.</span></span> <span data-ttu-id="c28d5-243">Una sottoclasse di una parte, quindi, sarà sempre una parte, con le stesse importazioni come classe padre.</span><span class="sxs-lookup"><span data-stu-id="c28d5-243">Therefore, a subclass of a part will always be a part, with the same imports as its parent class.</span></span>

<span data-ttu-id="c28d5-244">Le esportazioni dichiarate usando l'attributo `Export` non sono ereditate dalle sottoclassi.</span><span class="sxs-lookup"><span data-stu-id="c28d5-244">Exports declared by using the `Export` attribute are not inherited by subclasses.</span></span> <span data-ttu-id="c28d5-245">Una parte, tuttavia, può esportare se stessa usando l'attributo `InheritedExport` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-245">However, a part can export itself by using the `InheritedExport` attribute.</span></span> <span data-ttu-id="c28d5-246">Le sottoclassi della parte erediteranno e forniranno la stessa esportazione, inclusi nome e tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="c28d5-246">Subclasses of the part will inherit and provide the same export, including contract name and contract type.</span></span> <span data-ttu-id="c28d5-247">A differenza di un attributo `Export` , `InheritedExport` può essere applicato solo a livello di classe, non a livello di membro.</span><span class="sxs-lookup"><span data-stu-id="c28d5-247">Unlike an `Export` attribute, `InheritedExport` can be applied only at the class level, and not at the member level.</span></span> <span data-ttu-id="c28d5-248">Le esportazioni a livello di membri non possono quindi essere mai ereditate.</span><span class="sxs-lookup"><span data-stu-id="c28d5-248">Therefore, member-level exports can never be inherited.</span></span>

<span data-ttu-id="c28d5-249">Le quattro classi seguenti illustrano i principi dell'ereditarietà di importazione ed esportazione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-249">The following four classes demonstrate the principles of import and export inheritance.</span></span> <span data-ttu-id="c28d5-250">`NumTwo` eredita da `NumOne`, quindi `NumTwo` importerà `IMyData`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-250">`NumTwo` inherits from `NumOne`, so `NumTwo` will import `IMyData`.</span></span> <span data-ttu-id="c28d5-251">Le esportazioni normali non sono ereditate, quindi `NumTwo` non esporterà nulla.</span><span class="sxs-lookup"><span data-stu-id="c28d5-251">Ordinary exports are not inherited, so `NumTwo` will not export anything.</span></span> <span data-ttu-id="c28d5-252">`NumFour` eredita da `NumThree`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-252">`NumFour` inherits from `NumThree`.</span></span> <span data-ttu-id="c28d5-253">Poiché `NumThree` ha usato `InheritedExport`, `NumFour` ha un'esportazione con tipo di contratto `NumThree`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-253">Because `NumThree` used `InheritedExport`, `NumFour` has one export with contract type `NumThree`.</span></span> <span data-ttu-id="c28d5-254">Le esportazioni a livello di membri non sono mai ereditate, quindi `IMyData` non viene esportato.</span><span class="sxs-lookup"><span data-stu-id="c28d5-254">Member-level exports are never inherited, so `IMyData` is not exported.</span></span>

```vb
<Export()>
Public Class NumOne
    <Import()>
    Public Property MyData As IMyData
End Class

Public Class NumTwo
    Inherits NumOne

    'Imports are always inherited, so NumTwo will
    'Import IMyData

    'Ordinary exports are not inherited, so
    'NumTwo will NOT export anything.  As a result it
    'will not be discovered by the catalog!

End Class

<InheritedExport()>
Public Class NumThree

    <Export()>
    Public Property MyData As IMyData

    'This part provides two exports, one of
    'contract type NumThree, and one of
    'contract type IMyData.

End Class

Public Class NumFour
    Inherits NumThree

    'Because NumThree used InheritedExport,
    'this part has one export with contract
    'type NumThree.

    'Member-level exports are never inherited,
    'so IMyData is not exported.

End Class
```

```csharp
[Export]
public class NumOne
{
    [Import]
    public IMyData MyData { get; set; }
}

public class NumTwo : NumOne
{
    //Imports are always inherited, so NumTwo will
    //import IMyData.

    //Ordinary exports are not inherited, so
    //NumTwo will NOT export anything. As a result it
    //will not be discovered by the catalog!
}

[InheritedExport]
public class NumThree
{
    [Export]
    Public IMyData MyData { get; set; }

    //This part provides two exports, one of
    //contract type NumThree, and one of
    //contract type IMyData.
}

public class NumFour : NumThree
{
    //Because NumThree used InheritedExport,
    //this part has one export with contract
    //type NumThree.

    //Member-level exports are never inherited,
    //so IMyData is not exported.
}
```

<span data-ttu-id="c28d5-255">Se a un attributo `InheritedExport` sono associati metadati, anche i metadati saranno ereditati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-255">If there is metadata associated with an `InheritedExport` attribute, that metadata will also be inherited.</span></span> <span data-ttu-id="c28d5-256">Per ulteriori informazioni, vedere la sezione precedente "viste metadati e metadati". I metadati ereditati non possono essere modificati dalla sottoclasse.</span><span class="sxs-lookup"><span data-stu-id="c28d5-256">(For more information, see the earlier "Metadata and Metadata Views" section.) Inherited metadata cannot be modified by the subclass.</span></span> <span data-ttu-id="c28d5-257">Dichiarando di nuovo l'attributo `InheritedExport` con lo stesso nome e tipo di contratto ma con nuovi metadati, tuttavia, la sottoclasse potrà sostituire i metadati ereditati con nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-257">However, by re-declaring the `InheritedExport` attribute with the same contract name and contract type, but with new metadata, the subclass can replace the inherited metadata with new metadata.</span></span> <span data-ttu-id="c28d5-258">La classe seguente illustra questo principio.</span><span class="sxs-lookup"><span data-stu-id="c28d5-258">The following class demonstrates this principle.</span></span> <span data-ttu-id="c28d5-259">La parte `MegaLogger` eredita da `Logger` e include l'attributo `InheritedExport` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-259">The `MegaLogger` part inherits from `Logger` and includes the `InheritedExport` attribute.</span></span> <span data-ttu-id="c28d5-260">Poiché `MegaLogger` ripete la dichiarazione di nuovi metadati con nome Status, non erediterà i metadati Name e Version da `Logger`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-260">Since `MegaLogger` re-declares new metadata named Status, it does not inherit the Name and Version metadata from `Logger`.</span></span>

```vb
<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class Logger
    Implements IPlugin

    'Exports with contract type IPlugin
    'and metadata "Name" and "Version".
End Class

Public Class SuperLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Name" and "Version", exactly the same
    'as the Logger class.

End Class

<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Status", "Green")>
Public Class MegaLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Status" only. Re-declaring
    'the attribute replaces all metadata.

End Class
```

```csharp
[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version".
}

public class SuperLogger : Logger
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version", exactly the same
    //as the Logger class.
}

[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Status", "Green")]
public class MegaLogger : Logger        {
    //Exports with contract type IPlugin and
    //metadata "Status" only. Re-declaring
    //the attribute replaces all metadata.
}
```

<span data-ttu-id="c28d5-261">Quando si dichiara di nuovo l'attributo `InheritedExport` per eseguire l'override dei metadati, occorre assicurarsi che i tipi di contratto siano uguali.</span><span class="sxs-lookup"><span data-stu-id="c28d5-261">When re-declaring the `InheritedExport` attribute to override metadata, make sure that the contract types are the same.</span></span> <span data-ttu-id="c28d5-262">Nell'esempio precedente `IPlugin` è il tipo di contratto. Se sono diversi, anziché eseguire l'override di, il secondo attributo creerà una seconda esportazione indipendente dalla parte.</span><span class="sxs-lookup"><span data-stu-id="c28d5-262">(In the previous example, `IPlugin` is the contract type.) If they differ, instead of overriding, the second attribute will create a second, independent export from the part.</span></span> <span data-ttu-id="c28d5-263">In genere, ciò significa che sarà necessario specificare in modo esplicito il tipo di contratto quando si esegue l'override di un attributo `InheritedExport` , come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-263">Generally, this means that you will have to explicitly specify the contract type when you override an `InheritedExport` attribute, as shown in the previous example.</span></span>

<span data-ttu-id="c28d5-264">Poiché non è possibile creare direttamente istanze delle interfacce, non è in genere possibile decorarle con attributi `Export` o `Import` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-264">Since interfaces cannot be instantiated directly, they generally cannot be decorated with `Export` or `Import` attributes.</span></span> <span data-ttu-id="c28d5-265">Un'interfaccia può essere tuttavia decorata con l'attributo `InheritedExport` a livello di interfaccia e tale esportazione, insieme a eventuali metadati associati, sarà ereditata da qualsiasi classe che esegue l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-265">However, an interface can be decorated with an `InheritedExport` attribute at the interface level, and that export along with any associated metadata will be inherited by any implementing classes.</span></span> <span data-ttu-id="c28d5-266">L'interfaccia stessa, tuttavia, non sarà disponibile come parte.</span><span class="sxs-lookup"><span data-stu-id="c28d5-266">The interface itself will not be available as a part, however.</span></span>

<a name="custom_export_attributes"></a>

## <a name="custom-export-attributes"></a><span data-ttu-id="c28d5-267">Attributi di esportazione personalizzati</span><span class="sxs-lookup"><span data-stu-id="c28d5-267">Custom Export Attributes</span></span>

<span data-ttu-id="c28d5-268">Gli attributi di esportazione di base, `Export` e `InheritedExport`, possono essere estesi in modo da includere metadati come proprietà degli attributi.</span><span class="sxs-lookup"><span data-stu-id="c28d5-268">The basic export attributes, `Export` and `InheritedExport`, can be extended to include metadata as attribute properties.</span></span> <span data-ttu-id="c28d5-269">Questa tecnica è utile per l'applicazione di metadati simili a molte parti oppure per creare un albero di eredità di attributi di metadati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-269">This technique is useful for applying similar metadata to many parts, or creating an inheritance tree of metadata attributes.</span></span>

<span data-ttu-id="c28d5-270">Un attributo personalizzato può specificare il tipo di contratto, il nome del contratto o altri metadati.</span><span class="sxs-lookup"><span data-stu-id="c28d5-270">A custom attribute can specify the contract type, the contract name, or any other metadata.</span></span> <span data-ttu-id="c28d5-271">Per definire un attributo personalizzato, una classe che eredita da `ExportAttribute` (o `InheritedExportAttribute`) deve essere decorata con l'attributo `MetadataAttribute` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-271">In order to define a custom attribute, a class inheriting from `ExportAttribute` (or `InheritedExportAttribute`) must be decorated with the `MetadataAttribute` attribute.</span></span> <span data-ttu-id="c28d5-272">La classe seguente definisce un attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c28d5-272">The following class defines a custom attribute.</span></span>

```vb
<MetadataAttribute()>
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=false)>
Public Class MyAttribute
    Inherits ExportAttribute

    Public Property MyMetadata As String

    Public Sub New(ByVal myMetadata As String)
        MyBase.New(GetType(IMyAddin))

        myMetadata = myMetadata
    End Sub

End Class
```

```csharp
[MetadataAttribute]
[AttributeUsage(AttributeTargets.Class, AllowMultiple=false)]
public class MyAttribute : ExportAttribute
{
    public MyAttribute(string myMetadata)
        : base(typeof(IMyAddin))
    {
        MyMetadata = myMetadata;
    }

    public string MyMetadata { get; private set; }
}
```

<span data-ttu-id="c28d5-273">Questa classe definisce un attributo personalizzato denominato `MyAttribute` con tipo di contratto `IMyAddin` e alcuni metadati con nome `MyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-273">This class defines a custom attribute named `MyAttribute` with contract type `IMyAddin` and some metadata named `MyMetadata`.</span></span> <span data-ttu-id="c28d5-274">Tutte le proprietà in una classe contrassegnata con l'attributo `MetadataAttribute` sono considerate come metadati definiti nell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c28d5-274">All properties in a class marked with the `MetadataAttribute` attribute are considered to be metadata defined in the custom attribute.</span></span> <span data-ttu-id="c28d5-275">Le due dichiarazioni seguenti sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="c28d5-275">The following two declarations are equivalent.</span></span>

```vb
<Export(GetType(IMyAddin))>
<ExportMetadata("MyMetadata", "theData")>
Public Property myAddin As MyAddin
```

```vb
<MyAttribute("theData")>
Public Property myAddin As MyAddin
```

```csharp
[Export(typeof(IMyAddin)),
    ExportMetadata("MyMetadata", "theData")]
public MyAddin myAddin { get; set; }
```

```csharp
[MyAttribute("theData")]
public MyAddin myAddin { get; set; }
```

<span data-ttu-id="c28d5-276">Nella prima dichiarazione il tipo di contratto e i metadati sono definiti in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="c28d5-276">In the first declaration, the contract type and metadata are explicitly defined.</span></span> <span data-ttu-id="c28d5-277">Nella seconda dichiarazione il tipo di contratto e i metadati sono impliciti nell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c28d5-277">In the second declaration, the contract type and metadata are implicit in the customized attribute.</span></span> <span data-ttu-id="c28d5-278">In particolare nei casi in cui è necessario applicare una quantità elevata di metadati identici a molte parti, ad esempio informazioni su autore o copyright, l'uso di un attributo personalizzato può permettere un notevole risparmio di tempo e di duplicazione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-278">Particularly in cases where a large amount of identical metadata must be applied to many parts (for example, author or copyright information), using a custom attribute can save a lot of time and duplication.</span></span> <span data-ttu-id="c28d5-279">Gli alberi di eredità degli attributi personalizzati, inoltre, possono essere creati in modo da permettere variazioni.</span><span class="sxs-lookup"><span data-stu-id="c28d5-279">Further, inheritance trees of custom attributes can be created to allow for variations.</span></span>

<span data-ttu-id="c28d5-280">Per creare metadati facoltativi in un attributo personalizzato, è possibile usare l'attributo `DefaultValue` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-280">To create optional metadata in a custom attribute, you can use the `DefaultValue` attribute.</span></span> <span data-ttu-id="c28d5-281">Quando questo attributo è applicato a una proprietà in una classe di attributi personalizzata, specifica che la proprietà decorata è facoltativa e non deve essere fornita da un'utilità di esportazione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-281">When this attribute is applied to a property in a custom attribute class, it specifies that the decorated property is optional and does not have to be supplied by an exporter.</span></span> <span data-ttu-id="c28d5-282">Se un valore per la proprietà non è stato fornito, sarà assegnato il valore predefinito per questo tipo di proprietà, in genere `null`, `false`o 0.</span><span class="sxs-lookup"><span data-stu-id="c28d5-282">If a value for the property is not supplied, it will be assigned the default value for its property type (usually `null`, `false`, or 0.)</span></span>

<a name="creation_policies"></a>

## <a name="creation-policies"></a><span data-ttu-id="c28d5-283">Criteri di creazione</span><span class="sxs-lookup"><span data-stu-id="c28d5-283">Creation Policies</span></span>

<span data-ttu-id="c28d5-284">Quando una parte specifica un'importazione e si esegue una composizione, il contenitore di composizione tenta di trovare un'esportazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-284">When a part specifies an import and composition is performed, the composition container attempts to find a matching export.</span></span> <span data-ttu-id="c28d5-285">In caso di corretta corrispondenza tra importazione ed esportazione, il membro che esegue l'importazione è impostato su un'istanza dell'oggetto esportato.</span><span class="sxs-lookup"><span data-stu-id="c28d5-285">If it matches the import with an export successfully, the importing member is set to an instance of the exported object.</span></span> <span data-ttu-id="c28d5-286">La provenienza di questa istanza è controllata dai *criteri di creazione*della parte che esegue l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-286">Where this instance comes from is controlled by the exporting part's *creation policy*.</span></span>

<span data-ttu-id="c28d5-287">I due criteri di creazione consentiti sono *condivisi* e *non condivisi*.</span><span class="sxs-lookup"><span data-stu-id="c28d5-287">The two possible creation policies are *shared* and *non-shared*.</span></span> <span data-ttu-id="c28d5-288">Una parte con criteri di creazione condivisi sarà condivisa tra tutte le importazioni nel contenuto per una parte con tale contratto.</span><span class="sxs-lookup"><span data-stu-id="c28d5-288">A part with a creation policy of shared will be shared between every import in the container for a part with that contract.</span></span> <span data-ttu-id="c28d5-289">Quando il motore della composizione rileva una corrispondenza e deve impostare una proprietà che esegue l'importazione, crea un'istanza di una nuova copia della parte solo se non esiste già. In caso contrario, fornisce la copia esistente.</span><span class="sxs-lookup"><span data-stu-id="c28d5-289">When the composition engine finds a match and has to set an importing property, it will instantiate a new copy of the part only if one does not already exist; otherwise, it will supply the existing copy.</span></span> <span data-ttu-id="c28d5-290">Ciò significa che molti oggetti potrebbero includere riferimenti alla stessa parte.</span><span class="sxs-lookup"><span data-stu-id="c28d5-290">This means that many objects may have references to the same part.</span></span> <span data-ttu-id="c28d5-291">È quindi consigliabile che queste parti non si basino su uno stato interno che potrebbe subire modifiche da molte posizioni.</span><span class="sxs-lookup"><span data-stu-id="c28d5-291">Such parts should not rely on internal state that might be changed from many places.</span></span> <span data-ttu-id="c28d5-292">Questi criteri sono appropriati per parti statiche, parti che offrono servizi e parti che usano una quantità elevata di memoria o di risorse di altro tipo.</span><span class="sxs-lookup"><span data-stu-id="c28d5-292">This policy is appropriate for static parts, parts that provide services, and parts that consume a lot of memory or other resources.</span></span>

<span data-ttu-id="c28d5-293">Una parte con criteri di creazione non condivisi sarà creata ogni volta che è rilevata un'importazione corrispondente per una delle esportazioni della parte.</span><span class="sxs-lookup"><span data-stu-id="c28d5-293">A part with the creation policy of non-shared will be created every time a matching import for one of its exports is found.</span></span> <span data-ttu-id="c28d5-294">Sarà quindi creata un'istanza della nuova copia per ogni importazione nel contenitore corrispondente a uno dei contratti esportati della parte.</span><span class="sxs-lookup"><span data-stu-id="c28d5-294">A new copy will therefore be instantiated for every import in the container that matches one of the part's exported contracts.</span></span> <span data-ttu-id="c28d5-295">Lo stato interno di queste copie non sarà condiviso.</span><span class="sxs-lookup"><span data-stu-id="c28d5-295">The internal state of these copies will not be shared.</span></span> <span data-ttu-id="c28d5-296">Questi criteri sono appropriati per parti in cui ogni importazione necessita del proprio stato interno.</span><span class="sxs-lookup"><span data-stu-id="c28d5-296">This policy is appropriate for parts where each import requires its own internal state.</span></span>

<span data-ttu-id="c28d5-297">Sia l'importazione che l'esportazione possono specificare i criteri di creazione di una parte, scegliendo tra i valori `Shared`, `NonShared`o `Any`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-297">Both the import and the export can specify the creation policy of a part, from among the values `Shared`, `NonShared`, or `Any`.</span></span> <span data-ttu-id="c28d5-298">Il valore predefinito è `Any` sia per le importazioni che per le esportazioni.</span><span class="sxs-lookup"><span data-stu-id="c28d5-298">The default is `Any` for both imports and exports.</span></span> <span data-ttu-id="c28d5-299">Un'esportazione che specifica `Shared` o `NonShared` corrisponderà solo a un'importazione che specifica lo stesso valore o che specifica `Any`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-299">An export that specifies `Shared` or `NonShared` will only match an import that specifies the same, or that specifies `Any`.</span></span> <span data-ttu-id="c28d5-300">Analogamente, un'importazione che specifica `Shared` o `NonShared` corrisponderà solo a un'esportazione che specifica lo stesso valore o che specifica `Any`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-300">Similarly, an import that specifies `Shared` or `NonShared` will only match an export that specifies the same, or that specifies `Any`.</span></span> <span data-ttu-id="c28d5-301">Le importazioni e le esportazioni con criteri di creazione non compatibili non saranno considerate come corrispondenti, esattamente come non lo sono un'importazione e un'esportazione con tipo o nome di contratto non corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c28d5-301">Imports and exports with incompatible creation policies are not considered a match, in the same way as an import and export whose contract name or contract type are not a match.</span></span> <span data-ttu-id="c28d5-302">Se sia l'importazione che l'esportazione specificano `Any`o non specificano alcun criterio di creazione e usano il valore predefinito `Any`, i criteri di creazione saranno condivisi per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c28d5-302">If both import and export specify `Any`, or do not specify a creation policy and default to `Any`, the creation policy will default to shared.</span></span>

<span data-ttu-id="c28d5-303">L'esempio seguente mostra sia le importazioni che le esportazioni che specificano criteri di creazione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-303">The following example shows both imports and exports specifying creation policies.</span></span> <span data-ttu-id="c28d5-304">`PartOne` non specifica alcun criterio di creazione, quindi l'impostazione predefinita è `Any`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-304">`PartOne` does not specify a creation policy, so the default is `Any`.</span></span> <span data-ttu-id="c28d5-305">`PartTwo` non specifica alcun criterio di creazione, quindi l'impostazione predefinita è `Any`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-305">`PartTwo` does not specify a creation policy, so the default is `Any`.</span></span> <span data-ttu-id="c28d5-306">Poiché sia per l'importazione che per l'esportazione sarà usato il valore predefinito `Any`, `PartOne` sarà condivisa.</span><span class="sxs-lookup"><span data-stu-id="c28d5-306">Since both import and export default to `Any`, `PartOne` will be shared.</span></span> <span data-ttu-id="c28d5-307">`PartThree` specifica un criterio di creazione `Shared` , quindi `PartTwo` e `PartThree` condivideranno la stessa copia di `PartOne`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-307">`PartThree` specifies a `Shared` creation policy, so `PartTwo` and `PartThree` will share the same copy of `PartOne`.</span></span> <span data-ttu-id="c28d5-308">`PartFour` specifica un criterio di creazione `NonShared` , quindi `PartFour` non saranno condivisi in `PartFive`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-308">`PartFour` specifies a `NonShared` creation policy, so `PartFour` will be non-shared in `PartFive`.</span></span> <span data-ttu-id="c28d5-309">`PartSix` specifica un criterio di creazione `NonShared` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-309">`PartSix` specifies a `NonShared` creation policy.</span></span> <span data-ttu-id="c28d5-310">`PartFive` e `PartSix` riceveranno copie distinte di `PartFour`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-310">`PartFive` and `PartSix` will each receive separate copies of `PartFour`.</span></span> <span data-ttu-id="c28d5-311">`PartSeven` specifica un criterio di creazione `Shared` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-311">`PartSeven` specifies a `Shared` creation policy.</span></span> <span data-ttu-id="c28d5-312">Poiché non è disponibile alcuna `PartFour` esportata con un criterio di creazione `Shared`, l'importazione `PartSeven` non corrisponde a nessun elemento e non sarà completata.</span><span class="sxs-lookup"><span data-stu-id="c28d5-312">Because there is no exported `PartFour` with a creation policy of `Shared`, the `PartSeven` import does not match anything and will not be filled.</span></span>

```vb
<Export()>
Public Class PartOne
    'The default creation policy for an export is Any.
End Class

Public Class PartTwo

    <Import()>
    Public Property partOne As PartOne

    'The default creation policy for an import is Any.
    'If both policies are Any, the part will be shared.

End Class

Public Class PartThree

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partOne As PartOne

    'The Shared creation policy is explicitly specified.
    'PartTwo and PartThree will receive references to the
    'SAME copy of PartOne.

End Class

<Export()>
<PartCreationPolicy(CreationPolicy.NonShared)>
Public Class PartFour
    'The NonShared creation policy is explicitly specified.
End Class

Public Class PartFive

    <Import()>
    Public Property partFour As PartFour

    'The default creation policy for an import is Any.
    'Since the export's creation policy was explicitly
    'defined, the creation policy for this property will
    'be non-shared.

End Class

Public Class PartSix

    <Import(RequiredCreationPolicy:=CreationPolicy.NonShared)>
    Public Property partFour As PartFour

    'Both import and export specify matching creation
    'policies.  PartFive and PartSix will each receive
    'SEPARATE copies of PartFour, each with its own
    'internal state.

End Class

Public Class PartSeven

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partFour As PartFour

    'A creation policy mismatch.  Because there is no
    'exported PartFour with a creation policy of Shared,
    'this import does not match anything and will not be
    'filled.

End Class
```

```csharp
[Export]
public class PartOne
{
    //The default creation policy for an export is Any.
}

public class PartTwo
{
    [Import]
    public PartOne partOne { get; set; }

    //The default creation policy for an import is Any.
    //If both policies are Any, the part will be shared.
}

public class PartThree
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartOne partOne { get; set; }

    //The Shared creation policy is explicitly specified.
    //PartTwo and PartThree will receive references to the
    //SAME copy of PartOne.
}

[Export]
[PartCreationPolicy(CreationPolicy.NonShared)]
public class PartFour
{
    //The NonShared creation policy is explicitly specified.
}

public class PartFive
{
    [Import]
    public PartFour partFour { get; set; }

    //The default creation policy for an import is Any.
    //Since the export's creation policy was explicitly
    //defined, the creation policy for this property will
    //be non-shared.
}

public class PartSix
{
    [Import(RequiredCreationPolicy = CreationPolicy.NonShared)]
    public PartFour partFour { get; set; }

    //Both import and export specify matching creation
    //policies.  PartFive and PartSix will each receive
    //SEPARATE copies of PartFour, each with its own
    //internal state.
}

public class PartSeven
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartFour partFour { get; set; }

    //A creation policy mismatch.  Because there is no
    //exported PartFour with a creation policy of Shared,
    //this import does not match anything and will not be
    //filled.
}
```

<a name="life_cycle_and_disposing"></a>

## <a name="life-cycle-and-disposing"></a><span data-ttu-id="c28d5-313">Ciclo di vita ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="c28d5-313">Life Cycle and Disposing</span></span>

<span data-ttu-id="c28d5-314">Poiché le parti sono ospitate nel contenitore di composizione, il relativo ciclo di vita può essere più complesso rispetto a quello degli oggetti normali.</span><span class="sxs-lookup"><span data-stu-id="c28d5-314">Because parts are hosted in the composition container, their life cycle can be more complex than ordinary objects.</span></span> <span data-ttu-id="c28d5-315">Le parti possono implementare due interfacce importanti correlate al ciclo di vita, ovvero `IDisposable` e `IPartImportsSatisfiedNotification`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-315">Parts can implement two important life cycle-related interfaces: `IDisposable` and `IPartImportsSatisfiedNotification`.</span></span>

<span data-ttu-id="c28d5-316">Le parti che necessitano dell'esecuzione di operazioni in fase di arresto o del rilascio di risorse devono implementare `IDisposable`, come di consueto per oggetti .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c28d5-316">Parts that require work to be performed at shut down or that need to release resources should implement `IDisposable`, as usual for .NET Framework objects.</span></span> <span data-ttu-id="c28d5-317">Poiché tuttavia il contenitore crea e gestisce riferimenti alle parti, solo il contenitore proprietario di una parte dovrebbe chiamare il metodo `Dispose` per tale parte.</span><span class="sxs-lookup"><span data-stu-id="c28d5-317">However, since the container creates and maintains references to parts, only the container that owns a part should call the `Dispose` method on it.</span></span> <span data-ttu-id="c28d5-318">Il contenitore stesso implementa `IDisposable`e come parte della pulizia in `Dispose` chiamerà `Dispose` per tutte le parti di sua proprietà.</span><span class="sxs-lookup"><span data-stu-id="c28d5-318">The container itself implements `IDisposable`, and as portion of its cleanup in `Dispose` it will call `Dispose` on all the parts that it owns.</span></span> <span data-ttu-id="c28d5-319">Per questo motivo, è sempre consigliabile eliminare il contenitore di composizione quando il contenitore ed eventuali parti di sua proprietà non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="c28d5-319">For this reason, you should always dispose the composition container when it and any parts it owns are no longer needed.</span></span>

<span data-ttu-id="c28d5-320">Per i contenitori di composizione di lunga durata, il consumo di memoria da parte delle parti con criteri di creazione non condivisi può rappresentare un problema.</span><span class="sxs-lookup"><span data-stu-id="c28d5-320">For long-lived composition containers, memory consumption by parts with a creation policy of non-shared can become a problem.</span></span> <span data-ttu-id="c28d5-321">Le parti non condivise possono essere create più volte e saranno eliminate solo quando si elimina il contenitore stesso.</span><span class="sxs-lookup"><span data-stu-id="c28d5-321">These non-shared parts can be created multiple times and will not be disposed until the container itself is disposed.</span></span> <span data-ttu-id="c28d5-322">Per risolvere questo problema, il contenitore fornisce il metodo `ReleaseExport` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-322">To deal with this, the container provides the `ReleaseExport` method.</span></span> <span data-ttu-id="c28d5-323">Se si chiama questo metodo in un'esportazione non condivisa, tale esportazione sarà rimossa dal contenitore di composizione e sarà eliminata.</span><span class="sxs-lookup"><span data-stu-id="c28d5-323">Calling this method on a non-shared export removes that export from the composition container and disposes it.</span></span> <span data-ttu-id="c28d5-324">Saranno rimosse ed eliminate anche le parti usate solo dall'esportazione rimossa e così via lungo l'albero.</span><span class="sxs-lookup"><span data-stu-id="c28d5-324">Parts that are used only by the removed export, and so on down the tree, are also removed and disposed.</span></span> <span data-ttu-id="c28d5-325">In questo modo sarà possibile recuperare le risorse senza eliminare il contenitore di composizione.</span><span class="sxs-lookup"><span data-stu-id="c28d5-325">In this way, resources can be reclaimed without disposing the composition container itself.</span></span>

<span data-ttu-id="c28d5-326">`IPartImportsSatisfiedNotification` include un metodo con nome `OnImportsSatisfied`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-326">`IPartImportsSatisfiedNotification` contains one method named `OnImportsSatisfied`.</span></span> <span data-ttu-id="c28d5-327">Questo metodo è chiamato dal contenitore di composizione per qualsiasi parte che implementa l'interfaccia quando la composizione è stata completata e le importazioni della parte sono pronte per l'uso.</span><span class="sxs-lookup"><span data-stu-id="c28d5-327">This method is called by the composition container on any parts that implement the interface when composition has been completed and the part's imports are ready for use.</span></span> <span data-ttu-id="c28d5-328">Le parti sono create dal motore di composizione per completare le importazioni di altre parti.</span><span class="sxs-lookup"><span data-stu-id="c28d5-328">Parts are created by the composition engine to fill the imports of other parts.</span></span> <span data-ttu-id="c28d5-329">Prima dell'impostazione delle importazioni di una parte, sarà possibile eseguire inizializzazioni che si basano su o che modificano valori importati nel costruttore della parte solo se tali valori sono stati specificati come prerequisiti usando l'attributo `ImportingConstructor` .</span><span class="sxs-lookup"><span data-stu-id="c28d5-329">Before the imports of a part have been set, you cannot perform any initialization that relies on or manipulates imported values in the part constructor unless those values have been specified as prerequisites by using the `ImportingConstructor` attribute.</span></span> <span data-ttu-id="c28d5-330">Questo è in genere il metodo preferito, ma in alcuni casi è possibile che l'aggiunta di costruttori non sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="c28d5-330">This is normally the preferred method, but in some cases, constructor injection may not be available.</span></span> <span data-ttu-id="c28d5-331">In questi casi l'inizializzazione può essere eseguita in `OnImportsSatisfied`e la parte deve implementare `IPartImportsSatisfiedNotification`.</span><span class="sxs-lookup"><span data-stu-id="c28d5-331">In those cases, initialization can be performed in `OnImportsSatisfied`, and the part should implement `IPartImportsSatisfiedNotification`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c28d5-332">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c28d5-332">See also</span></span>

- [<span data-ttu-id="c28d5-333">Video Channel 9: Aprire le applicazioni con Managed Extensibility Framework</span><span class="sxs-lookup"><span data-stu-id="c28d5-333">Channel 9 Video: Open Up Your Applications with the Managed Extensibility Framework</span></span>](https://channel9.msdn.com/events/TechEd/NorthAmerica/2009/DTL328)
- [<span data-ttu-id="c28d5-334">Video Channel 9: Managed Extensibility Framework (MEF) 2.0</span><span class="sxs-lookup"><span data-stu-id="c28d5-334">Channel 9 Video: Managed Extensibility Framework (MEF) 2.0</span></span>](https://channel9.msdn.com/posts/NET-45-Oleg-Lvovitch-and-Kevin-Ransom-Managed-Extensibility-Framework-MEF-20)
