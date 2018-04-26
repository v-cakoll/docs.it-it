---
title: Proprietà
description: Informazioni sulle proprietà di C#, tra cui funzionalità per la convalida, valori calcolati, valutazione lazy e notifiche di modifica di proprietà.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 04/03/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 6950d25a-bba1-4744-b7c7-a3cc90438c55
ms.openlocfilehash: 05e51d527dc3c05301fc85d7717c751dc46bf9fa
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="properties"></a><span data-ttu-id="dc531-104">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dc531-104">Properties</span></span>

<span data-ttu-id="dc531-105">Le proprietà sono elementi fondamentali in C#.</span><span class="sxs-lookup"><span data-stu-id="dc531-105">Properties are first class citizens in C#.</span></span> <span data-ttu-id="dc531-106">Il linguaggio definisce la sintassi che consente agli sviluppatori di scrivere codice che esprime in modo preciso la finalità della progettazione.</span><span class="sxs-lookup"><span data-stu-id="dc531-106">The language defines syntax that enables developers to write code that accurately expresses their design intent.</span></span>

<span data-ttu-id="dc531-107">Quando viene eseguito l'accesso, le proprietà si comportano come i campi.</span><span class="sxs-lookup"><span data-stu-id="dc531-107">Properties behave like fields when they are accessed.</span></span>
<span data-ttu-id="dc531-108">Tuttavia, a differenza dei campi, le proprietà vengono implementate con funzioni di accesso che definiscono le istruzioni eseguite al momento dell'accesso e dell'assegnazione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc531-108">However, unlike fields, properties are implemented with accessors that define the statements executed when a property is accessed or assigned.</span></span>

## <a name="property-syntax"></a><span data-ttu-id="dc531-109">Sintassi delle proprietà</span><span class="sxs-lookup"><span data-stu-id="dc531-109">Property Syntax</span></span>

<span data-ttu-id="dc531-110">La sintassi delle proprietà è un'estensione naturale dei campi.</span><span class="sxs-lookup"><span data-stu-id="dc531-110">The syntax for properties is a natural extension to fields.</span></span> <span data-ttu-id="dc531-111">Un campo definisce una posizione di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="dc531-111">A field defines a storage location:</span></span>

```csharp
public class Person
{
    public string FirstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="dc531-112">La definizione di una proprietà contiene le dichiarazioni di una funzione di accesso `get` e `set` che recupera e assegna il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="dc531-112">A property definition contains declarations for a `get` and `set` accessor that retrieves and assigns the value of that property:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="dc531-113">La sintassi illustrata sopra è la sintassi della *proprietà automatica*.</span><span class="sxs-lookup"><span data-stu-id="dc531-113">The syntax shown above is the *auto property* syntax.</span></span> <span data-ttu-id="dc531-114">Il compilatore genera la posizione di archiviazione per il campo che esegue il backup della proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc531-114">The compiler generates the storage location for the field that backs up the property.</span></span> <span data-ttu-id="dc531-115">Il compilatore implementa anche il corpo delle funzioni di accesso `get` e `set`.</span><span class="sxs-lookup"><span data-stu-id="dc531-115">The compiler also implements the body of the `get` and `set` accessors.</span></span>

<span data-ttu-id="dc531-116">In alcuni casi è necessario inizializzare una proprietà con un valore diverso da quello predefinito per il suo tipo.</span><span class="sxs-lookup"><span data-stu-id="dc531-116">Sometimes, you need to initialize a property to a value other than the default for its type.</span></span>  <span data-ttu-id="dc531-117">In C# questa operazione è possibile impostando un valore dopo la parentesi graffa chiusa della proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc531-117">C# enables that by setting a value after the closing brace for the property.</span></span> <span data-ttu-id="dc531-118">Per la proprietà `FirstName` è preferibile usare come valore iniziale una stringa vuota anziché `null`.</span><span class="sxs-lookup"><span data-stu-id="dc531-118">You may prefer the initial value for the `FirstName` property to be the empty string rather than `null`.</span></span> <span data-ttu-id="dc531-119">Ecco come eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="dc531-119">You would specify that as shown below:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; } = string.Empty;

    // remaining implementation removed from listing
}
```

<span data-ttu-id="dc531-120">Questo è particolarmente utile per le proprietà di sola lettura, come si vedrà più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dc531-120">This is most useful for read-only properties, as you'll see later in this topic.</span></span>

<span data-ttu-id="dc531-121">È anche possibile definire l'archiviazione manualmente, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dc531-121">You can also define the storage yourself, as shown below:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get { return firstName; }
        set { firstName = value; }
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="dc531-122">Se l'implementazione di una proprietà corrisponde a un'espressione singola, è possibile usare *membri con corpo di espressione* per il getter o il setter:</span><span class="sxs-lookup"><span data-stu-id="dc531-122">When a property implementation is a single expression, you can use *expression-bodied members* for the getter or setter:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get => firstName;
        set => firstName = value;
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="dc531-123">Questa sintassi semplificata verrà usata ovunque applicabile in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dc531-123">This simplified syntax will be used where applicable throughout this topic.</span></span>

<span data-ttu-id="dc531-124">La definizione della proprietà illustrata sopra è una proprietà di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="dc531-124">The property definition shown above is a read-write property.</span></span> <span data-ttu-id="dc531-125">Si noti la parola chiave `value` nella funzione di accesso impostata.</span><span class="sxs-lookup"><span data-stu-id="dc531-125">Notice the keyword `value` in the set accessor.</span></span> <span data-ttu-id="dc531-126">La funzione di accesso `set` ha sempre un singolo parametro denominato `value`.</span><span class="sxs-lookup"><span data-stu-id="dc531-126">The `set` accessor always has a single parameter named `value`.</span></span> <span data-ttu-id="dc531-127">La funzione di accesso `get` deve restituire un valore che è convertibile nel tipo della proprietà (in questo esempio `string`).</span><span class="sxs-lookup"><span data-stu-id="dc531-127">The `get` accessor must return a value that is convertible to the type of the property (`string` in this example).</span></span>
 
<span data-ttu-id="dc531-128">Queste sono le nozioni di basi sulla sintassi.</span><span class="sxs-lookup"><span data-stu-id="dc531-128">That's the basics of the syntax.</span></span> <span data-ttu-id="dc531-129">Esistono numerose varianti che supportano un'ampia gamma di termini di progettazione diversi.</span><span class="sxs-lookup"><span data-stu-id="dc531-129">There are many different variations that support a variety of different design idioms.</span></span> <span data-ttu-id="dc531-130">Di seguito sono descritti i termini e le opzioni di sintassi per ogni termine.</span><span class="sxs-lookup"><span data-stu-id="dc531-130">Let's explore those, and learn the syntax options for each.</span></span>

## <a name="scenarios"></a><span data-ttu-id="dc531-131">Scenari</span><span class="sxs-lookup"><span data-stu-id="dc531-131">Scenarios</span></span>

<span data-ttu-id="dc531-132">Gli esempi precedenti hanno illustrato uno dei casi più semplici di definizione delle proprietà, ovvero una proprietà di lettura/scrittura senza convalida.</span><span class="sxs-lookup"><span data-stu-id="dc531-132">The examples above showed one of the simplest cases of property definition: a read-write property with no validation.</span></span> <span data-ttu-id="dc531-133">Scrivendo il codice desiderato nelle funzioni di accesso `get` e `set` è possibile creare scenari diversi.</span><span class="sxs-lookup"><span data-stu-id="dc531-133">By writing the code you want in the `get` and `set` accessors, you can create many different scenarios.</span></span>

### <a name="validation"></a><span data-ttu-id="dc531-134">Convalida</span><span class="sxs-lookup"><span data-stu-id="dc531-134">Validation</span></span>

<span data-ttu-id="dc531-135">È possibile scrivere codice nella funzione di accesso `set` per assicurarsi che i valori rappresentati da una proprietà siano sempre validi.</span><span class="sxs-lookup"><span data-stu-id="dc531-135">You can write code in the `set` accessor to ensure that the values represented by a property are always valid.</span></span> <span data-ttu-id="dc531-136">Ad esempio, si supponga che una regola per la classe `Person` preveda che il nome non può essere vuoto o uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="dc531-136">For example, suppose one rule for the `Person` class is that the name cannot be blank or white space.</span></span> <span data-ttu-id="dc531-137">Sarà necessario scrivere:</span><span class="sxs-lookup"><span data-stu-id="dc531-137">You would write that as follows:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get => firstName;
        set
        {
            if (string.IsNullOrWhiteSpace(value))
                throw new ArgumentException("First name must not be blank");
            firstName = value;
        }
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="dc531-138">L'esempio precedente applica la regola che prevede che il nome non può essere vuoto o uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="dc531-138">The example above enforces the rule that the first name must not be blank or white space.</span></span> <span data-ttu-id="dc531-139">Se lo sviluppatore scrive</span><span class="sxs-lookup"><span data-stu-id="dc531-139">If a developer writes</span></span>

```csharp
hero.FirstName = "";
```

<span data-ttu-id="dc531-140">L'assegnazione genera `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="dc531-140">That assignment throws an `ArgumentException`.</span></span> <span data-ttu-id="dc531-141">Poiché la funzione di accesso di un insieme di proprietà deve avere un tipo restituito void, gli errori vengono segnalati nella funzione di accesso dell'insieme generando un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="dc531-141">Because a property set accessor must have a void return type, you report errors in the set accessor by throwing an exception.</span></span>

<span data-ttu-id="dc531-142">Questo è un caso semplice di convalida.</span><span class="sxs-lookup"><span data-stu-id="dc531-142">That is a simple case of validation.</span></span> <span data-ttu-id="dc531-143">La stessa sintassi può essere estesa a ogni elemento necessario nello scenario.</span><span class="sxs-lookup"><span data-stu-id="dc531-143">You can extend this same syntax to anything needed in your scenario.</span></span> <span data-ttu-id="dc531-144">È possibile controllare le relazioni tra le diverse proprietà o eseguire la convalida in base a qualsiasi condizione esterna.</span><span class="sxs-lookup"><span data-stu-id="dc531-144">You can check the relationships between different properties, or validate against any external conditions.</span></span> <span data-ttu-id="dc531-145">Tutte le istruzioni C# valide sono valide nella funzione di accesso di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc531-145">Any valid C# statements are valid in a property accessor.</span></span>

### <a name="read-only"></a><span data-ttu-id="dc531-146">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc531-146">Read-only</span></span>

<span data-ttu-id="dc531-147">Le definizioni di proprietà descritte fino a questo punto si riferiscono a proprietà di lettura/scrittura con funzioni di accesso pubbliche.</span><span class="sxs-lookup"><span data-stu-id="dc531-147">Up to this point, all the property definitions you have seen are read/write properties with public accessors.</span></span> <span data-ttu-id="dc531-148">Non si tratta tuttavia dell'unica accessibilità valida per le proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc531-148">That's not the only valid accessibility for properties.</span></span>
<span data-ttu-id="dc531-149">È possibile creare proprietà di sola lettura o assegnare un'accessibilità diversa alle funzioni di accesso set e get.</span><span class="sxs-lookup"><span data-stu-id="dc531-149">You can create read-only properties, or give different accessibility to the set and get accessors.</span></span> <span data-ttu-id="dc531-150">Si supponga che la classe `Person` debba consentire soltanto la modifica del valore della proprietà `FirstName` da altri metodi della classe.</span><span class="sxs-lookup"><span data-stu-id="dc531-150">Suppose that your `Person` class should only enable changing the value of the `FirstName` property from other methods in that class.</span></span> <span data-ttu-id="dc531-151">È possibile assegnare alla funzione di accesso set l'accessibilità `private` anziché `public`:</span><span class="sxs-lookup"><span data-stu-id="dc531-151">You could give the set accessor `private` accessibility instead of `public`:</span></span>

```csharp
public class Person
{
    public string FirstName { get; private set; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="dc531-152">L'accesso alla proprietà `FirstName` potrà quindi essere eseguito da qualsiasi codice, ma la proprietà potrà essere assegnata soltanto da altro codice della classe `Person`.</span><span class="sxs-lookup"><span data-stu-id="dc531-152">Now, the `FirstName` property can be accessed from any code, but it can only be assigned from other code in the `Person` class.</span></span>

<span data-ttu-id="dc531-153">È possibile aggiungere qualsiasi modificatore di accesso restrittivo alle funzioni di accesso set o get.</span><span class="sxs-lookup"><span data-stu-id="dc531-153">You can add any restrictive access modifier to either the set or get accessors.</span></span> <span data-ttu-id="dc531-154">Il modificatore di accesso inserito nella singola funzione di accesso deve essere più restrittivo del modificatore di accesso della definizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc531-154">Any access modifier you place on the individual accessor must be more limited than the access modifier on the property definition.</span></span> <span data-ttu-id="dc531-155">Il codice precedente è valido poiché la proprietà `FirstName` è `public` e la funzione di accesso set è `private`.</span><span class="sxs-lookup"><span data-stu-id="dc531-155">The above is legal because the `FirstName` property is `public`, but the set accessor is `private`.</span></span> <span data-ttu-id="dc531-156">Non è possibile dichiarare una proprietà `private` con una funzione di accesso `public`.</span><span class="sxs-lookup"><span data-stu-id="dc531-156">You could not declare a `private` property with a `public` accessor.</span></span> <span data-ttu-id="dc531-157">Le dichiarazioni di proprietà possono anche essere dichiarate `protected`, `internal`, `protected internal`, `private protected` o anche `private`.</span><span class="sxs-lookup"><span data-stu-id="dc531-157">Property declarations can also be declared `protected`, `internal`, `protected internal`, `private protected` or even `private`.</span></span>   

<span data-ttu-id="dc531-158">È anche consentito inserire il modificatore più restrittivo nella funzione di accesso `get`.</span><span class="sxs-lookup"><span data-stu-id="dc531-158">It is also legal to place the more restrictive modifier on the `get` accessor.</span></span> <span data-ttu-id="dc531-159">Ad esempio, è possibile avere una proprietà `public` e limitare la funzione di accesso `get` a `private`.</span><span class="sxs-lookup"><span data-stu-id="dc531-159">For example, you could have a `public` property, but restrict the `get` accessor to `private`.</span></span> <span data-ttu-id="dc531-160">Questo scenario viene usato raramente.</span><span class="sxs-lookup"><span data-stu-id="dc531-160">That scenario is rarely done in practice.</span></span>

<span data-ttu-id="dc531-161">È anche possibile limitare le modifiche a una proprietà, in modo che possa essere impostata solo in un costruttore o in un inizializzatore di proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc531-161">You can also restrict modifications to a property so that it can only be set in a constructor or a property initializer.</span></span> <span data-ttu-id="dc531-162">È possibile modificare in tal senso la classe `Person` come segue:</span><span class="sxs-lookup"><span data-stu-id="dc531-162">You can modify the `Person` class so as follows:</span></span>

```csharp
public class Person
{
    public Person(string firstName)
    {
        this.FirstName = firstName;
    }

    public string FirstName { get; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="dc531-163">Questa funzionalità viene in genere usata per l'inizializzazione delle raccolte esposte come proprietà di sola lettura:</span><span class="sxs-lookup"><span data-stu-id="dc531-163">This feature is most commonly used for initializing collections that are exposed as read-only properties:</span></span>

```csharp
public class Measurements
{
    public ICollection<DataPoint> points { get; } = new List<DataPoint>();
}
```

### <a name="computed-properties"></a><span data-ttu-id="dc531-164">Proprietà calcolate</span><span class="sxs-lookup"><span data-stu-id="dc531-164">Computed Properties</span></span>

<span data-ttu-id="dc531-165">Una proprietà non si limita a restituire il valore di un campo membro.</span><span class="sxs-lookup"><span data-stu-id="dc531-165">A property does not need to simply return the value of a member field.</span></span> <span data-ttu-id="dc531-166">È possibile creare proprietà che restituiscono un valore calcolato.</span><span class="sxs-lookup"><span data-stu-id="dc531-166">You can create properties that return a computed value.</span></span> <span data-ttu-id="dc531-167">Espandere l'oggetto `Person` per restituire il nome completo, calcolato concatenando il nome e il cognome:</span><span class="sxs-lookup"><span data-stu-id="dc531-167">Let's expand the `Person` object to return the full name, computed by concatenating the first and last names:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string FullName { get { return $"{FirstName} {LastName}"; } }
}
```

<span data-ttu-id="dc531-168">L'esempio precedente usa la funzionalità di [interpolazione delle stringhe](../csharp/language-reference/tokens/interpolated.md) per creare la stringa formattata per il nome completo.</span><span class="sxs-lookup"><span data-stu-id="dc531-168">The example above uses the [string interpolation](../csharp/language-reference/tokens/interpolated.md) feature to create the formatted string for the full name.</span></span>

<span data-ttu-id="dc531-169">È anche possibile usare *membri con corpo di espressione* che consentono di creare la proprietà calcolata `FullName` in modo più conciso:</span><span class="sxs-lookup"><span data-stu-id="dc531-169">You can also use *expression-bodied members*, which provides a more succinct way to create the computed `FullName` property:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string FullName =>  $"{FirstName} {LastName}";
}
```
 
<span data-ttu-id="dc531-170">I *membri con corpo di espressione* usano la sintassi delle *espressioni lambda* per definire un metodo che contiene una singola espressione.</span><span class="sxs-lookup"><span data-stu-id="dc531-170">*Expression-bodied members* use the *lambda expression* syntax to define a method that contain a single expression.</span></span> <span data-ttu-id="dc531-171">In questo caso, l'espressione restituisce il nome completo per l'oggetto person.</span><span class="sxs-lookup"><span data-stu-id="dc531-171">Here, that expression returns the full name for the person object.</span></span>

### <a name="lazy-evaluated-properties"></a><span data-ttu-id="dc531-172">Proprietà con valutazione lazy</span><span class="sxs-lookup"><span data-stu-id="dc531-172">Lazy Evaluated Properties</span></span>

<span data-ttu-id="dc531-173">È possibile unire il concetto di proprietà calcolata al concetto di archiviazione e creare una *proprietà con valutazione lazy*.</span><span class="sxs-lookup"><span data-stu-id="dc531-173">You can mix the concept of a computed property with storage and create a *lazy evaluated property*.</span></span>  <span data-ttu-id="dc531-174">Ad esempio, è possibile aggiornare la proprietà `FullName` in modo che venga eseguita soltanto la formattazione della stringa al primo accesso:</span><span class="sxs-lookup"><span data-stu-id="dc531-174">For example, you could update the `FullName` property so that the string formatting only happened the first time it was accessed:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    private string fullName;
    public string FullName
    {
        get
        {
            if (fullName == null)
                fullName = $"{FirstName} {LastName}";
            return fullName;
        }
    }
}
```

<span data-ttu-id="dc531-175">Il codice riportato sopra tuttavia contiene un bug.</span><span class="sxs-lookup"><span data-stu-id="dc531-175">The above code contains a bug though.</span></span> <span data-ttu-id="dc531-176">Se il codice aggiorna il valore della proprietà `FirstName` o `LastName`, il campo `fullName` valutato in precedenza non è valido.</span><span class="sxs-lookup"><span data-stu-id="dc531-176">If code updates the value of either the `FirstName` or `LastName` property, the previously evaluated `fullName` field is invalid.</span></span> <span data-ttu-id="dc531-177">È necessario aggiornare le funzioni di accesso `set` della proprietà `FirstName` e `LastName` in modo che il campo `fullName` venga calcolato nuovamente:</span><span class="sxs-lookup"><span data-stu-id="dc531-177">You need to update the `set` accessors of the `FirstName` and `LastName` property so that the `fullName` field is calculated again:</span></span>

```csharp
public class Person
{
    private string firstName;
    public string FirstName
    {
        get => firstName;
        set
        {
            firstName = value;
            fullName = null;
        }
    }

    private string lastName;
    public string LastName
    {
        get => lastName;
        set
        {
            lastName = value;
            fullName = null;
        }
    }

    private string fullName;
    public string FullName
    {
        get
        {
            if (fullName == null)
                fullName = $"{FirstName} {LastName}";
            return fullName;
        }
    }
}
```

<span data-ttu-id="dc531-178">La versione finale valuta la proprietà `FullName` solo quando necessario.</span><span class="sxs-lookup"><span data-stu-id="dc531-178">This final version evaluates the `FullName` property only when needed.</span></span>
<span data-ttu-id="dc531-179">Se è valida, viene usata la versione calcolata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dc531-179">If the previously calculated version is valid, it's used.</span></span> <span data-ttu-id="dc531-180">Se un'altra modifica dello stato annulla la validità della versione calcolata in precedenza, la versione verrà ricalcolata.</span><span class="sxs-lookup"><span data-stu-id="dc531-180">If another state change invalidates the previously calculated version, it will be recalculated.</span></span> <span data-ttu-id="dc531-181">Non è necessario che gli sviluppatori che usano questa classe siano a conoscenza dei dettagli dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="dc531-181">Developers that use this class do not need to know the details of the implementation.</span></span> <span data-ttu-id="dc531-182">Nessuna di queste modifiche interne ha effetto sull'uso dell'oggetto Person.</span><span class="sxs-lookup"><span data-stu-id="dc531-182">None of these internal changes affect the use of the Person object.</span></span> <span data-ttu-id="dc531-183">Questo è il motivo principale dell'uso delle proprietà per l'esposizione dei membri dati di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="dc531-183">That's the key reason for using Properties to expose data members of an object.</span></span>
 
### <a name="inotifypropertychanged"></a><span data-ttu-id="dc531-184">INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="dc531-184">INotifyPropertyChanged</span></span>

<span data-ttu-id="dc531-185">Uno scenario finale in cui è necessario scrivere codice nella funzione di accesso di una proprietà è quello finalizzato al supporto dell'interfaccia `INotifyPropertyChanged` usata per inviare ai client di data binding la notifica della modifica di un valore.</span><span class="sxs-lookup"><span data-stu-id="dc531-185">A final scenario where you need to write code in a property accessor is to support the `INotifyPropertyChanged` interface used to notify data binding clients that a value has changed.</span></span> <span data-ttu-id="dc531-186">Quando viene modificato il valore di una proprietà, l'oggetto genera l'evento `PropertyChanged` per indicare la modifica.</span><span class="sxs-lookup"><span data-stu-id="dc531-186">When the value of a property changes, the object raises the `PropertyChanged` event to indicate the change.</span></span> <span data-ttu-id="dc531-187">Le librerie di data binding aggiornano a loro volta gli elementi visualizzati in base alla modifica.</span><span class="sxs-lookup"><span data-stu-id="dc531-187">The data binding libraries, in turn, update display elements based on that change.</span></span> <span data-ttu-id="dc531-188">Il codice seguente illustra come implementare `INotifyPropertyChanged` per la proprietà `FirstName` della classe person.</span><span class="sxs-lookup"><span data-stu-id="dc531-188">The code below shows how you would implement `INotifyPropertyChanged` for the `FirstName` property of this person class.</span></span>

```csharp
public class Person : INotifyPropertyChanged
{
    public string FirstName
    {
        get => firstName;
        set
        {
            if (string.IsNullOrWhiteSpace(value))
                throw new ArgumentException("First name must not be blank");
            if (value != firstName)
            {
                PropertyChanged?.Invoke(this, 
                    new PropertyChangedEventArgs(nameof(FirstName)));
            }
            firstName = value;
        }
    }
    private string firstName;

    public event PropertyChangedEventHandler PropertyChanged;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="dc531-189">L'operatore `?.` è chiamato *operatore condizionale Null*.</span><span class="sxs-lookup"><span data-stu-id="dc531-189">The `?.` operator is called the *null conditional operator*.</span></span> <span data-ttu-id="dc531-190">L'operatore cerca un riferimento Null prima di eseguire la valutazione della parte destra dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="dc531-190">It checks for a null reference before evaluating the right side of the operator.</span></span> <span data-ttu-id="dc531-191">Se non vengono trovati sottoscrittori dell'evento `PropertyChanged`, il codice che genera l'evento non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="dc531-191">The end result is that if there are no subscribers to the `PropertyChanged` event, the code to raise the event doesn't execute.</span></span> <span data-ttu-id="dc531-192">In questo caso, verrà generato `NullReferenceException` senza eseguire il controllo.</span><span class="sxs-lookup"><span data-stu-id="dc531-192">It would throw a `NullReferenceException` without this check in that case.</span></span> <span data-ttu-id="dc531-193">Per altre informazioni, vedere la pagina relativa a [`events`](delegates-events.md).</span><span class="sxs-lookup"><span data-stu-id="dc531-193">See the page on [`events`](delegates-events.md) for more details.</span></span> <span data-ttu-id="dc531-194">Questo esempio usa anche il nuovo operatore `nameof` per convertire il simbolo del nome della proprietà nella rappresentazione di testo.</span><span class="sxs-lookup"><span data-stu-id="dc531-194">This example also uses the new `nameof` operator to convert from the property name symbol to its text representation.</span></span>
<span data-ttu-id="dc531-195">L'uso di `nameof` può ridurre gli errori nel caso in cui il nome della proprietà sia stato digitato erroneamente.</span><span class="sxs-lookup"><span data-stu-id="dc531-195">Using `nameof` can reduce errors where you have mistyped the name of the property.</span></span>

<span data-ttu-id="dc531-196">Anche questo è un esempio di un caso in cui è possibile scrivere codice nelle funzioni di accesso per supportare gli scenari necessari.</span><span class="sxs-lookup"><span data-stu-id="dc531-196">Again, this is an example of a case where you can write code in your accessors to support the scenarios you need.</span></span>

## <a name="summing-up"></a><span data-ttu-id="dc531-197">Conclusioni</span><span class="sxs-lookup"><span data-stu-id="dc531-197">Summing up</span></span>

<span data-ttu-id="dc531-198">Le proprietà sono una forma di campi intelligenti in una classe o un oggetto.</span><span class="sxs-lookup"><span data-stu-id="dc531-198">Properties are a form of smart fields in a class or object.</span></span> <span data-ttu-id="dc531-199">All'esterno dell'oggetto, vengono visualizzate come campi dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="dc531-199">From outside the object, they appear like fields in the object.</span></span> <span data-ttu-id="dc531-200">Tuttavia, le proprietà possono essere implementate usando l'intera gamma di funzionalità di C#.</span><span class="sxs-lookup"><span data-stu-id="dc531-200">However, properties can be implemented using the full palette of C# functionality.</span></span>
<span data-ttu-id="dc531-201">È possibile specificare la convalida, un'accessibilità diversa, la valutazione lazy o tutti i requisiti necessari negli scenari.</span><span class="sxs-lookup"><span data-stu-id="dc531-201">You can provide validation, different accessibility, lazy evaluation, or any requirements your scenarios need.</span></span>
