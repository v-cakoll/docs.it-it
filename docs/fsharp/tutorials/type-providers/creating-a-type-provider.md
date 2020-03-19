---
title: 'Esercitazione: Creare un provider di tipiTutorial: Create a Type Provider'
description: Informazioni su come creare provider di tipi F , in F , 3.0 esaminando diversi provider di tipi semplici per illustrare i concetti di base.
ms.date: 11/04/2019
ms.openlocfilehash: 3b8145d4c2d8bf96b6dcf66de02e9f2d83927d74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186115"
---
# <a name="tutorial-create-a-type-provider"></a>Esercitazione: Creare un provider di tipiTutorial: Create a Type Provider

Il meccanismo del provider di tipi in F è una parte significativa del supporto per la programmazione ricca di informazioni. In questa esercitazione viene illustrato come creare provider di tipi personalizzati illustrando lo sviluppo di diversi provider di tipi semplici per illustrare i concetti di base. Per ulteriori informazioni sul meccanismo del provider di tipi in F , vedere [Provider](index.md)di tipi .

L'ecosistema F , contiene una gamma di provider di tipi per Internet di uso comune e servizi dati aziendali. Ad esempio:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) include provider di tipi per i formati di documento JSON, XML, CSV e HTML.

- [SQLProvider](https://fsprojects.github.io/SQLProvider/) fornisce l'accesso fortemente tipizzato ai database SQL tramite un mapping di oggetti e query LINQ F , su queste origini dati.

- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) dispone di un set di provider di tipi per l'incorporamento controllato in fase di compilazione di T-SQL in F.

- [FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) è un set precedente di provider di tipi da utilizzare solo con la programmazione .NET Framework per l'accesso ai servizi dati SQL, Entity Framework, OData e WSDL.

Se necessario, è possibile creare provider di tipi personalizzati oppure fare riferimento a provider di tipi creati da altri utenti. Ad esempio, l'organizzazione potrebbe disporre di un servizio dati che fornisce un numero elevato e crescente di set di dati denominati, ognuno con il proprio schema di dati stabile. È possibile creare un provider di tipi che legge gli schemi e presenta i set di dati correnti al programmatore in modo fortemente tipizzato.

## <a name="before-you-start"></a>Prima di iniziare

Il meccanismo del provider di tipi è progettato principalmente per l'inserimento di spazi di informazioni sui dati e sui servizi stabili nell'esperienza di programmazione di F.

Questo meccanismo non è progettato per l'inserimento di spazi informazioni il cui schema cambia durante l'esecuzione del programma in modi rilevanti per la logica del programma. Inoltre, il meccanismo non è progettato per la metaprogrammazione all'intra-linguaggio, anche se tale dominio contiene alcuni usi validi. È consigliabile utilizzare questo meccanismo solo se necessario e in cui lo sviluppo di un provider di tipi produce un valore molto elevato.

È consigliabile evitare di scrivere un provider di tipi in cui uno schema non è disponibile. Analogamente, è consigliabile evitare di scrivere un provider di tipi in cui sarebbe sufficiente una libreria .NET ordinaria (o anche una esistente).

Prima di iniziare, è possibile porre le seguenti domande:

- Si dispone di uno schema per l'origine delle informazioni? In caso affermativo, qual è il mapping nel sistema di tipi F e .NET?

- È possibile usare un'API esistente (tipizzata in modo dinamico) come punto di partenza per l'implementazione?

- L'utente e l'organizzazione avranno un utilizzo sufficiente del provider di tipi per rendere utile la scrittura? Una normale libreria .NET soddisfa le proprie esigenze?

- Quanto verrà modificato lo schema?

- Cambierà durante la codifica?

- Cambierà tra le sessioni di codifica?

- Cambierà durante l'esecuzione del programma?

I provider di tipi sono più adatti alle situazioni in cui lo schema è stabile in fase di esecuzione e durante la durata del codice compilato.

## <a name="a-simple-type-provider"></a>Un provider di tipi sempliceA Simple Type Provider

L'esempio è Samples.HelloWorldTypeProvider, simile `examples` agli esempi nella directory dell'SDK del [provider di tipi F .](https://github.com/fsprojects/FSharp.TypeProviders.SDK/) Il provider rende disponibile uno "spazio dei tipi" che contiene 100 tipi cancellati, come illustrato nel `Type1`codice seguente utilizzando la sintassi della firma F e omettendo i dettagli per tutti tranne . Per ulteriori informazioni sui tipi cancellati, vedere [Dettagli sui tipi forniti cancellati](#details-about-erased-provided-types) più avanti in questo argomento.

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    nested type NestedType =
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

Si noti che il set di tipi e membri forniti è noto in modo statico. In questo esempio non viene sfruttata la capacità dei provider di fornire tipi che dipendono da uno schema. L'implementazione del provider di tipi è descritta nel codice seguente e i dettagli sono illustrati nelle sezioni successive di questo argomento.

> [!WARNING]
> Potrebbero esserci differenze tra questo codice e gli esempi online.

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =

  // Inheriting from this type provides implementations of ITypeProvider
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) =
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>]
do()
```

Per utilizzare questo provider, aprire un'istanza separata di Visual Studio, creare uno script F , quindi aggiungere un riferimento al provider dallo script utilizzando #r come illustrato nel codice seguente:To use this provider, open a separate instance of Visual Studio, create an F' script, and then add a reference to the provider from your script by using #r as the following code shows:

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

Cercare quindi i tipi `Samples.HelloWorldTypeProvider` nello spazio dei nomi generato dal provider di tipi.

Prima di ricompilare il provider, assicurarsi di aver chiuso tutte le istanze di Visual Studio e F Interactive che utilizzano la DLL del provider. In caso contrario, si verificherà un errore di compilazione perché la DLL di output verrà bloccata.

Per eseguire il debug di questo provider utilizzando le istruzioni print, creare uno script che espone un problema con il provider e quindi utilizzare il codice seguente:

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Per eseguire il debug di questo provider utilizzando Visual Studio, aprire il prompt dei comandi per sviluppatori per Visual Studio con credenziali amministrative ed eseguire il comando seguente:

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

In alternativa, aprire Visual Studio, aprire `Debug/Attach to process…`il menu Debug, scegliere e connettersi a un altro `devenv` processo in cui si sta modificando lo script. Utilizzando questo metodo, è possibile indirizzare più facilmente la logica specifica nel provider di tipi digitando in modo interattivo le espressioni nella seconda istanza (con IntelliSense completo e altre funzionalità).

È possibile disabilitare il debug Just My Code per identificare meglio gli errori nel codice generato. Per informazioni su come abilitare o disabilitare questa funzionalità, vedere [Spostamento all'interno](/visualstudio/debugger/navigating-through-code-with-the-debugger)del codice con il debugger . Inoltre, è anche possibile impostare la `Debug` intercettazione delle `Exceptions` eccezioni first-chance aprendo il `Exceptions` menu e scegliendo o scegliendo i tasti Ctrl , Alt e E per aprire la finestra di dialogo. Nella finestra di `Common Language Runtime Exceptions`dialogo, `Thrown` in , selezionare la casella di controllo.

### <a name="implementation-of-the-type-provider"></a>Implementazione del provider di tipi

In questa sezione vengono illustrate le sezioni principali dell'implementazione del provider di tipi. In primo luogo, si definisce il tipo per il provider di tipi personalizzato stesso:

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

Questo tipo deve essere pubblico ed è necessario contrassegnarlo con il [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attributo in modo che il compilatore riconoscerà il provider di tipi quando un progetto F , separato fa riferimento all'assembly che contiene il tipo. Il *config* config parametro è facoltativo e, se presente, contiene informazioni di configurazione contestuali per l'istanza del provider di tipi che crea il compilatore F.

Successivamente, implementare il [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interfaccia. In questo caso, `TypeProviderForNamespaces` si utilizza `ProvidedTypes` il tipo dall'API come tipo di base. Questo tipo di helper può fornire una raccolta finita di spazi dei nomi forniti con entusiasmo, ognuno dei quali contiene direttamente un numero finito di tipi fissi e forniti con entusiasmo. In questo contesto, il provider genera i tipi *anche* se non sono necessari o utilizzati.

```fsharp
inherit TypeProviderForNamespaces(config)
```

Definire quindi i valori privati locali che specificano lo spazio dei nomi per i tipi forniti e trovare l'assembly del provider di tipi stesso. Questo assembly viene utilizzato in un secondo momento come tipo padre logico dei tipi cancellati forniti.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

Successivamente, creare una funzione per fornire ognuno dei tipi Type1... Tipo100. Questa funzione viene illustrata in modo più dettagliato più avanti in questo argomento.

```fsharp
let makeOneProvidedType (n:int) = …
```

Successivamente, generare i 100 tipi forniti:Next, generate the 100 provided types:

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

Successivamente, aggiungere i tipi come spazio dei nomi fornito:Next, add the types as a provided namespace:

```fsharp
do this.AddNamespace(namespaceName, types)
```

Infine, aggiungere un attributo di assembly che indica che si sta creando una DLL del provider di tipi:Finally, add an assembly attribute that indicates that you are creating a type provider DLL:

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a>Fornire un tipo e i relativi membri

La `makeOneProvidedType` funzione fa il vero lavoro di fornire uno dei tipi.

```fsharp
let makeOneProvidedType (n:int) =
…
```

In questo passaggio viene illustrata l'implementazione di questa funzione. In primo luogo, creare il tipo fornito (ad esempio, Tipo1, quando n è 1 o Tipo57, quando n è 57).

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

È necessario notare i seguenti punti:

- Questo tipo fornito viene cancellato.  Poiché si indica che `obj`il tipo di base è , le istanze verranno visualizzate come valori di tipo [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) nel codice compilato.

- Quando si specifica un tipo non annidato, è necessario specificare l'assembly e lo spazio dei nomi. Per i tipi cancellati, l'assembly deve essere l'assembly del provider di tipi stesso.

Aggiungere quindi la documentazione XML al tipo. Questa documentazione viene ritardata, ovvero calcolata su richiesta se il compilatore host ne ha bisogno.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

Successivamente si aggiunge una proprietà statica fornita al tipo:Next you add a provided static property to the type:

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

Ottenere questa proprietà restituirà sempre la stringa "Hello!". Il `GetterCode` per la proprietà utilizza una citazione di F , che rappresenta il codice generato dal compilatore host per ottenere la proprietà. Per ulteriori informazioni sulle offerte, vedere Citazioni di codice [(F )](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).

Aggiungere la documentazione XML alla proprietà.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

Associare ora la proprietà fornita al tipo fornito. È necessario associare un membro fornito a un solo tipo. In caso contrario, il membro non sarà mai accessibile.

```fsharp
t.AddMember staticProp
```

Creare ora un costruttore fornito che non accetta parametri.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

Il `InvokeCode` per il costruttore restituisce un'offerta di F , che rappresenta il codice generato dal compilatore host quando viene chiamato il costruttore. Ad esempio, è possibile utilizzare il seguente costruttore:

```fsharp
new Type10()
```

Verrà creata un'istanza del tipo fornito con i dati sottostanti "I dati dell'oggetto". Il codice citato include una conversione in [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) perché tale tipo è la cancellazione di questo tipo fornito (come specificato al momento della creazione del tipo fornito).

Aggiungere la documentazione XML al costruttore e aggiungere il costruttore fornito al tipo fornito:Add XML documentation to the constructor, and add the provided constructor to the provided type:

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

Creare un secondo costruttore fornito che accetta un parametro:Create a second provided constructor that takes one parameter:

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

Il `InvokeCode` per il costruttore restituisce nuovamente un'offerta di F , che rappresenta il codice generato dal compilatore host per una chiamata al metodo. Ad esempio, è possibile utilizzare il seguente costruttore:

```fsharp
new Type10("ten")
```

Un'istanza del tipo fornito viene creata con i dati sottostanti "dieci". Potresti aver già `InvokeCode` notato che la funzione restituisce un'offerta. L'input di questa funzione è un elenco di espressioni, una per ogni parametro del costruttore. In questo caso, un'espressione che rappresenta `args.[0]`il valore del singolo parametro è disponibile in . Il codice per una chiamata al costruttore forza il valore `obj`restituito al tipo cancellato. Dopo aver aggiunto il secondo costruttore fornito al tipo, creare una proprietà di istanza fornita:After you add the second provided constructor to the type, you create a provided instance property:

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

Ottenere questa proprietà restituirà la lunghezza della stringa, ovvero l'oggetto rappresentazione. La `GetterCode` proprietà restituisce un'offerta di F, che specifica il codice generato dal compilatore host per ottenere la proprietà. Come `InvokeCode`, `GetterCode` la funzione restituisce un'offerta. Il compilatore host chiama questa funzione con un elenco di argomenti. In questo caso, gli argomenti includono solo la singola espressione che rappresenta l'istanza su `args.[0]`cui viene chiamato il metodo di chiamata, a cui è possibile accedere utilizzando . L'implementazione di quindi giunzioni nell'offerta di `obj`risultato in corrispondenza del tipo cancellato e un cast viene utilizzato per soddisfare il meccanismo del compilatore per il controllo dei `GetterCode` tipi che l'oggetto è una stringa. La parte `makeOneProvidedType` successiva di fornisce un metodo di istanza con un parametro.

```fsharp
let instanceMeth =
    ProvidedMethod(methodName = "InstanceMethod",
                   parameters = [ProvidedParameter("x",typeof<int>)],
                   returnType = typeof<char>,
                   invokeCode = (fun args ->
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

Infine, creare un tipo annidato che contiene 100 proprietà annidate. La creazione di questo tipo annidato e delle relative proprietà viene ritardata, ovvero calcolata su richiesta.

```fsharp
t.AddMembersDelayed(fun () ->
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () ->
    let staticPropsInNestedType =
      [
          for i in 1 .. 100 ->
              let valueOfTheProperty = "I am string "  + string i

              let p =
                ProvidedProperty(propertyName = "StaticProperty" + string i,
                  propertyType = typeof<string>,
                  isStatic = true,
                  getterCode= (fun args -> <@@ valueOfTheProperty @@>))

              p.AddXmlDocDelayed(fun () ->
                  sprintf "This is StaticProperty%d on NestedType" i)

              p
      ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a>Dettagli sui tipi forniti cancellati

Nell'esempio riportato in questa sezione vengono forniti solo *i tipi forniti cancellati,* particolarmente utili nelle situazioni seguenti:

- Quando si scrive un provider per uno spazio informazioni che contiene solo dati e metodi.

- Quando si scrive un provider in cui una semantica accurata del tipo di runtime non è fondamentale per l'uso pratico dello spazio informazioni.

- Quando si scrive un provider per uno spazio informazioni così grande e interconnesso che non è tecnicamente possibile generare tipi .NET reali per lo spazio informazioni.

In questo esempio, ogni tipo fornito `obj`viene cancellato in type e `obj` tutti gli utilizzi del tipo verranno visualizzati come tipo nel codice compilato. Infatti, gli oggetti sottostanti in questi esempi sono `System.Object` stringhe, ma il tipo verrà visualizzato come nel codice compilato .NET. Come per tutti gli usi della cancellazione del tipo, è possibile utilizzare il boxing esplicito, l'unboxing e il cast ai tipi cancellati sovvertiti. In questo caso, un'eccezione cast non valida può generare quando viene utilizzato l'oggetto. Un runtime del provider può definire il proprio tipo di rappresentazione privata per la protezione da false rappresentazioni. Non è possibile definire i tipi cancellati in F . Solo i tipi forniti possono essere cancellati. È necessario comprendere le ramificazioni, sia pratiche che semantiche, dell'utilizzo di tipi cancellati per il provider di tipi o di un provider che fornisce tipi cancellati. Un tipo cancellato non ha un tipo .NET reale. Pertanto, non è possibile eseguire una reflection accurata sul tipo ed è possibile sovvertire i tipi cancellati se si utilizzano cast di runtime e altre tecniche che si basano sulla semantica esatta dei tipi di runtime. La sottoversione dei tipi cancellati spesso genera eccezioni di cast dei tipi in fase di esecuzione.

### <a name="choosing-representations-for-erased-provided-types"></a>Scelta delle rappresentazioni per i tipi forniti cancellatiChoosing Representations for Erased Provided Types

Per alcuni utilizzi dei tipi forniti cancellati, non è necessaria alcuna rappresentazione. Ad esempio, il tipo fornito cancellato potrebbe contenere solo proprietà statiche e membri e nessun costruttore e nessun metodo o proprietà restituirebbe un'istanza del tipo. Se è possibile raggiungere istanze di un tipo fornito cancellato, è necessario considerare le domande seguenti:If you can reach instances of an erased provided type, you must consider the following questions:

**Qual è la cancellazione di un tipo fornito?**

- La cancellazione di un tipo fornito è il modo in cui il tipo viene visualizzato nel codice .NET compilato.

- La cancellazione di un tipo di classe cancellato fornito è sempre il primo tipo di base non cancellato nella catena di ereditarietà del tipo.

- La cancellazione di un tipo di `System.Object`interfaccia cancellata fornita è sempre .

**Quali sono le rappresentazioni di un tipo fornito?**

- L'insieme di oggetti possibili per un tipo fornito cancellato sono chiamati le relative rappresentazioni. Nell'esempio in questo documento, le rappresentazioni di `Type1..Type100` tutti i tipi forniti cancellati sono sempre oggetti stringa.

Tutte le rappresentazioni di un tipo fornito devono essere compatibili con la cancellazione del tipo fornito. (In caso contrario, il compilatore F , verrà generato un errore per un utilizzo del provider di tipi o non verificabile verrà generato codice .NET non valido. Un provider di tipi non è valido se restituisce un codice che fornisce una rappresentazione non valida.

È possibile scegliere una rappresentazione per gli oggetti forniti utilizzando uno dei seguenti approcci, entrambi molto comuni:

- Se si fornisce semplicemente un wrapper fortemente tipizzato su un tipo .NET esistente, è spesso opportuno che il tipo cancelli a tale tipo, utilizzi istanze di tale tipo come rappresentazioni o entrambi. Questo approccio è appropriato quando la maggior parte dei metodi esistenti su tale tipo ha ancora senso quando si utilizza la versione fortemente tipizzata.

- Se si desidera creare un'API che differisce in modo significativo da qualsiasi API .NET esistente, è opportuno creare tipi di runtime che saranno la cancellazione dei tipi e le rappresentazioni per i tipi forniti.

L'esempio in questo documento usa le stringhe come rappresentazioni di oggetti forniti. Spesso, può essere opportuno utilizzare altri oggetti per le rappresentazioni. Ad esempio, è possibile utilizzare un dizionario come contenitore delle proprietà:For example, you may use a dictionary as a property bag:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

In alternativa, è possibile definire un tipo nel provider di tipi che verrà utilizzato in fase di esecuzione per formare la rappresentazione, insieme a una o più operazioni di runtime:Alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

I membri forniti possono quindi costruire istanze di questo tipo di oggetto:Provided members can then construct instances of this object type:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

In questo caso, è possibile (facoltativamente) utilizzare questo tipo come tipo `baseType` di cancellazione specificando questo tipo come quando si costruisce il `ProvidedTypeDefinition`:

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>Lezioni chiave

Nella sezione precedente è stato illustrato come creare un provider di tipi di cancellazione semplice che fornisce una gamma di tipi, proprietà e metodi. In questa sezione è stato inoltre illustrato il concetto di cancellazione dei tipi, inclusi alcuni dei vantaggi e degli svantaggi di fornire tipi cancellati da un provider di tipi e sono state discusse le rappresentazioni dei tipi cancellati.

## <a name="a-type-provider-that-uses-static-parameters"></a>Un provider di tipi che utilizza parametri staticiA Type Provider That Uses Static Parameters

La possibilità di parametrizzare i provider di tipi in base ai dati statici consente molti scenari interessanti, anche nei casi in cui il provider non deve accedere a dati locali o remoti. In questa sezione, imparerai alcune tecniche di base per mettere insieme un provider di questo tipo.

### <a name="type-checked-regex-provider"></a>Tipo Checked Regex Provider

Si supponga di voler implementare un provider di tipi <xref:System.Text.RegularExpressions.Regex> per le espressioni regolari che esegue il wrapping delle librerie .NET in un'interfaccia che fornisce le seguenti garanzie in fase di compilazione:

- Verifica della validità di un'espressione regolare.

- Fornire proprietà denominate per le corrispondenze basate su qualsiasi nome di gruppo nell'espressione regolare.

In questa sezione viene illustrato come `RegexTyped` utilizzare i provider di tipi per creare un tipo che il modello di espressione regolare parametrizza per fornire questi vantaggi. Il compilatore segnalerà un errore se il modello fornito non è valido e il provider di tipi può estrarre i gruppi dal modello in modo che sia possibile accedervi usando le proprietà denominate nelle corrispondenze. Quando si progetta un provider di tipi, è necessario considerare come l'API esposta deve essere per gli utenti finali e come questa progettazione verrà convertita in codice .NET. L'esempio seguente mostra come usare un'API di questo tipo per ottenere i componenti del prefisso:

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

Nell'esempio seguente viene illustrato come il provider di tipi converte queste chiamate:The following example shows how the type provider translates these calls:

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

Tenere presente quanto segue:

- Il tipo Regex standard `RegexTyped` rappresenta il tipo con parametri.

- Il `RegexTyped` costruttore genera una chiamata al costruttore Regex, passando l'argomento di tipo statico per il modello.

- I risultati `Match` del metodo sono <xref:System.Text.RegularExpressions.Match> rappresentati dal tipo standard.

- Ogni gruppo denominato genera una proprietà fornita e l'accesso alla proprietà comporta l'utilizzo di un indicizzatore nella raccolta di `Groups` una corrispondenza.

Il codice seguente è il nucleo della logica per implementare tale provider e in questo esempio viene omalsa l'aggiunta di tutti i membri al tipo fornito. Per informazioni su ogni membro aggiunto, vedere la sezione appropriata più avanti in questo argomento. Per il codice completo, scaricare l'esempio dal pacchetto di [esempio di F . 3.0](https://archive.codeplex.com/?p=fsharp3sample) sul sito Web CodePlex.

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with
          | [| :? string as pattern|] ->

            // Create an instance of the regular expression.
            //
            // This will fail with System.ArgumentException if the regular expression is not valid.
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty =
              ProvidedTypeDefinition(
                thisAssembly,
                rootNamespace,
                typeName,
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

Tenere presente quanto segue:

- Il provider di tipi accetta `pattern`due parametri statici: , che è obbligatorio, e `options`, che sono facoltativi (perché viene fornito un valore predefinito).

- Dopo aver fornito gli argomenti statici, si crea un'istanza dell'espressione regolare. Questa istanza genererà un'eccezione se il Regex non è valido e questo errore verrà segnalato agli utenti.

- All'interno del `DefineStaticParameters` callback, si definisce il tipo che verrà restituito dopo che gli argomenti vengono forniti.

- Questo codice `HideObjectMethods` viene impostato su true in modo che l'esperienza IntelliSense rimarrà semplificata. Questo attributo `Equals` `GetHashCode`fa `Finalize`sì `GetType` che i membri , , e vengano eliminati dagli elenchi IntelliSense per un oggetto fornito.

- Utilizzare `obj` come tipo di base del metodo, ma `Regex` si utilizzerà un oggetto come rappresentazione di runtime di questo tipo, come illustrato nell'esempio seguente.

- La chiamata `Regex` al costruttore <xref:System.ArgumentException> genera un quando un'espressione regolare non è valida. Il compilatore intercetta questa eccezione e segnala un messaggio di errore all'utente in fase di compilazione o nell'editor di Visual Studio. Questa eccezione consente la convalida delle espressioni regolari senza eseguire un'applicazione.

Il tipo definito in precedenza non è ancora utile perché non contiene proprietà o metodi significativi. Aggiungere innanzitutto `IsMatch` un metodo statico:First, add a static method:

```fsharp
let isMatch =
    ProvidedMethod(
        methodName = "IsMatch",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = typeof<bool>,
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string."
ty.AddMember isMatch
```

Il codice precedente definisce un metodo , che `bool`accetta una stringa come input e restituisce un oggetto `IsMatch`. L'unica parte difficile è `args` l'uso `InvokeCode` dell'argomento all'interno della definizione. In questo `args` esempio, è un elenco di citazioni che rappresenta gli argomenti di questo metodo. Se il metodo è un metodo di `this` istanza, il primo argomento rappresenta l'argomento. Tuttavia, per un metodo statico, gli argomenti sono tutti solo gli argomenti espliciti per il metodo. Si noti che il tipo del valore tra virgolette `bool`deve corrispondere al tipo restituito specificato (in questo caso, ). Si noti inoltre `AddXmlDoc` che questo codice utilizza il metodo per assicurarsi che il metodo fornito disponga anche di documentazione utile, che è possibile fornire tramite IntelliSense.Also note that this code uses the method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.

Successivamente, aggiungere un'istanza Match metodo. Tuttavia, questo metodo deve restituire `Match` un valore di un tipo fornito in modo che i gruppi sono accessibili in modo fortemente tipizzato. Pertanto, è `Match` innanzitutto dichiarato il tipo. Poiché questo tipo dipende dal modello fornito come argomento statico, questo tipo deve essere annidato all'interno della definizione del tipo con parametri:Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

Aggiungere quindi una proprietà al tipo di corrispondenza per ogni gruppo. In fase di esecuzione, <xref:System.Text.RegularExpressions.Match> una corrispondenza viene rappresentata come valore, pertanto l'offerta che definisce la proprietà deve utilizzare la <xref:System.Text.RegularExpressions.Match.Groups> proprietà indicizzata per ottenere il gruppo pertinente.

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop =
      ProvidedProperty(
        propertyName = group,
        propertyType = typeof<Group>,
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

Anche in questo caso, si noti che si sta aggiungendo la documentazione XML alla proprietà fornita. Si noti inoltre che una `GetterCode` proprietà può essere letta se viene `SetterCode` fornita una funzione e la proprietà può essere scritta se viene fornita una funzione, pertanto la proprietà risultante è di sola lettura.

A questo punto è possibile creare un `Match` metodo di istanza che restituisce un valore di questo tipo:Now you can create an instance method that returns a value of this type:

```fsharp
let matchMethod =
    ProvidedMethod(
        methodName = "Match",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = matchTy,
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

ty.AddMember matchMeth
```

Poiché si sta creando `args.[0]` un `RegexTyped` metodo di istanza, rappresenta `args.[1]` l'istanza in cui viene chiamato il metodo ed è l'argomento di input.

Infine, fornire un costruttore in modo che le istanze del tipo fornito possono essere create.

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

Il costruttore si limita a cancellare la creazione di un'istanza Regex .NET standard, che viene nuovamente sottoposta a boxing in un oggetto perché `obj` è la cancellazione del tipo fornito. Con tale modifica, l'utilizzo dell'API di esempio specificato in precedenza nell'argomento funziona come previsto. Il codice seguente è completo e finale:The following code is complete and final:

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with
            | [| :? string as pattern|] ->

                // Create an instance of the regular expression.

                let r = System.Text.RegularExpressions.Regex(pattern)

                // Declare the typed regex provided type.

                let ty =
                    ProvidedTypeDefinition(
                        thisAssembly,
                        rootNamespace,
                        typeName,
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch =
                    ProvidedMethod(
                        methodName = "IsMatch",
                        parameters = [ProvidedParameter("input", typeof<string>)],
                        returnType = typeof<bool>,
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy =
                    ProvidedTypeDefinition(
                        "MatchType",
                        baseType = Some baseTy,
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop =
                          ProvidedProperty(
                            propertyName = group,
                            propertyType = typeof<Group>,
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth =
                  ProvidedMethod(
                    methodName = "Match",
                    parameters = [ProvidedParameter("input", typeof<string>)],
                    returnType = matchTy,
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor =
                  ProvidedConstructor(
                    parameters = [],
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a>Lezioni chiave

In questa sezione è stato illustrato come creare un provider di tipi che opera sui relativi parametri statici. Il provider controlla il parametro statico e fornisce le operazioni in base al relativo valore.

## <a name="a-type-provider-that-is-backed-by-local-data"></a>Un provider di tipi supportato da dati localiA Type Provider That Is Backed by Local Data

Spesso si desidera che i provider di tipi presentino API basate non solo su parametri statici, ma anche informazioni provenienti da sistemi locali o remoti. In questa sezione vengono illustrati i provider di tipi basati su dati locali, ad esempio i file di dati locali.

### <a name="simple-csv-file-provider"></a>Provider di file CSV semplice

Come semplice esempio, si consideri un provider di tipi per l'accesso ai dati scientifici in formato CSV (Comma Separated Value). In questa sezione si presuppone che i file CSV contengano una riga di intestazione seguita da dati a virgola mobile, come illustrato nella tabella seguente:

|Distanza (metro)|Tempo (secondo)|
|----------------|-------------|
|50.0|3,7|
|100.0|5,2|
|150.0|6.4|

In questa sezione viene illustrato come fornire un tipo `Distance` che `float<meter>` è `Time` possibile utilizzare `float<second>`per ottenere righe con una proprietà di tipo e una proprietà di tipo . Per semplicità, vengono formulati i seguenti presupposti:

- I nomi delle intestazioni sono senza unità o hanno il formato "Nome (unità)" e non contengono virgole.

- Le unità sono tutte unità di System International (SI) come definito dal modulo [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F )](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) .

- Le unità sono tutte semplici (ad esempio, metro) anziché composte (ad esempio, metro/secondo).

- Tutte le colonne contengono dati a virgola mobile.

Un fornitore più completo allenterebbe queste restrizioni.

Anche in questo caso il primo passaggio consiste nel considerare l'aspetto dell'API. Dato un file `info.csv` con i contenuti della tabella precedente (nel formato delimitato da virgole), gli utenti del provider possono scrivere codice simile all'esempio seguente:

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

In questo caso, il compilatore deve convertire queste chiamate in qualcosa di simile all'esempio seguente:In this case, the compiler should convert these calls into something like the following example:

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

La conversione ottimale richiederà al `CsvFile` provider di tipi di definire un tipo reale nell'assembly del provider di tipi. I provider di tipi spesso si basano su alcuni tipi di supporto e metodi per eseguire il wrapping di logica importante. Poiché le misure vengono cancellate in `float[]` fase di esecuzione, è possibile utilizzare un tipo come tipo cancellato per una riga. Il compilatore considererà colonne diverse come con tipi di misura diversi. Ad esempio, la prima colonna `float<meter>`dell'esempio include `float<second>`type e la seconda con . Tuttavia, la rappresentazione cancellata può rimanere abbastanza semplice.

Il codice seguente mostra il nucleo dell'implementazione.

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data =
        seq {
            for line in File.ReadAllLines(filename) |> Seq.skip 1 ->
                line.Split(',') |> Array.map float
        }
        |> Seq.cache
    member _.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->

        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop =
                ProvidedProperty(fieldName, fieldTy,
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop)

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 =
            ProvidedConstructor([],
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)],
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop =
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy),
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

Tenere presente i punti seguenti sull'implementazione:Note the following points about the implementation:

- I costruttori di overload consentono di leggere il file originale o uno con uno schema identico. Questo modello è comune quando si scrive un provider di tipi per origini dati locali o remote e questo modello consente di usare un file locale come modello per i dati remoti.

- È possibile utilizzare il valore [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) passato al costruttore del provider di tipi per risolvere i nomi di file relativi.

- È possibile `AddDefinitionLocation` utilizzare il metodo per definire la posizione delle proprietà fornite. Pertanto, se `Go To Definition` si utilizza su una proprietà fornita, il file CSV verrà aperto in Visual Studio.

- È possibile `ProvidedMeasureBuilder` utilizzare il tipo per cercare le `float<_>` unità SI e per generare i tipi pertinenti.

### <a name="key-lessons"></a>Lezioni chiave

In questa sezione è stato illustrato come creare un provider di tipi per un'origine dati locale con uno schema semplice contenuto nell'origine dati stessa.

## <a name="going-further"></a>Approfondimenti

Le sezioni seguenti includono suggerimenti per ulteriori studi.

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>Uno sguardo al codice compilato per i tipi cancellati

Per fornire un'idea di come l'utilizzo del provider di tipi corrisponde al codice generato, esaminare la funzione seguente utilizzando l'oggetto `HelloWorldTypeProvider` utilizzato in precedenza in questo argomento.

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

Di seguito è riportata un'immagine del codice risultante decompilato utilizzando ildasm.exe:

```il
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

Come illustrato nell'esempio, tutte `Type1` le `InstanceProperty` menzioni del tipo e della proprietà sono state cancellate, lasciando solo le operazioni sui tipi di runtime coinvolti.

### <a name="design-and-naming-conventions-for-type-providers"></a>Convenzioni di progettazione e denominazione per i provider di tipiDesign and Naming Conventions for Type Providers

Quando si creano provider di tipi, osservare le convenzioni seguenti.

**Provider per protocolli di connettività** In generale, i nomi della maggior parte delle DLL del provider per i protocolli `TypeProvider` di `TypeProviders`connettività dei dati e dei servizi, ad esempio le connessioni OData o SQL, devono terminare con o . Ad esempio, utilizzare un nome di DLL analogo alla stringa seguente:

`Fabrikam.Management.BasicTypeProviders.dll`

Assicurarsi che i tipi forniti siano membri dello spazio dei nomi corrispondente e indicare il protocollo di connettività implementato:

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**Fornitori di utilità per la codifica generale**.  Per un provider di tipi di utilità come quello per le espressioni regolari, il provider di tipi può far parte di una libreria di base, come illustrato nell'esempio seguente:For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

In questo caso, il tipo fornito verrà visualizzato in un punto appropriato in base alle normali convenzioni di progettazione .NET:In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

**Origini dati Singleton**. Alcuni provider di tipi si connettono a una singola origine dati dedicata e forniscono solo dati. In questo caso, è `TypeProvider` necessario eliminare il suffisso e utilizzare le normali convenzioni per la denominazione .NET:In this case, you should drop the suffix and use normal conventions for .NET naming:

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

Per altre informazioni, `GetConnection` vedere la convenzione di progettazione descritta più avanti in questo argomento.

### <a name="design-patterns-for-type-providers"></a>Modelli di progettazione per i provider di tipiDesign Patterns for Type Providers

Nelle sezioni seguenti vengono descritti i modelli di progettazione che è possibile utilizzare per la creazione di provider di tipi.

#### <a name="the-getconnection-design-pattern"></a>Il modello di progettazione GetConnectionThe GetConnection Design Pattern

La maggior parte dei provider `GetConnection` di tipi deve essere scritta per utilizzare il modello utilizzato dai provider di tipi in FSharp.Data.TypeProviders.dll, come illustrato nell'esempio seguente:

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>Provider di tipi supportati da servizi e dati remotiType Providers Backed By Remote Data and Services

Prima di creare un provider di tipi supportato da dati e servizi remoti, è necessario considerare una serie di problemi inerenti alla programmazione connessa. Questi problemi includono le considerazioni seguenti:These issues include the following considerations:

- mapping dello schema

- liveness e invalidazione in presenza di modifica dello schema

- memorizzazione nella cache dello schema

- implementazioni asincrone delle operazioni di accesso ai dati

- query di supporto, incluse le query LINQSupporting queries, including LINQ queries

- credenziali e autenticazione

In questo argomento non vengono esaminati ulteriormente questi problemi.

### <a name="additional-authoring-techniques"></a>Tecniche di creazione aggiuntiveAdditional Authoring Techniques

Quando si scrivono provider di tipi personalizzati, è possibile utilizzare le tecniche aggiuntive seguenti.

### <a name="creating-types-and-members-on-demand"></a>Creazione di tipi e membri su richiestaCreating Types and Members On-Demand

L'API ProvidedType ha ritardato le versioni di AddMember.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

Queste versioni vengono utilizzate per creare spazi su richiesta di tipi.

### <a name="providing-array-types-and-generic-type-instantiations"></a>Fornitura di tipi di matrice e istanze di tipi genericiProviding Array types and Generic Type Instantiations

I membri forniti vengono forniti (le cui firme includono tipi di matrice, tipi `MakeArrayType` `MakePointerType`byref `MakeGenericType` e istanze di tipi generici) utilizzando le normali , , e in qualsiasi istanza di <xref:System.Type>, tra cui `ProvidedTypeDefinitions`.

> [!NOTE]
> In alcuni casi potrebbe essere necessario `ProvidedTypeBuilder.MakeGenericType`utilizzare l'helper in .  Per ulteriori informazioni, vedere la [documentazione di Type Provider SDK.](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations)

### <a name="providing-unit-of-measure-annotations"></a>Fornire annotazioni di unità di misura

L'API ProvidedTypes fornisce helper per fornire annotazioni di misura. Ad esempio, per `float<kg>`fornire il tipo , utilizzare il codice seguente:

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  Per fornire `Nullable<decimal<kg/m^2>>`il tipo , utilizzare il codice seguente:

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>Accesso alle risorse locali o locali per gli script

A ogni istanza di un `TypeProviderConfig` provider di tipi può essere assegnato un valore durante la costruzione. Questo valore contiene la "cartella di risoluzione" per il provider, ovvero la cartella del progetto per la compilazione o la directory che contiene uno script, l'elenco degli assembly a cui si fa riferimento e altre informazioni.

### <a name="invalidation"></a>Invalidazione

I provider possono generare segnali di invalidamento per notificare al servizio di linguaggio F , che i presupposti dello schema potrebbero essere stati modificati. Quando si verifica l'invalidazione, un controllo dei tipi viene rifatto se il provider è ospitato in Visual Studio.When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio. Questo segnale verrà ignorato quando il provider è ospitato in F , Interactive o dal compilatore F , fsc.exe .

### <a name="caching-schema-information"></a>Memorizzazione nella cache delle informazioni sullo schemaCaching Schema Information

I provider devono spesso memorizzare nella cache l'accesso alle informazioni sullo schema. I dati memorizzati nella cache devono essere archiviati utilizzando un nome di file specificato come parametro statico o come dati utente. Un esempio di memorizzazione `LocalSchemaFile` nella cache dello `FSharp.Data.TypeProviders` schema è il parametro nei provider di tipi nell'assembly. Nell'implementazione di questi provider, questo parametro statico indica al provider di tipi di utilizzare le informazioni sullo schema nel file locale specificato anziché accedere all'origine dati in rete. Per utilizzare le informazioni sullo schema memorizzate nella cache, è inoltre necessario impostare il parametro `ForceUpdate` static su `false`. È possibile utilizzare una tecnica simile per abilitare l'accesso ai dati online e offline.

### <a name="backing-assembly"></a>Assemblaggio di backup

Quando si `.dll` compila `.exe` un file o , il file DLL di backup per i tipi generati viene collegato in modo statico all'assembly risultante. Questo collegamento viene creato copiando le definizioni di tipo IL (Intermediate Language) e tutte le risorse gestite dall'assembly di backup nell'assembly finale. Quando si utilizza f , il file DLL di backup non viene copiato e viene invece caricato direttamente nel processo interattivo di F.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>Eccezioni e diagnostica dai provider di tipiExceptions and Diagnostics from Type Providers

Tutti gli utilizzi di tutti i membri dai tipi forniti possono generare eccezioni. In tutti i casi, se un provider di tipi genera un'eccezione, il compilatore host attribuisce l'errore a un provider di tipi specifico.

- Le eccezioni del provider di tipi non devono mai generare errori interni del compilatore.

- I provider di tipi non possono segnalare avvisi.

- Quando un provider di tipi è ospitato nel compilatore F , in un ambiente di sviluppo F , o interattivo F , vengono rilevate tutte le eccezioni da tale provider. Il Message proprietà è sempre il testo dell'errore e non viene visualizzata alcuna traccia dello stack. Se si intende generare un'eccezione, è `System.NotSupportedException`possibile `System.IO.IOException` `System.Exception`generare gli esempi seguenti: , , .

#### <a name="providing-generated-types"></a>Fornire tipi generati

Finora, questo documento ha spiegato come fornire i tipi cancellati. È anche possibile usare il meccanismo del provider di tipi in F , per fornire i tipi generati, che vengono aggiunti come definizioni di tipo .NET reali nel programma degli utenti. È necessario fare riferimento ai tipi forniti generati utilizzando una definizione di tipo.

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

Il codice helper ProvidedTypes-0.2 che fa parte della versione di F . Le istruzioni seguenti devono essere true per una definizione di tipo generata:The following statements must be true for a generated type definition:

- `isErased` deve essere impostato su `false`.

- Il tipo generato deve essere `ProvidedAssembly()`aggiunto a un oggetto appena costruito, che rappresenta un contenitore per i frammenti di codice generati.

- Il provider deve disporre di un assembly che dispone di un file .dll .NET di backup effettivo con un file DLL corrispondente su disco.

## <a name="rules-and-limitations"></a>Regole e limitazioni

Quando si scrivono provider di tipi, tenere presenti le regole e le limitazioni seguenti.

### <a name="provided-types-must-be-reachable"></a>I tipi forniti devono essere raggiungibili

Tutti i tipi forniti devono essere raggiungibili dai tipi non annidati. I tipi non annidati vengono forniti `TypeProviderForNamespaces` nella chiamata `AddNamespace`al costruttore o in una chiamata a . Ad esempio, se il `StaticClass.P : T`provider fornisce un tipo , è necessario assicurarsi che T sia un tipo non annidato o annidato sotto uno.

Ad esempio, alcuni provider hanno `DataTypes` una classe `T1, T2, T3, ...` statica, ad esempio che contengono questi tipi. In caso contrario, l'errore indica che è stato trovato un riferimento al tipo T nell'assembly A, ma il tipo non è stato trovato in tale assembly. Se viene visualizzato questo errore, verificare che tutti i sottotipi siano raggiungibili dai tipi di provider. Nota: `T1, T2, T3...` questi tipi sono indicati come tipi *al volo.* Ricordarsi di inserirli in uno spazio dei nomi accessibile o in un tipo padre.

### <a name="limitations-of-the-type-provider-mechanism"></a>Limitazioni del meccanismo del provider di tipi

Il meccanismo del provider di tipi in F , presenta le limitazioni seguenti:The type provider mechanism in F' has the following limitations:

- L'infrastruttura sottostante per i provider di tipi in F , non supporta i tipi generici forniti o i metodi generici forniti.

- Il meccanismo non supporta i tipi annidati con parametri statici.

## <a name="development-tips"></a>Suggerimenti per lo sviluppo

Durante il processo di sviluppo, è possibile trovare utili i suggerimenti seguenti:You might find the following tips helpful during the development process:

### <a name="run-two-instances-of-visual-studio"></a>Eseguire due istanze di Visual StudioRun two instances of Visual Studio

È possibile sviluppare il provider di tipi in un'istanza e testare il provider nell'altra perché l'IDE di test accetta un blocco sul file DLL che impedisce la ricompilazione del provider di tipi. Pertanto, è necessario chiudere la seconda istanza di Visual Studio mentre il provider è compilato nella prima istanza e quindi è necessario riaprire la seconda istanza dopo la compilazione del provider.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>Eseguire il debug dei provider di tipi utilizzando le chiamate di fsc.exe

È possibile richiamare i provider di tipi utilizzando gli strumenti seguenti:You can invoke type providers by using the following tools:

- fsc.exe (Compilatore da riga di comando F)

- fsi.exe (Compilatore interattivo F)

- devenv.exe (Visual Studio)

È spesso possibile eseguire il debug dei provider di tipi più facilmente utilizzando fsc.exe in un file script di test, ad esempio script.fsx. È possibile avviare un debugger da un prompt dei comandi.

```console
devenv /debugexe fsc.exe script.fsx
```

  È possibile utilizzare la registrazione da stampa a stdout.

## <a name="see-also"></a>Vedere anche

- [Provider di tipi](index.md)
- [SDK del provider di tipi](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
