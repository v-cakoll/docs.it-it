---
title: 'Esercitazione: creare un provider di tipi'
description: 'Informazioni su come creare provider di tipi F # personalizzati in F # 3,0 esaminando diversi provider di tipi semplici per illustrare i concetti di base.'
ms.date: 11/04/2019
ms.openlocfilehash: 67ebd91007ff814370573ebc1a65b2c7a8399f7d
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202137"
---
# <a name="tutorial-create-a-type-provider"></a>Esercitazione: creare un provider di tipi

Il meccanismo del provider di tipi in F # è una parte significativa del suo supporto per la programmazione avanzata delle informazioni. Questa esercitazione illustra come creare provider di tipi personalizzati grazie allo sviluppo di diversi provider di tipi semplici per illustrare i concetti di base. Per ulteriori informazioni sul meccanismo del provider di tipi in F #, vedere [provider di tipi](index.md).

L'ecosistema F # contiene una gamma di provider di tipi per i servizi dati Internet e aziendali di uso comune. Ad esempio:

- [FSharp. Data](https://fsharp.github.io/FSharp.Data/) include provider di tipi per i formati di documenti JSON, XML, CSV e HTML.

- [Sqlfornitor](https://fsprojects.github.io/SQLProvider/) fornisce accesso fortemente tipizzato ai database SQL tramite un mapping di oggetti e query LINQ F # su tali origini dati.

- [FSharp. Data. SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) include un set di provider di tipi per l'incorporamento di T-SQL selezionato in fase di compilazione in F #.

- [FSharp. Data. TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) è un set di provider di tipi obsoleto che può essere utilizzato solo con la programmazione .NET Framework per l'accesso a SQL, Entity Framework, OData e WSDL Data Services.

Se necessario, è possibile creare provider di tipi personalizzati o fare riferimento a provider di tipi creati da altri. Ad esempio, l'organizzazione potrebbe disporre di un servizio dati che fornisce un numero elevato e crescente di set di dati denominati, ognuno con un proprio schema di dati stabile. È possibile creare un provider di tipi che legge gli schemi e presenta i set di dati correnti al programmatore in modo fortemente tipizzato.

## <a name="before-you-start"></a>Prima di iniziare

Il meccanismo del provider di tipi è progettato principalmente per inserire dati stabili e spazi di informazioni sui servizi nell'esperienza di programmazione F #.

Questo meccanismo non è progettato per l'inserimento di spazi di informazioni con modifiche dello schema durante l'esecuzione del programma in modi rilevanti per la logica del programma. Inoltre, il meccanismo non è progettato per la metaprogrammazione intra-linguaggio, anche se tale dominio contiene alcuni usi validi. È consigliabile utilizzare questo meccanismo solo laddove necessario e in cui lo sviluppo di un provider di tipi restituisce un valore molto elevato.

È consigliabile evitare di scrivere un provider di tipi in cui uno schema non è disponibile. Analogamente, è consigliabile evitare di scrivere un provider di tipi in cui sarebbe sufficiente una libreria .NET ordinaria (o persino una esistente).

Prima di iniziare, è possibile porre le domande seguenti:

- Si dispone di uno schema per l'origine informazioni? In caso affermativo, qual è il mapping del sistema di tipi F # e .NET?

- È possibile usare un'API esistente (tipizzata in modo dinamico) come punto di partenza per l'implementazione?

- L'utente e l'organizzazione hanno a disposizione un utilizzo sufficiente del provider di tipi per fare in modo che la scrittura valga? Una normale libreria .NET soddisfa le tue esigenze?

- Quanto cambierà lo schema?

- Il cambiamento verrà modificato durante la codifica?

- Cambierà tra le sessioni di codifica?

- Il cambiamento verrà modificato durante l'esecuzione del programma?

I provider di tipi sono ideali per le situazioni in cui lo schema è stabile in fase di esecuzione e durante il ciclo di vita del codice compilato.

## <a name="a-simple-type-provider"></a>Provider di tipi semplici

Questo esempio è Samples. HelloWorldTypeProvider, simile agli esempi nella `examples` directory dell'SDK del [provider di tipi F #](https://github.com/fsprojects/FSharp.TypeProviders.SDK/). Il provider rende disponibile uno "spazio di tipo" che contiene 100 tipi cancellati, come illustrato nel codice seguente usando la sintassi della firma F # e omettendo i dettagli per tutti gli elementi eccetto `Type1` . Per ulteriori informazioni sui tipi cancellati, vedere [Dettagli sui tipi specificati cancellati](#details-about-erased-provided-types) più avanti in questo argomento.

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

Si noti che il set di tipi e membri forniti è stato noto in modo statico. Questo esempio non sfrutta la capacità dei provider di fornire tipi che dipendono da uno schema. L'implementazione del provider di tipi è illustrata nel codice seguente e i dettagli sono descritti nelle sezioni successive di questo argomento.

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

Per usare questo provider, aprire un'istanza separata di Visual Studio, creare uno script F #, quindi aggiungere un riferimento al provider dallo script usando #r come illustrato nel codice seguente:

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

Cercare quindi i tipi nello `Samples.HelloWorldTypeProvider` spazio dei nomi generato dal provider di tipi.

Prima di ricompilare il provider, assicurarsi di avere chiuso tutte le istanze di Visual Studio e F# Interactive che usano la DLL del provider. In caso contrario, si verificherà un errore di compilazione perché la DLL di output sarà bloccata.

Per eseguire il debug di questo provider utilizzando le istruzioni Print, creare uno script che espone un problema con il provider e quindi utilizzare il codice seguente:

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Per eseguire il debug di questo provider con Visual Studio, aprire il Prompt dei comandi per gli sviluppatori per Visual Studio con credenziali amministrative ed eseguire il comando seguente:

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

In alternativa, aprire Visual Studio, aprire il menu debug, scegliere `Debug/Attach to process…` e connettersi a un altro `devenv` processo in cui si sta modificando lo script. Utilizzando questo metodo, è possibile indirizzare più facilmente la logica specifica nel provider di tipi digitando in modo interattivo le espressioni nella seconda istanza (con IntelliSense completo e altre funzionalità).

È possibile disabilitare Just My Code debug per identificare meglio gli errori nel codice generato. Per informazioni su come abilitare o disabilitare questa funzionalità, vedere [esplorazione del codice con il debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger). Inoltre, è possibile impostare l'individuazione delle eccezioni first-chance aprendo il `Debug` menu e scegliendo `Exceptions` o scegliendo i tasti CTRL + ALT + E per aprire la finestra di `Exceptions` dialogo. In tale finestra di dialogo, in `Common Language Runtime Exceptions` selezionare la `Thrown` casella di controllo.

### <a name="implementation-of-the-type-provider"></a>Implementazione del provider di tipi

Questa sezione illustra le sezioni principali dell'implementazione del provider di tipi. In primo luogo, si definisce il tipo per il provider di tipi personalizzato:

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

Questo tipo deve essere pubblico ed è necessario contrassegnarlo con l'attributo [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) in modo che il compilatore riconosca il provider di tipi quando un progetto F # separato fa riferimento all'assembly che contiene il tipo. Il parametro *config* è facoltativo e, se presente, contiene le informazioni di configurazione contestuali per l'istanza del provider di tipi creata dal compilatore F #.

Successivamente, si implementa l'interfaccia [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) . In questo caso, il tipo viene usato `TypeProviderForNamespaces` dall' `ProvidedTypes` API come tipo di base. Questo tipo di helper può fornire una raccolta limitata di spazi dei nomi forniti in modo eager, ognuno dei quali contiene direttamente un numero finito di tipi fissi e con supporto eager. In questo contesto, il provider genera con *entusiasmo* i tipi anche se non sono necessari o usati.

```fsharp
inherit TypeProviderForNamespaces(config)
```

Definire quindi i valori privati locali che specificano lo spazio dei nomi per i tipi forniti e trovare l'assembly del provider di tipi. Questo assembly viene utilizzato in seguito come tipo padre logico dei tipi cancellati forniti.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

Successivamente, creare una funzione per fornire ogni tipo di tipo1... Type100. Questa funzione è illustrata in modo più dettagliato più avanti in questo argomento.

```fsharp
let makeOneProvidedType (n:int) = …
```

Generare quindi i tipi forniti 100:

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

Aggiungere quindi i tipi come uno spazio dei nomi specificato:

```fsharp
do this.AddNamespace(namespaceName, types)
```

Infine, aggiungere un attributo dell'assembly che indichi che si sta creando una DLL del provider di tipi:

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a>Fornire un tipo e i relativi membri

La `makeOneProvidedType` funzione esegue il lavoro effettivo di fornire uno dei tipi.

```fsharp
let makeOneProvidedType (n:int) =
…
```

Questo passaggio illustra l'implementazione di questa funzione. Per prima cosa, creare il tipo specificato (ad esempio, tipo1, quando n = 1, o Type57, quando n = 57).

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

Tenere presente quanto segue:

- Questo tipo specificato è stato cancellato.  Poiché si indica che il tipo di base è `obj` , le istanze verranno visualizzate come valori di tipo [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) nel codice compilato.

- Quando si specifica un tipo non annidato, è necessario specificare l'assembly e lo spazio dei nomi. Per i tipi cancellati, l'assembly deve essere l'assembly del provider di tipi.

Successivamente, aggiungere la documentazione XML al tipo. Questa documentazione viene ritardata, ovvero calcolata su richiesta se il compilatore host lo richiede.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

Aggiungere quindi una proprietà statica specificata al tipo:

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

Il recupero di questa proprietà restituirà sempre la stringa "Hello!". `GetterCode`Per la proprietà viene utilizzata una virgoletta F #, che rappresenta il codice generato dal compilatore host per ottenere la proprietà. Per ulteriori informazioni sulle quotazioni, vedere [citazioni di codice (F #)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).

Aggiungere la documentazione XML alla proprietà.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

A questo punto, alleghi la proprietà specificata al tipo fornito. È necessario alleghi un membro fornito a un solo tipo. In caso contrario, il membro non sarà mai accessibile.

```fsharp
t.AddMember staticProp
```

Creare ora un costruttore fornito che non accetta parametri.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

L'oggetto `InvokeCode` per il costruttore restituisce una quotazione F # che rappresenta il codice generato dal compilatore host quando viene chiamato il costruttore. Ad esempio, è possibile usare il costruttore seguente:

```fsharp
new Type10()
```

Verrà creata un'istanza del tipo fornito con i dati sottostanti "i dati dell'oggetto". Il codice tra virgolette include una conversione in [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) perché tale tipo è la cancellazione di questo tipo specificato (come specificato quando è stato dichiarato il tipo fornito).

Aggiungere la documentazione XML al costruttore e aggiungere il costruttore fornito al tipo fornito:

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

Creare un secondo costruttore fornito che accetti un parametro:

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

L'oggetto `InvokeCode` per il costruttore restituisce nuovamente una quotazione F #, che rappresenta il codice generato dal compilatore host per una chiamata al metodo. Ad esempio, è possibile usare il costruttore seguente:

```fsharp
new Type10("ten")
```

Viene creata un'istanza del tipo fornito con i dati sottostanti "dieci". È possibile che sia già stato notato che la `InvokeCode` funzione restituisce una quotation. L'input per questa funzione è un elenco di espressioni, una per ogni parametro del costruttore. In questo caso, un'espressione che rappresenta il valore del singolo parametro è disponibile in `args.[0]` . Il codice per una chiamata al costruttore assegna il valore restituito al tipo cancellato `obj` . Dopo aver aggiunto il secondo costruttore fornito al tipo, si crea una proprietà di istanza specificata:

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

Ottenendo questa proprietà, viene restituita la lunghezza della stringa, ovvero l'oggetto rappresentazione. La `GetterCode` proprietà restituisce una quotazione F # che specifica il codice generato dal compilatore host per ottenere la proprietà. Analogamente `InvokeCode` a, la `GetterCode` funzione restituisce una quotation. Il compilatore host chiama questa funzione con un elenco di argomenti. In questo caso, gli argomenti includono solo l'espressione singola che rappresenta l'istanza sulla quale viene chiamato il metodo Get, a cui è possibile accedere tramite `args.[0]` . L'implementazione di viene quindi contenuta `GetterCode` nella quotazione dei risultati in corrispondenza del tipo cancellato `obj` e viene utilizzato un cast per soddisfare il meccanismo del compilatore per verificare i tipi che l'oggetto è una stringa. La parte successiva di `makeOneProvidedType` fornisce un metodo di istanza con un parametro.

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

Infine, creare un tipo annidato che contiene 100 proprietà nidificate. La creazione di questo tipo annidato e delle relative proprietà viene ritardata, ovvero calcolata su richiesta.

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

### <a name="details-about-erased-provided-types"></a>Dettagli sui tipi specificati cancellati

Nell'esempio riportato in questa sezione vengono forniti solo i *tipi forniti cancellati*, che risultano particolarmente utili nelle situazioni seguenti:

- Quando si scrive un provider per uno spazio informazioni che contiene solo dati e metodi.

- Quando si scrive un provider in cui la semantica di tipo runtime accurato non è fondamentale per l'uso pratico dello spazio informativo.

- Quando si scrive un provider per uno spazio informativo molto grande e interconnesso, non è tecnicamente possibile generare tipi .NET reali per lo spazio informativo.

In questo esempio, ogni tipo fornito viene cancellato nel tipo `obj` e tutti gli utilizzi del tipo verranno visualizzati come tipo `obj` nel codice compilato. Infatti, gli oggetti sottostanti in questi esempi sono stringhe, ma il tipo verrà visualizzato come `System.Object` nel codice compilato .NET. Come per tutti gli usi della cancellazione dei tipi, è possibile usare la conversione boxing esplicita, unboxing e cast per sovvertire i tipi cancellati. In questo caso, è possibile che venga generata un'eccezione cast non valida quando si usa l'oggetto. Un runtime del provider può definire il proprio tipo di rappresentazione privata per facilitare la protezione da false rappresentazioni. Non è possibile definire i tipi cancellati in F #. Solo i tipi specificati possono essere cancellati. È necessario comprendere le ramificazioni, sia pratiche che semantiche, di usare i tipi cancellati per il provider di tipi o un provider che fornisce tipi cancellati. Un tipo cancellato non ha un tipo .NET reale. Pertanto, non è possibile eseguire una reflection accurata sul tipo ed è possibile sovvertire i tipi cancellati se si usano i cast di runtime e altre tecniche che si basano sulla semantica esatta del tipo di Runtime. La sovversione dei tipi cancellati spesso genera eccezioni di cast di tipo in fase di esecuzione.

### <a name="choosing-representations-for-erased-provided-types"></a>Scelta di rappresentazioni per i tipi specificati cancellati

Per alcuni usi dei tipi specificati cancellati, non è necessaria alcuna rappresentazione. Ad esempio, il tipo fornito cancellato potrebbe contenere solo proprietà statiche e membri e nessun costruttore, né metodi o proprietà restituiscono un'istanza del tipo. Se è possibile raggiungere istanze di un tipo fornito cancellato, è necessario prendere in considerazione le domande seguenti:

**Qual è la cancellazione di un tipo fornito?**

- La cancellazione di un tipo fornito è il modo in cui il tipo viene visualizzato nel codice .NET compilato.

- La cancellazione di un tipo di classe cancellato specificato è sempre il primo tipo di base non cancellato nella catena di ereditarietà del tipo.

- La cancellazione di un tipo di interfaccia cancellato specificato è sempre `System.Object` .

**Quali sono le rappresentazioni di un tipo fornito?**

- Il set di oggetti possibili per un tipo fornito cancellato è denominato rappresentazioni. Nell'esempio di questo documento, le rappresentazioni di tutti i tipi forniti cancellati `Type1..Type100` sono sempre oggetti stringa.

Tutte le rappresentazioni di un tipo fornito devono essere compatibili con la cancellazione del tipo fornito. In caso contrario, il compilatore F # restituirà un errore per l'uso del provider di tipi oppure verrà generato un codice .NET non verificabile che non è valido. Un provider di tipi non è valido se restituisce un codice che fornisce una rappresentazione non valida.

È possibile scegliere una rappresentazione per gli oggetti forniti usando uno degli approcci seguenti, entrambi molto comuni:

- Se si fornisce semplicemente un wrapper fortemente tipizzato su un tipo .NET esistente, è spesso consigliabile cancellare il tipo in tale tipo, utilizzare istanze di quel tipo come rappresentazioni o entrambe. Questo approccio è appropriato quando la maggior parte dei metodi esistenti su quel tipo è ancora utile quando si usa la versione fortemente tipizzata.

- Se si vuole creare un'API che differisce in modo significativo da qualsiasi API .NET esistente, è opportuno creare tipi di runtime che saranno la cancellazione e le rappresentazioni del tipo per i tipi forniti.

Nell'esempio riportato in questo documento vengono utilizzate stringhe come rappresentazioni degli oggetti forniti. Spesso può essere opportuno usare altri oggetti per le rappresentazioni. Ad esempio, è possibile usare un dizionario come contenitore delle proprietà:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

In alternativa, è possibile definire un tipo nel provider di tipi che verrà utilizzato in fase di esecuzione per formare la rappresentazione, insieme a una o più operazioni di runtime:

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

I membri forniti possono quindi creare istanze di questo tipo di oggetto:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

In questo caso, è possibile (facoltativamente) usare questo tipo come cancellazione del tipo specificando questo tipo come `baseType` quando si costruisce l'oggetto `ProvidedTypeDefinition` :

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>Lezioni chiave

Nella sezione precedente è stato illustrato come creare un semplice provider di tipi di cancellazione che fornisce un intervallo di tipi, proprietà e metodi. In questa sezione viene anche illustrato il concetto di cancellazione dei tipi, inclusi alcuni dei vantaggi e degli svantaggi di fornire tipi cancellati da un provider di tipi e le rappresentazioni di tipi cancellati.

## <a name="a-type-provider-that-uses-static-parameters"></a>Provider di tipi che utilizza parametri statici

La possibilità di parametrizzare i provider di tipi in base ai dati statici Abilita molti scenari interessanti, anche nei casi in cui il provider non debba accedere a dati locali o remoti. In questa sezione verranno illustrate alcune tecniche di base per riunire un provider di questo tipo.

### <a name="type-checked-regex-provider"></a>Digitare il provider Regex selezionato

Si supponga di voler implementare un provider di tipi per le espressioni regolari che esegue il wrapping delle <xref:System.Text.RegularExpressions.Regex> librerie .NET in un'interfaccia che fornisce le garanzie della fase di compilazione seguenti:

- Verifica per determinare se un'espressione regolare è valida.

- Fornire proprietà denominate sulle corrispondenze basate su qualsiasi nome di gruppo nell'espressione regolare.

Questa sezione illustra come usare i provider di tipi per creare un `RegexTyped` tipo che il modello di espressione regolare parametrizza per fornire questi vantaggi. Il compilatore segnalerà un errore se il modello fornito non è valido e il provider di tipi può estrarre i gruppi dal modello in modo che sia possibile accedervi usando proprietà denominate sulle corrispondenze. Quando si progetta un provider di tipi, è necessario prendere in considerazione il modo in cui l'API esposta deve esaminare gli utenti finali e il modo in cui questa progettazione verrà convertita nel codice .NET. Nell'esempio seguente viene illustrato come utilizzare tale API per ottenere i componenti del codice area:

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

Nell'esempio seguente viene illustrato il modo in cui il provider di tipi converte queste chiamate:

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

Tenere presente quanto segue:

- Il tipo Regex standard rappresenta il tipo con parametri `RegexTyped` .

- Il `RegexTyped` costruttore genera una chiamata al costruttore Regex, passando l'argomento di tipo statico per il modello.

- I risultati del `Match` metodo sono rappresentati dal tipo standard <xref:System.Text.RegularExpressions.Match> .

- Ogni gruppo denominato restituisce una proprietà fornita e l'accesso alla proprietà comporta l'utilizzo di un indicizzatore in una raccolta di corrispondenze `Groups` .

Il codice seguente è il nucleo della logica per implementare tale provider e in questo esempio viene omessa l'aggiunta di tutti i membri al tipo fornito. Per informazioni su ogni membro aggiunto, vedere la sezione appropriata più avanti in questo argomento. Per il codice completo, scaricare l'esempio dal [pacchetto di esempio F # 3,0](https://archive.codeplex.com/?p=fsharp3sample) sul sito Web CodePlex.

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

- Il provider di tipi accetta due parametri statici: `pattern` , che è obbligatorio, e `options` , che sono facoltativi (poiché viene fornito un valore predefinito).

- Dopo aver fornito gli argomenti statici, creare un'istanza dell'espressione regolare. Questa istanza genererà un'eccezione se l'espressione regolare non è in formato corretto e questo errore verrà segnalato agli utenti.

- All'interno del `DefineStaticParameters` callback, è necessario definire il tipo che verrà restituito dopo che gli argomenti sono stati specificati.

- Questo codice imposta `HideObjectMethods` su true in modo che l'esperienza IntelliSense rimanga semplificata. Questo attributo fa `Equals` `GetHashCode` `Finalize` `GetType` in modo che i membri,, e vengano eliminati dagli elenchi IntelliSense per un oggetto fornito.

- Usare `obj` come tipo di base del metodo, ma si userà un `Regex` oggetto come rappresentazione di runtime di questo tipo, come illustrato nell'esempio successivo.

- La chiamata al `Regex` costruttore genera un'eccezione <xref:System.ArgumentException> quando un'espressione regolare non è valida. Il compilatore rileva questa eccezione e segnala un messaggio di errore all'utente in fase di compilazione o nell'editor di Visual Studio. Questa eccezione consente la convalida delle espressioni regolari senza eseguire un'applicazione.

Il tipo definito sopra non è ancora utile perché non contiene metodi o proprietà significative. Aggiungere prima di tutto un `IsMatch` metodo statico:

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

Il codice precedente definisce un metodo `IsMatch` che accetta una stringa come input e restituisce un oggetto `bool` . L'unica parte complessa è l'uso dell' `args` argomento all'interno della `InvokeCode` definizione. In questo esempio, `args` è un elenco di citazioni che rappresenta gli argomenti di questo metodo. Se il metodo è un metodo di istanza, il primo argomento rappresenta l' `this` argomento. Tuttavia, per un metodo statico, gli argomenti sono solo gli argomenti espliciti del metodo. Si noti che il tipo del valore tra virgolette deve corrispondere al tipo restituito specificato (in questo caso, `bool` ). Si noti inoltre che questo codice usa il `AddXmlDoc` metodo per assicurarsi che il metodo fornito includa anche una documentazione utile, che può essere fornita tramite IntelliSense.

Aggiungere quindi un metodo di corrispondenza dell'istanza. Tuttavia, questo metodo deve restituire un valore di un `Match` tipo specificato in modo che sia possibile accedere ai gruppi in modo fortemente tipizzato. Quindi, si dichiara innanzitutto il `Match` tipo. Poiché questo tipo dipende dal modello fornito come argomento statico, questo tipo deve essere annidato all'interno della definizione del tipo con parametri:

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

Viene quindi aggiunta una proprietà al tipo di corrispondenza per ogni gruppo. In fase di esecuzione, una corrispondenza viene rappresentata come <xref:System.Text.RegularExpressions.Match> valore, quindi la citazione che definisce la proprietà deve utilizzare la <xref:System.Text.RegularExpressions.Match.Groups> proprietà indicizzata per ottenere il gruppo pertinente.

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

Si noti anche che si sta aggiungendo la documentazione XML alla proprietà specificata. Si noti inoltre che una proprietà può essere letta se `GetterCode` viene fornita una funzione e la proprietà può essere scritta se `SetterCode` viene fornita una funzione, quindi la proprietà risultante è di sola lettura.

A questo punto è possibile creare un metodo di istanza che restituisce un valore di questo `Match` tipo:

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

Poiché si sta creando un metodo di istanza, `args.[0]` rappresenta l' `RegexTyped` istanza sulla quale viene chiamato il metodo e `args.[1]` è l'argomento di input.

Infine, fornire un costruttore in modo che sia possibile creare istanze del tipo fornito.

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

Il costruttore cancella semplicemente la creazione di un'istanza di Regex .NET standard, che viene nuovamente sottoposti a Boxing in un oggetto perché `obj` è la cancellazione del tipo fornito. Con questa modifica, l'utilizzo dell'API di esempio specificato in precedenza nell'argomento funziona come previsto. Il codice seguente è completo e finale:

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

In questa sezione è stato illustrato come creare un provider di tipi che opera sui parametri statici. Il provider controlla il parametro statico e fornisce operazioni in base al relativo valore.

## <a name="a-type-provider-that-is-backed-by-local-data"></a>Provider di tipi supportato da dati locali

Spesso è consigliabile che i provider di tipi presentino API basate solo su parametri statici, ma anche su informazioni provenienti da sistemi locali o remoti. In questa sezione vengono illustrati i provider di tipi basati su dati locali, ad esempio i file di dati locali.

### <a name="simple-csv-file-provider"></a>Provider di file CSV semplice

Come esempio semplice, si consideri un provider di tipi per l'accesso ai dati scientifici nel formato con valori delimitati da virgole (CSV). In questa sezione si presuppone che i file CSV contengano una riga di intestazione seguita da dati a virgola mobile, come illustrato nella tabella seguente:

|Distanza (contatore)|Ora (secondo)|
|----------------|-------------|
|50.0|3.7|
|100.0|5,2|
|150.0|6.4|

In questa sezione viene illustrato come fornire un tipo che è possibile utilizzare per ottenere le righe con una `Distance` proprietà di tipo `float<meter>` e una `Time` proprietà di tipo `float<second>` . Per semplicità, vengono eseguiti i presupposti seguenti:

- I nomi di intestazione sono senza unità o hanno il formato "nome (unità)" e non contengono virgole.

- Le unità sono tutte unità di sistema internazionale (SI) come definito dal modulo [Microsoft. FSharp. Data. UnitSystems. si. UnitNames (F #)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) .

- Le unità sono tutte semplici (ad esempio, il contatore) invece del composto (ad esempio, il contatore/secondo).

- Tutte le colonne contengono dati a virgola mobile.

Un provider più completo potrebbe allentare queste restrizioni.

Anche in questo caso, il primo passaggio consiste nel considerare l'aspetto dell'API. Dato un file `info.csv` con i contenuti della tabella precedente (nel formato delimitato da virgole), gli utenti del provider possono scrivere codice simile all'esempio seguente:

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

In questo caso, il compilatore deve convertire queste chiamate in qualcosa di simile all'esempio seguente:

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

La conversione ottimale richiederà al provider di tipi di definire un `CsvFile` tipo reale nell'assembly del provider di tipi. I provider di tipi spesso si basano su alcuni tipi di helper e metodi per eseguire il wrapping di logica importante. Poiché le misure vengono cancellate in fase di esecuzione, è possibile usare `float[]` come tipo cancellato per una riga. Il compilatore considererà colonne diverse con tipi di misure diversi. Ad esempio, la prima colonna dell'esempio è di tipo `float<meter>` , mentre la seconda è `float<second>` . Tuttavia, la rappresentazione cancellata può rimanere piuttosto semplice.

Il codice seguente illustra il nucleo dell'implementazione.

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

Si notino i seguenti punti sull'implementazione:

- I costruttori di overload consentono di leggere il file originale o uno con lo stesso schema. Questo modello è comune quando si scrive un provider di tipi per le origini dati locali o remote e questo modello consente di usare un file locale come modello per i dati remoti.

- È possibile usare il valore [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) passato al costruttore del provider di tipi per risolvere i nomi di file relativi.

- È possibile utilizzare il `AddDefinitionLocation` metodo per definire il percorso delle proprietà specificate. Se pertanto si utilizza `Go To Definition` in una proprietà fornita, il file CSV viene aperto in Visual Studio.

- È possibile usare il `ProvidedMeasureBuilder` tipo per cercare le unità di misura e per generare i `float<_>` tipi pertinenti.

### <a name="key-lessons"></a>Lezioni chiave

In questa sezione è stato illustrato come creare un provider di tipi per un'origine dati locale con uno schema semplice contenuto nell'origine dati stessa.

## <a name="going-further"></a>Approfondimenti

Le sezioni seguenti includono suggerimenti per un'ulteriore analisi.

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>Esaminare il codice compilato per i tipi cancellati

Per avere un'idea di come l'uso del provider di tipi corrisponda al codice emesso, esaminare la funzione seguente usando l'oggetto `HelloWorldTypeProvider` usato in precedenza in questo argomento.

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

Ecco un'immagine del codice risultante decompilato usando Ildasm. exe:

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

Come illustrato nell'esempio, tutte le menzioni del tipo `Type1` e della `InstanceProperty` proprietà sono state cancellate, lasciando solo le operazioni sui tipi di runtime necessari.

### <a name="design-and-naming-conventions-for-type-providers"></a>Convenzioni di progettazione e denominazione per i provider di tipi

Quando si creano provider di tipi, osservare le convenzioni seguenti.

**Provider per i protocolli di connettività** In generale, i nomi della maggior parte delle dll del provider per i protocolli di connettività di dati e servizi, ad esempio le connessioni OData o SQL, devono terminare con `TypeProvider` o `TypeProviders` . Usare, ad esempio, un nome di DLL simile alla stringa seguente:

`Fabrikam.Management.BasicTypeProviders.dll`

Verificare che i tipi forniti siano membri dello spazio dei nomi corrispondente e indicare il protocollo di connettività implementato:

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**Provider di utilità per la codifica generale**.  Per un provider del tipo di utilità, ad esempio per le espressioni regolari, il provider di tipi può fare parte di una libreria di base, come illustrato nell'esempio seguente:

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

In questo caso, il tipo fornito viene visualizzato in un punto appropriato secondo le normali convenzioni di progettazione .NET:

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

**Origini dati singleton**. Alcuni provider di tipi si connettono a una singola origine dati dedicata e forniscono solo i dati. In questo caso, è necessario eliminare il `TypeProvider` suffisso e usare le convenzioni normali per la denominazione .NET:

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

Per ulteriori informazioni, vedere la `GetConnection` convenzione di progettazione descritta più avanti in questo argomento.

### <a name="design-patterns-for-type-providers"></a>Modelli di progettazione per i provider di tipi

Le sezioni seguenti descrivono i modelli di progettazione che è possibile usare per la creazione di provider di tipi.

#### <a name="the-getconnection-design-pattern"></a>Modello di Progettazione GetConnection

La maggior parte dei provider di tipi deve essere scritta in modo da usare il `GetConnection` modello usato dai provider di tipi in FSharp. Data. TypeProviders. dll, come illustrato nell'esempio seguente:

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>Provider di tipi supportati da servizi e dati remoti

Prima di creare un provider di tipi supportato da servizi e dati remoti, è necessario considerare una serie di problemi inerenti alla programmazione connessa. Questi problemi includono le considerazioni seguenti:

- mapping dello schema

- Livezza e invalidamento in presenza di modifiche dello schema

- Caching dello schema

- implementazioni asincrone di operazioni di accesso ai dati

- supporto delle query, incluse le query LINQ

- credenziali e autenticazione

Questo argomento non Esplora ulteriormente questi problemi.

### <a name="additional-authoring-techniques"></a>Tecniche di creazione aggiuntive

Quando si scrivono provider di tipi personalizzati, è consigliabile usare le tecniche aggiuntive seguenti.

### <a name="creating-types-and-members-on-demand"></a>Creazione di tipi e membri su richiesta

L'API ProvidedType ha versioni ritardate di AddMember.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

Queste versioni vengono usate per creare spazi su richiesta di tipi.

### <a name="providing-array-types-and-generic-type-instantiations"></a>Fornire tipi di matrici e creazioni di istanze di tipi generici

I membri forniti, le cui firme includono i tipi di matrice, i tipi ByRef e le creazioni di istanze di tipi generici, usano i normali `MakeArrayType` , `MakePointerType` e `MakeGenericType` in qualsiasi istanza di <xref:System.Type> , incluso `ProvidedTypeDefinitions` .

> [!NOTE]
> In alcuni casi potrebbe essere necessario utilizzare l'helper in `ProvidedTypeBuilder.MakeGenericType` .  Per altri dettagli, vedere la [documentazione relativa all'SDK del provider di tipi](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) .

### <a name="providing-unit-of-measure-annotations"></a>Specifica di un'unità di annotazioni di misura

L'API ProvidedTypes fornisce helper per fornire annotazioni di misura. Per fornire il tipo, ad esempio `float<kg>` , usare il codice seguente:

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  Per fornire il tipo `Nullable<decimal<kg/m^2>>` , usare il codice seguente:

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>Accesso alle risorse locali del progetto o dello script

A ogni istanza di un provider di tipi può essere assegnato un `TypeProviderConfig` valore durante la costruzione. Questo valore contiene la "cartella di risoluzione" per il provider, ovvero la cartella di progetto per la compilazione o la directory che contiene uno script, l'elenco degli assembly a cui si fa riferimento e altre informazioni.

### <a name="invalidation"></a>Invalidamento

I provider possono generare segnali di invalidazione per notificare al servizio del linguaggio F # che è possibile che si siano modificati i presupposti dello schema. Quando si verifica l'invalidamento, viene eseguito il riesecuzione di un typecheck se il provider è ospitato in Visual Studio. Questo segnale verrà ignorato quando il provider è ospitato in F# Interactive o dal compilatore F # (FSC. exe).

### <a name="caching-schema-information"></a>Memorizzazione nella cache delle informazioni sullo schema

I provider devono spesso memorizzare nella cache l'accesso alle informazioni dello schema. I dati memorizzati nella cache devono essere archiviati usando un nome file specificato come parametro statico o come dati utente. Un esempio di memorizzazione nella cache degli schemi è il `LocalSchemaFile` parametro nei provider di tipi nell' `FSharp.Data.TypeProviders` assembly. Nell'implementazione di questi provider, questo parametro statico indica al provider di tipi di utilizzare le informazioni sullo schema nel file locale specificato anziché accedere all'origine dati tramite la rete. Per utilizzare le informazioni dello schema memorizzate nella cache, è necessario impostare anche il parametro statico `ForceUpdate` su `false` . È possibile usare una tecnica simile per abilitare l'accesso ai dati online e offline.

### <a name="backing-assembly"></a>Assembly di backup

Quando si compila un `.dll` `.exe` file o, il file dll sottostante per i tipi generati viene collegato in modo statico nell'assembly risultante. Questo collegamento viene creato copiando le definizioni del tipo Intermediate Language (IL) e tutte le risorse gestite dall'assembly di supporto nell'assembly finale. Quando si usa F# Interactive, il file con estensione dll di backup non viene copiato e viene invece caricato direttamente nel processo di F# Interactive.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>Eccezioni e diagnostica dai provider di tipi

Tutti gli utilizzi di tutti i membri dei tipi specificati possono generare eccezioni. In tutti i casi, se un provider di tipi genera un'eccezione, il compilatore host attribuisce l'errore a un provider di tipi specifico.

- Le eccezioni del provider di tipi non devono mai causare errori interni del compilatore.

- I provider di tipi non possono segnalare avvisi.

- Quando un provider di tipi è ospitato nel compilatore F #, in un ambiente di sviluppo F # o F# Interactive vengono rilevate tutte le eccezioni del provider. La proprietà Message è sempre il testo dell'errore e non viene visualizzata alcuna traccia dello stack. Se si sta per generare un'eccezione, è possibile generare gli esempi seguenti: `System.NotSupportedException` , `System.IO.IOException` , `System.Exception` .

#### <a name="providing-generated-types"></a>Fornire tipi generati

Fino a questo punto, questo documento ha illustrato come fornire tipi cancellati. È anche possibile usare il meccanismo del provider di tipi in F # per fornire i tipi generati, che vengono aggiunti come definizioni di tipo .NET reali al programma degli utenti. È necessario fare riferimento ai tipi forniti generati utilizzando una definizione di tipo.

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

Il codice helper ProvidedTypes-0,2 che fa parte della versione F # 3,0 ha solo un supporto limitato per la fornitura di tipi generati. Per una definizione di tipo generata è necessario che siano soddisfatte le istruzioni seguenti:

- `isErased` deve essere impostato su `false`.

- Il tipo generato deve essere aggiunto a un oggetto appena costruito `ProvidedAssembly()` , che rappresenta un contenitore per i frammenti di codice generati.

- Il provider deve disporre di un assembly con un file con estensione dll .NET che esegue il backup con un file dll corrispondente su disco.

## <a name="rules-and-limitations"></a>Regole e limitazioni

Quando si scrivono provider di tipi, tenere presenti le regole e le limitazioni seguenti.

### <a name="provided-types-must-be-reachable"></a>I tipi specificati devono essere raggiungibili

Tutti i tipi forniti devono essere raggiungibili dai tipi non annidati. I tipi non annidati sono specificati nella chiamata al `TypeProviderForNamespaces` costruttore o a una chiamata a `AddNamespace` . Se, ad esempio, il provider fornisce un tipo `StaticClass.P : T` , è necessario assicurarsi che T sia un tipo non annidato o annidato sotto uno.

Alcuni provider, ad esempio, hanno una classe statica, ad esempio, `DataTypes` che contengono questi `T1, T2, T3, ...` tipi. In caso contrario, l'errore indica che è stato trovato un riferimento al tipo T nell'assembly A, ma non è stato possibile trovare il tipo nell'assembly. Se viene visualizzato questo errore, verificare che tutti i sottotipi possano essere raggiunti dai tipi di provider. Nota: questi `T1, T2, T3...` tipi sono definiti tipi in tempo *reale* . Ricordarsi di inserirli in uno spazio dei nomi accessibile o in un tipo padre.

### <a name="limitations-of-the-type-provider-mechanism"></a>Limitazioni del meccanismo del provider di tipi

Il meccanismo del provider di tipi in F # presenta le limitazioni seguenti:

- L'infrastruttura sottostante per i provider di tipi in F # non supporta i tipi generici forniti o i metodi generici forniti.

- Il meccanismo non supporta i tipi annidati con parametri statici.

## <a name="development-tips"></a>Suggerimenti per lo sviluppo

I suggerimenti seguenti potrebbero risultare utili durante il processo di sviluppo:

### <a name="run-two-instances-of-visual-studio"></a>Eseguire due istanze di Visual Studio

È possibile sviluppare il provider di tipi in un'istanza e testare il provider nell'altro perché l'IDE di test accetterà un blocco sul file con estensione dll che impedisce la ricompilazione del provider di tipi. Pertanto, è necessario chiudere la seconda istanza di Visual Studio mentre il provider viene compilato nella prima istanza, quindi è necessario riaprire la seconda istanza dopo la compilazione del provider.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>Eseguire il debug di provider di tipi usando le chiamate di FSC. exe

È possibile richiamare i provider di tipi utilizzando gli strumenti seguenti:

- FSC. exe (compilatore della riga di comando F #)

- FSI. exe (compilatore F# Interactive)

- devenv. exe (Visual Studio)

Spesso è possibile eseguire il debug dei provider di tipi usando FSC. exe in un file script di test, ad esempio script. FSX. È possibile avviare un debugger da un prompt dei comandi.

```console
devenv /debugexe fsc.exe script.fsx
```

  È possibile usare la registrazione da stampa a stdout.

## <a name="see-also"></a>Vedere anche

- [Provider di tipi](index.md)
- [SDK del provider di tipi](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
