---
title: 'Esercitazione: Creare un Provider di tipi (F #)'
description: 'Informazioni su come creare il proprio provider di tipi F # in F # 3.0 esaminando i diversi provider di tipo semplice per illustrare i concetti di base.'
ms.date: 05/16/2016
ms.openlocfilehash: 3c998377b2c3a408d536ef416f3799bf7f04b6bd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44212321"
---
# <a name="tutorial-create-a-type-provider"></a>Esercitazione: Creare un Provider di tipi

Il meccanismo di provider in F # è una parte significativa del supporto per la programmazione avanzata di informazioni. Questa esercitazione illustra come creare il proprio provider di tipi attraverso lo sviluppo di diversi provider di tipo semplice per illustrare i concetti di base. Per altre informazioni sul meccanismo di provider di tipo in F #, vedere [provider di tipi](index.md).

L'ecosistema di F # contiene una gamma di provider di tipi per uso comune Internet e enterprise data services. Ad esempio:

- [FSharp](https://fsharp.github.io/FSharp.Data/) include il provider di tipi per formati di documenti JSON, XML, CSV e HTML.

- [SQLProvider](https://fsprojects.github.io/SQLProvider/) fornisce accesso fortemente tipizzato ai database SQL tramite un mapping degli oggetti e LINQ F # le query su tali origini dati.

- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) dispone di un set di provider di tipi per la fase di compilazione selezionata incorporamento di T-SQL in F #.

- [Typeproviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) è un precedente set di provider di tipi per l'uso solo con la programmazione di .NET Framework per l'accesso ai servizi di dati SQL, Entity Framework, OData e WSDL.

Se necessario, è possibile creare provider di tipi personalizzati, oppure è possibile fare riferimento a provider di tipi creati da altri. Ad esempio, l'organizzazione potrebbe avere un servizio dati che fornisce un numero elevato e continuamente crescente di set di dati denominati, ciascuno con il proprio schema dati stabile. È possibile creare un provider di tipi che legge gli schemi e presenta i set di dati correnti per il programmatore in una modalità fortemente tipizzata.

## <a name="before-you-start"></a>Prima di iniziare

Il meccanismo di provider è progettato principalmente per l'inserimento di dati stabili e spazi di informazioni del servizio nell'esperienza di programmazione F #.

Questo meccanismo non è progettato per l'inserimento di spazi di informazioni cui lo schema cambia durante l'esecuzione del programma in modi che sono rilevanti per la logica del programma. Inoltre, il meccanismo non è progettato per intra-language metaprogrammazione, anche se tale dominio contiene alcuni utilizzi validi. È consigliabile usare questo meccanismo solo laddove necessario e in cui lo sviluppo di un provider di tipi produce un valore molto elevato.

È consigliabile evitare la scrittura di un provider di tipi in uno schema non è disponibile. Analogamente, è consigliabile evitare la scrittura di un provider di tipi in cui un normale (o persino esistente) basterebbe libreria .NET.

Prima di iniziare, si potrebbero chiedere alle domande seguenti:

- Si hanno uno schema per l'origine di informazioni? In questo caso, qual è il mapping a F # e sistema di tipi .NET?

- È possibile utilizzare un'API (tipizzata in modo dinamico) esistente come punto di partenza per l'implementazione?

- E l'organizzazione avrà sufficiente utilizzi del provider del tipo per rendere la scrittura possono essere utili? Sarebbe una libreria.NET normale soddisfa le proprie esigenze?

- Quanto verrà modificato lo schema?

- Verrà modificato durante la scrittura di codice?

- Verrà modificato tra le sessioni di codifica?

- Verrà modificato durante l'esecuzione del programma?

Provider di tipi sono particolarmente adatti alle situazioni in cui lo schema è stabile in fase di esecuzione e nel corso della durata del codice compilato.

## <a name="a-simple-type-provider"></a>Un Provider di tipi semplici

Questo esempio è Samples. helloworldtypeprovider, simili agli esempi nel `examples` directory del [F # tipo Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/). Il provider rende disponibile un "spazio di tipo" che contiene 100 tipi cancellati, come illustrato nel codice seguente utilizzando sintassi della firma F # e omettendo i dettagli per tutti tranne `Type1`. Per altre informazioni sui tipi cancellati, vedere [informazioni dettagliate sulle cancellati forniti tipi](#details-about-erased-provided-types) più avanti in questo argomento.

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

Si noti che il set di tipi e membri forniti sia noto staticamente. In questo esempio non sfrutta la possibilità di provider forniscono i tipi che dipendono da uno schema. Nel codice seguente viene descritta l'implementazione del provider del tipo e i dettagli sono descritti nelle sezioni successive di questo argomento.

>[!WARNING]
Possono essere presenti differenze tra il codice e gli esempi online.

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

Per usare questo provider, aprire un'istanza separata di Visual Studio, creare uno script F # e quindi aggiungere un riferimento al provider dallo script utilizzando #r come illustrato nel codice seguente:

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

Cercare quindi i tipi nel `Samples.HelloWorldTypeProvider` dello spazio dei nomi che ha generato il provider di tipi.

Prima di ricompilare il provider, assicurarsi che siano state chiuse tutte le istanze di Visual Studio e F # Interactive che usano la DLL del provider. In caso contrario, viene visualizzato un errore di compilazione perché l'output DLL verrà bloccata.

Per eseguire il debug di questo provider con istruzioni print, creare script che espone un problema con il provider e quindi usare il codice seguente:

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Per eseguire il debug di questo provider con Visual Studio, aprire il prompt dei comandi di Visual Studio con credenziali amministrative ed eseguire il comando seguente:

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

In alternativa, aprire Visual Studio, aprire il menu di Debug, scegli `Debug/Attach to process…`e associare a un altro `devenv` processo in cui si sta modificando lo script. Con questo metodo, è possibile assegnare più facilmente particolare per la logica nel provider di tipi, in modo interattivo digitando le espressioni nella seconda istanza (con funzionalità complete di IntelliSense e altre funzionalità).

È possibile disabilitare Just My Code per identificare più facilmente gli errori nel codice generato del debug. Per informazioni su come abilitare o disabilitare questa funzionalità, vedere [spostarsi nel codice con il Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger). Inoltre, è anche possibile impostare le eccezioni first-chance rilevamento, aprire il `Debug` menu e scegliendo `Exceptions` oppure scegliendo i tasti Ctrl + Alt + E aprire il `Exceptions` nella finestra di dialogo. Nella finestra di dialogo, sotto `Common Language Runtime Exceptions`, selezionare il `Thrown` casella di controllo.

### <a name="implementation-of-the-type-provider"></a>Implementazione del Provider di tipo

In questa sezione illustra le sezioni principali dell'implementazione del provider di tipo. È in primo luogo, definire il tipo per il provider di tipi personalizzato se stessa:

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

Questo tipo deve essere pubblico ed è necessario contrassegnarla con il [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) in modo che il compilatore riconoscerà il provider di tipi quando un progetto F # separato fa riferimento all'assembly che contiene il tipo di attributo. Il *config* parametro è facoltativo e, se presente, contiene le informazioni di configurazione di scelta rapida per l'istanza del provider di tipi che consente di creare il compilatore F #.

Successivamente, si implementa il [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interfaccia. In questo caso, si utilizza il `TypeProviderForNamespaces` digitare dal `ProvidedTypes` API come tipo di base. Questo tipo di helper può indicare una raccolta finita di accuratamente fornita spazi dei nomi, ognuno dei quali direttamente contiene un numero finito di correzione, accuratamente i tipi forniti. In questo contesto, il provider *accuratamente* genera tipi anche se essi non sono necessari o usati.

```fsharp
inherit TypeProviderForNamespaces(config)
```

Successivamente, definire i valori privati locali che specificano lo spazio dei nomi per i tipi specificati e trovare l'assembly di provider di tipo stesso. Questo assembly viene usato in un secondo momento come il tipo di elemento padre logico dei tipi cancellati forniti.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

Successivamente, creare una funzione per specificare ognuno dei tipi Type1... Type100. Questa funzione è illustrata più dettagliatamente più avanti in questo argomento.

```fsharp
let makeOneProvidedType (n:int) = …
```

Generare quindi i tipi specificati 100:

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

Successivamente, aggiungere i tipi come uno spazio dei nomi specificato:

```fsharp
do this.AddNamespace(namespaceName, types)
```

Aggiungere infine un attributo dell'assembly che indica che si sta creando una DLL del provider di tipo:

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a>Che fornisce un tipo e i relativi membri

Il `makeOneProvidedType` funzione esegue il lavoro effettivo di fornire uno dei tipi.

```fsharp
let makeOneProvidedType (n:int) = 
…
```

Questo passaggio spiega l'implementazione di questa funzione. Creare innanzitutto il tipo fornito (ad esempio, Type1, quando n = 1 o Type57, quando n = 57).

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

Si noti quanto riportato di seguito:

- Queste informazioni specificate tipo verrà cancellato.  Poiché si indica che è il tipo di base `obj`, le istanze verranno visualizzati come valori di tipo [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) nel codice compilato.

- Quando si specifica un tipo non annidato, è necessario specificare l'assembly e dello spazio dei nomi. Per i tipi cancellati, l'assembly deve essere l'assembly di provider di tipo stesso.

Aggiungere quindi la documentazione XML per il tipo. Questa documentazione viene ritardato, vale a dire, calcolate su richiesta se ne ha bisogno il compilatore host.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

Aggiungere una proprietà statica fornita al tipo:

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
                                  propertyType = typeof<string>, 
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

Ottiene questa proprietà restituisce sempre la stringa "Hello!". Il `GetterCode` per la proprietà viene utilizzata una quotation F #, che rappresenta il codice che genera il compilatore host per il recupero della proprietà. Per altre informazioni sulle offerte, vedere [citazioni di codice (F #)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).

Aggiungere la documentazione XML per la proprietà.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

Ora è possibile associare proprietà fornita per il tipo specificato. È necessario associare un membro specificato in un unico tipo. In caso contrario, il membro non potranno mai essere accessibile.

```fsharp
t.AddMember staticProp
```

Creare ora un costruttore specificato che non accetta parametri.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

Il `InvokeCode` per il costruttore restituisce un quotation F #, che rappresenta il codice che il compilatore host genera l'errore quando viene chiamato il costruttore. Ad esempio, è possibile usare il costruttore seguente:

```fsharp
new Type10()
```

Verrà creata un'istanza del tipo fornito con i dati sottostanti "I dati dell'oggetto". Il codice tra virgolette include una conversione [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) perché tale tipo è la cancellazione di questo fornito di tipo (come specificato quando è dichiarato il tipo specificato).

Aggiungere la documentazione XML per il costruttore e aggiungere il costruttore fornito per il tipo specificato:

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

Creare un secondo costruttore specificato che accetta un parametro:

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

Il `InvokeCode` per il costruttore restituisce nuovamente una quotation F #, che rappresenta il codice che ha generato il compilatore host per una chiamata al metodo. Ad esempio, è possibile usare il costruttore seguente:

```fsharp
new Type10("ten")
```

Viene creata un'istanza del tipo fornito con i dati sottostanti "10". Si è già notato che la `InvokeCode` funzione restituisce una citazione. L'input a questa funzione è un elenco di espressioni, uno per ogni parametro del costruttore. In questo caso, è disponibile in un'espressione che rappresenta il valore del parametro singolo `args.[0]`. Il codice per una chiamata al costruttore assegna il valore restituito nel tipo cancellato `obj`. Dopo aver aggiunto il secondo costruttore fornito al tipo, si crea una proprietà di istanza fornita:

```fsharp
let instanceProp = 
    ProvidedProperty(propertyName = "InstanceProperty", 
                     propertyType = typeof<int>, 
                     getterCode= (fun args -> 
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

Ottiene questa proprietà verrà restituita la lunghezza della stringa, ovvero l'oggetto di rappresentazione. Il `GetterCode` proprietà restituisce una quotation F # che specifica il codice per ottenere la proprietà generata dal compilatore host. Ad esempio `InvokeCode`, il `GetterCode` funzione restituisce una citazione. Il compilatore host chiama questa funzione con un elenco di argomenti. In questo caso, gli argomenti includono solo la singola espressione che rappresenta l'istanza sulla quale viene chiamato il metodo Get, che è possibile accedere usando `args.[0]`. L'implementazione di `GetterCode` quindi sottopone a splicing nell'offerta di risultato in corrispondenza del tipo cancellato `obj`, e viene utilizzato un cast per soddisfare il meccanismo del compilatore per il controllo dei tipi che l'oggetto è una stringa. La parte successiva della `makeOneProvidedType` fornisce un metodo di istanza con un parametro.

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

Infine, creare un tipo annidato che contiene 100 proprietà annidate. La creazione di questo tipo e le relative proprietà annidati viene ritardato, vale a dire, calcolate su richiesta.

```fsharp
t.AddMembersDelayed(fun () -> 
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () -> 
    let staticPropsInNestedType = 
      [ for i in 1 .. 100 do
          let valueOfTheProperty = "I am string "  + string i

          let p = 
            ProvidedProperty(propertyName = "StaticProperty" + string i, 
              propertyType = typeof<string>, 
              isStatic = true,
              getterCode= (fun args -> <@@ valueOfTheProperty @@>))

          p.AddXmlDocDelayed(fun () -> 
              sprintf "This is StaticProperty%d on NestedType" i)

          yield p ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a>Informazioni dettagliate sui tipi forniti cancellati

L'esempio in questa sezione vengono fornite solo *cancellati tipi specificati*, che sono particolarmente utili nelle situazioni seguenti:

- Quando si scrive un provider per uno spazio di informazioni che contiene solo i dati e metodi.

- Quando si scrive un provider in cui una semantica tipo-runtime accurate non è critica per l'uso pratico dello spazio di informazioni.

- Quando si scrive un provider per uno spazio di informazioni che è così grande e interconnessi che non è tecnicamente possibile per generare i tipi .NET reali per lo spazio di informazioni.

In questo esempio, ogni fornito di tipo verrà cancellato al tipo `obj`, e tutti gli usi del tipo verranno visualizzato come tipo `obj` nel codice compilato. In effetti, gli oggetti sottostanti in questi esempi sono stringhe, ma il tipo verrà visualizzato come `System.Object` in .NET codice compilato. Come con tutti gli usi di cancellazione di tipo, è possibile usare la conversione boxing esplicito, conversione unboxing ed eseguendo il cast a compromettere cancellati i tipi. In questo caso, un'eccezione di cast non valida potrebbe quando l'oggetto viene usato. Un provider runtime è possibile definire un proprio tipo di rappresentazione privata per proteggersi da rappresentazioni false. Non è possibile definire i tipi cancellati in F # se stesso. Solo i tipi specificati possono essere cancellati. È necessario comprendere le ramificazioni, entrambi pratici e semantici, di usare uno tipi cancellati per il provider di tipo o un provider che fornisce cancellati tipi. Un tipo cancellato non dispone di alcun tipo .NET reale. Pertanto, non è possibile eseguire sul tipo di reflection accurata e si potrebbero compromettere i tipi cancellati se si usano i cast di runtime e altre tecniche che si basano sulla semantica del tipo esatto di runtime. Subversion dei tipi cancellati spesso comporta eccezioni di cast di tipo in fase di esecuzione.

### <a name="choosing-representations-for-erased-provided-types"></a>Scelta di rappresentazioni per cancellare i tipi forniti

Per alcuni casi di utilizzo dei tipi forniti cancellati, non è necessaria alcuna rappresentazione. Ad esempio, è il cancellato fornito tipo potrebbe contenere solo le proprietà statiche e membri e alcun costruttore, e nessuna proprietà o metodi restituisce un'istanza del tipo. Se è possibile raggiungere le istanze di un cancellato fornito di tipo, è necessario considerare le domande seguenti:

**Che cos'è la cancellazione di un tipo fornito?**

- La cancellazione di un tipo fornito è come il tipo viene visualizzato nel codice .NET compilato.

- La cancellazione di un tipo di classe cancellato fornita è sempre il primo non cancellati tipo di base nella catena di ereditarietà del tipo.

- La cancellazione di un tipo di interfaccia cancellato fornita è sempre `System.Object`.

**Quali sono le rappresentazioni di un tipo fornito?**

- Il set di oggetti possibili per un tipo fornito cancellati vengono chiamati relative rappresentazioni. Nell'esempio in questo documento, le rappresentazioni di tutti il cancellato fornito tipi `Type1..Type100` sono sempre oggetti stringa.

Tutte le rappresentazioni di un tipo fornito devono essere compatibile con la cancellazione del tipo fornito. (In caso contrario, il compilatore F # genererà un errore per un utilizzo del provider del tipo, o verrà generato codice .NET non verificabile che non è valido. Un provider di tipi non è valido se restituisce un codice che fornisce una rappresentazione non valida.

È possibile scegliere una rappresentazione per gli oggetti forniti utilizzando uno degli approcci seguenti, che sono molto comuni:

- Se si forniscono un wrapper fortemente tipizzato semplicemente su un tipo .NET esistente, è spesso opportuno per il tipo cancellare a quel tipo, usare le istanze di tale tipo come rappresentazioni o entrambi. Questo approccio è appropriato quando la maggior parte dei metodi esistenti su tale tipo siano comunque valide quando si usa la versione fortemente tipizzata.

- Se si desidera creare un'API che differisce significativamente da tutte API .NET esistente, è opportuno creare i tipi di runtime che saranno la cancellazione di tipo e rappresentazioni per i tipi specificati.

L'esempio in questo documento usa le stringhe come rappresentazioni di oggetti specificati. Spesso, potrebbe essere opportuno usare altri oggetti per le rappresentazioni. Ad esempio, è possibile utilizzare un dizionario come un contenitore di proprietà:

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

In alternativa, è possibile definire un tipo nel provider di tipo che verrà usato in fase di esecuzione per formare la rappresentazione, insieme a uno o più operazioni di runtime:

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

I membri specificati possono quindi costruire le istanze di questo tipo di oggetto:

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

In questo caso, si potrebbe (facoltativamente) usare questo tipo come la cancellazione di tipo specificando questo tipo come le `baseType` durante la costruzione di `ProvidedTypeDefinition`:

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>Lezioni principali

La sezione precedente è stato spiegato come creare un provider di tipi cancellazione semplice che offre una gamma di tipi, proprietà e metodi. In questa sezione viene inoltre illustrato il concetto di cancellazione di tipo, tra cui alcuni dei vantaggi e svantaggi di fornire i tipi cancellati da un provider di tipi e illustrate rappresentazioni di tipi cancellati.

## <a name="a-type-provider-that-uses-static-parameters"></a>Un Provider di tipi che utilizza parametri statici

La possibilità di impostare i parametri provider di tipi da dati statici consente molti scenari interessanti, anche in casi in cui il provider non è necessario accedere ai dati locali o remoti. In questa sezione si apprenderà alcune tecniche di base per la creazione di un provider di questo tipo.

### <a name="type-checked-regex-provider"></a>Tipo controllato Provider Regex

Si supponga che si desidera implementare un provider di tipi per le espressioni regolari che esegue il wrapping di .NET <xref:System.Text.RegularExpressions.Regex> librerie in un'interfaccia che fornisce le seguenti garanzie in fase di compilazione:

- Verifica se un'espressione regolare è valida.

- Fornendo proprietà denominate corrispondenze basate su tutti i nomi dei gruppi nell'espressione regolare.

Questa sezione illustra come usare i provider di tipi per creare un `RegexTyped` digitare che Parametrizza il criterio di espressione regolare per fornire tali vantaggi. Il compilatore segnalerà un errore se il modello fornito non è valido e il provider di tipi può estrarre i gruppi nel criterio in modo che è possibile accedervi usando le proprietà sulle corrispondenze denominate. Quando si progetta un provider di tipi, è necessario considerare come dovrebbe apparire relative API esposta agli utenti finali e modo in cui questo progetto verrà convertito in codice .NET. Nell'esempio seguente viene illustrato come utilizzare questo tipo di API per ottenere i componenti del codice area:

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

Nell'esempio seguente viene illustrato come il provider di tipi converte queste chiamate:

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

Tenere presente quanto segue:

- Il tipo di espressione regolare standard rappresenta i parametri `RegexTyped` tipo.

- Il `RegexTyped` costruttore comporta una chiamata al costruttore di espressioni regolari, passando l'argomento di tipo statico per il modello.

- I risultati del `Match` metodo sono rappresentati dallo standard <xref:System.Text.RegularExpressions.Match> tipo.

- Ogni gruppo denominato comporta una proprietà specificata e l'accesso alla proprietà comporta un uso di un indicizzatore in caso di corrispondenza `Groups` raccolta.

Il codice seguente è il nucleo della logica per implementare un provider di questo tipo, e questo esempio viene omesso l'aggiunta di tutti i membri per il tipo specificato. Per informazioni su ogni membro aggiunto, vedere la sezione appropriata più avanti in questo argomento. Per il codice completo, scaricare l'esempio dal [pacchetto di esempio F # 3.0](https://fsharp3sample.codeplex.com) sul sito Web Codeplex.

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

- Il provider di tipi accetta due parametri statici: il `pattern`, che è obbligatorio e il `options`, quali sono facoltativi (perché è stato specificato un valore predefinito).

- Dopo che vengono forniti gli argomenti statici, si crea un'istanza dell'espressione regolare. L'istanza genererà un'eccezione se l'espressione regolare non è valido e questo errore verrà segnalato agli utenti.

- All'interno di `DefineStaticParameters` callback, si definisce il tipo che verrà restituito dopo che gli argomenti vengono forniti.

- Questo codice imposta `HideObjectMethods` su true in modo che l'esperienza IntelliSense rimarrà semplificata. Questo attributo determina il `Equals`, `GetHashCode`, `Finalize`, e `GetType` membri da eliminare da elenchi di IntelliSense per un oggetto specificato.

- Si utilizza `obj` come tipo di base del metodo, ma si userà un `Regex` oggetto come rappresentazione di runtime di questo tipo, come illustrato nell'esempio successivo.

- La chiamata per il `Regex` costruttore genera un <xref:System.ArgumentException> quando un'espressione regolare non è valida. Il compilatore intercetta questa eccezione e segnala all'utente un messaggio di errore in fase di compilazione o nell'editor di Visual Studio. Questa eccezione consente le espressioni regolari per essere convalidato ma non in esecuzione un'applicazione.

Il tipo definito in precedenza non è ancora utile poiché non contiene qualsiasi proprietà o metodi significativi. In primo luogo, aggiungere un valore statico `IsMatch` metodo:

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

Il codice precedente definisce un metodo `IsMatch`, che accetta come input una stringa e restituisce un `bool`. L'unica parte complicata consiste nell'utilizzare il `args` argomento all'interno di `InvokeCode` definizione. In questo esempio `args` è riportato un elenco di offerte che rappresenta gli argomenti per questo metodo. Se il metodo è un metodo di istanza, il primo argomento rappresenta il `this` argomento. Tuttavia, per un metodo statico, gli argomenti sono tutto senza l'esplicita al metodo. Si noti che il tipo del valore tra virgolette deve corrispondere al tipo restituito specificato (in questo caso, `bool`). Si noti inoltre che questo codice Usa il `AddXmlDoc` metodo per assicurarsi che il metodo specificato è inoltre utile documentazione, che è possibile fornire IntelliSense.

Successivamente, aggiungere un'istanza del metodo di corrispondenza. Tuttavia, questo metodo deve restituire un valore di un oggetto fornito `Match` tipo in modo che i gruppi sono accessibili in modo fortemente tipizzato. In questo modo, si dichiara prima di tutto la `Match` tipo. Poiché questo tipo dipende il criterio è stato fornito come argomento statico, questo tipo deve essere annidato all'interno della definizione di tipo con parametri:

```fsharp
let matchTy = 
    ProvidedTypeDefinition(
        "MatchType", 
        baseType = Some baseTy, 
        hideObjectMethods = true)

ty.AddMember matchTy
```

È quindi possibile aggiungere una proprietà al tipo di corrispondenza per ogni gruppo. In fase di esecuzione, una corrispondenza è rappresentata come un <xref:System.Text.RegularExpressions.Match> valore, pertanto la quotation che definisce la proprietà è necessario usare il <xref:System.Text.RegularExpressions.Match.Groups> indicizzato per ottenere il gruppo pertinente.

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

Anche in questo caso, si noti che si aggiunge la documentazione XML per la proprietà fornita. Si noti inoltre che una proprietà può essere letti se un `GetterCode` vengono fornite funzioni e le proprietà possono essere scritti se un `SetterCode` vengono fornite funzioni, in modo che la proprietà risulta è di sola lettura.

Ora è possibile creare un metodo di istanza che restituisce un valore di questo `Match` tipo:

```fsharp
let matchMethod = 
    ProvidedMethod(
        methodName = "Match", 
        parameters = [ProvidedParameter("input", typeof<string>)], 
        returnType = matchTy, 
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first ocurrence of this regular expression" 

ty.AddMember matchMeth
```

Poiché si sta creando un metodo di istanza `args.[0]` rappresenta il `RegexTyped` istanza su cui viene chiamato il metodo, e `args.[1]` è l'argomento di input.

Infine, fornire un costruttore in modo che è possibile creare istanze del tipo fornito.

```fsharp
let ctor = 
    ProvidedConstructor(
        parameters = [], 
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

Il costruttore Cancella semplicemente per la creazione di un'istanza di espressioni regolari di .NET standard, che è nuovamente sottoposto a boxing a un oggetto perché `obj` è la cancellazione del tipo fornito. Con questa modifica, l'esempio di utilizzo di API che specificata in precedenza nell'argomento funziona come previsto. Il codice seguente è completo e finale:

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
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurence of this regular expression"

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

### <a name="key-lessons"></a>Lezioni principali

In questa sezione viene spiegato come creare un provider di tipi che agisce sui relativi parametri statici. Il provider controlla il parametro static e offre operazioni in base al relativo valore.

## <a name="a-type-provider-that-is-backed-by-local-data"></a>Un Provider di tipi supportato da dati locali

Spesso è possibile che il provider di tipi per presentare le API basate su non solo parametri statici, ma anche informazioni provenienti da sistemi locali o remoti. Questa sezione vengono illustrati i provider di tipi che si basano sui dati locali, ad esempio file di dati locali.

### <a name="simple-csv-file-provider"></a>Provider di File CSV semplice

Un esempio semplice, prendere in considerazione un provider di tipi per l'accesso ai dati scientifici in formato CSV (Comma Separated Value). In questa sezione si presuppone che i file CSV deve contenere una riga di intestazione seguita da dati a virgola mobile, come illustrato nella tabella seguente:

|Distanza (misurazione)|Tempo (secondo)|
|----------------|-------------|
|50.0|3.7|
|100.0|5.2|
|150.0|6.4|

In questa sezione viene illustrato come fornire un tipo che è possibile usare per ottenere le righe con un `Distance` vlastnosti typu `float<meter>` e una `Time` vlastnosti typu `float<second>`. Per semplicità, i presupposti seguenti:

- I nomi di intestazione sono un'unità di misura o avere il formato "Nome (unità)" e non contengono virgole.

- Le unità sono tutte le unità Systeme International (SI) come le [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames (modulo) (F #)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) modulo definisce.

- Le unità sono tutti semplice (ad esempio, controllare) piuttosto che composta (ad esempio, misuratore/secondo).

- Tutte le colonne contengono dati a virgola mobile.

Un provider di più completo sarebbe Allentare queste restrizioni.

Anche in questo caso il primo passaggio è da considerare come dovrebbe apparire l'API. Dato un file `info.csv` con i contenuti della tabella precedente (nel formato delimitato da virgole), gli utenti del provider possono scrivere codice simile all'esempio seguente:

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

La traduzione ottima richiederà il provider di tipi definire un reale `CsvFile` tipo nell'assembly del provider di tipi. Provider di tipi si basano spesso su alcuni tipi di helper e metodi per eseguire il wrapping importanti per la logica. Poiché le misure vengono cancellate in fase di esecuzione, è possibile usare un `float[]` come tipo cancellato per una riga. Il compilatore considererà come se avessero tipi differenti misura colonne diverse. Ad esempio, la prima colonna nel nostro esempio dispone di tipo `float<meter>`, mentre la seconda è `float<second>`. Tuttavia, la rappresentazione cancellata può rimanere piuttosto semplice.

Il codice seguente illustra le principali dell'implementazione.

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data = 
        seq { for line in File.ReadAllLines(filename) |> Seq.skip 1 do
                 yield line.Split(',') |> Array.map float }
        |> Seq.cache
    member __.Data = data

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

Tenere presente i punti seguenti circa l'implementazione:

- Costruttori di overload consentono il file originale o uno che dispone di uno schema identico da leggere. Questo modello è comune quando si scrive un provider di tipi per le origini dati locali o remoti, e questo modello consente a un file locale da utilizzare come modello per i dati remoti.

- È possibile usare la [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) valore che viene passato al costruttore del provider di tipo per risolvere i nomi di file relativo.

- È possibile usare il `AddDefinitionLocation` metodo per definire la posizione delle proprietà specificata. Pertanto, se si usa `Go To Definition` su una proprietà specificata, il file CSV verrà aperto in Visual Studio.

- È possibile usare la `ProvidedMeasureBuilder` tipo per cercare le unità del sistema internazionale di misura e generare il relativo `float<_>` tipi.

### <a name="key-lessons"></a>Lezioni principali

In questa sezione viene spiegato come creare un provider di tipi per un'origine dati locale con un semplice schema contenuta nell'origine dati stessa.

## <a name="going-further"></a>Approfondimenti

Le sezioni seguenti includono alcuni suggerimenti per approfondire l'argomento.

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>Esaminare il codice compilato per i tipi cancellati

Per avere un'idea di come l'utilizzo del provider del tipo corrispondente al codice che viene generato, esaminare la funzione seguente usando il `HelloWorldTypeProvider` utilizzato in precedenza in questo argomento.

```fsharp
let function1 () = 
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

Ecco un'immagine del codice decompilato usando ildasm.exe risulta:

```
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

Come illustrato nell'esempio, tutti i riferimenti di tipo `Type1` e il `InstanceProperty` proprietà sono state cancellate, lasciando solo le operazioni sui tipi di runtime coinvolti.

### <a name="design-and-naming-conventions-for-type-providers"></a>Progettazione e convenzioni di denominazione per i provider di tipi

Osservare le convenzioni seguenti durante la creazione di provider di tipi.

**Provider per i protocolli di connettività** In generale, i nomi del provider la maggior parte delle DLL per i protocolli di connettività dei dati e il servizio, ad esempio le connessioni di OData o SQL, devono terminare `TypeProvider` o `TypeProviders`. Ad esempio, usare un nome DLL che è simile alla stringa seguente:

```
  Fabrikam.Management.BasicTypeProviders.dll
```

Assicurarsi che i tipi forniti sono membri dello spazio dei nomi corrispondenti e indicano il protocollo di connettività che è stata implementata:

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**I provider di utilità per la scrittura di codice generale**.  Per un'utilità provider di tipi, ad esempio che per le espressioni regolari, il provider di tipi può essere parte di una libreria di base, come illustrato nell'esempio seguente:

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

In questo caso, il tipo fornito apparirebbe in un momento appropriato in base alle convenzioni di progettazione .NET normale:

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

**Zdroje dat singleton**. Alcuni provider di tipi connettersi a un'origine dati dedicato e fornire solo i dati. In questo caso, è necessario eliminare il `TypeProvider` suffisso e usare le normali convenzioni di denominazione .NET:

```fsharp
#r "Fabrikam.Data.Freebase.dll"
  
let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

Per altre informazioni, vedere il `GetConnection` progettare convenzione che è descritti più avanti in questo argomento.

### <a name="design-patterns-for-type-providers"></a>Schemi progettuali per provider di tipi

Le sezioni seguenti descrivono i modelli di progettazione che è possibile usare durante la creazione di provider di tipi.

#### <a name="the-getconnection-design-pattern"></a>Lo schema progettuale GetConnection

La maggior parte dei provider di tipi deve essere scritto per utilizzare il `GetConnection` modello viene usato per il provider di tipi in FSharp.Data.TypeProviders.dll, come illustrato nell'esempio seguente:

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>Provider di tipi supportati da servizi e dei dati remota

Prima di creare un provider di tipi supportato da servizi e dei dati remota, è necessario considerare una gamma di problemi che vengono svolte nella programmazione connesso. Tali problemi riguardano le considerazioni seguenti:

- mapping dello schema

- attività e invalidamento in presenza di modifica dello schema

- la memorizzazione nella cache dello schema

- implementazioni asincrone di operazioni di accesso ai dati

- supporto delle query, incluse le query LINQ

- le credenziali e autenticazione

In questo argomento non Esplora ulteriormente questi problemi.

### <a name="additional-authoring-techniques"></a>Ulteriori informazioni sulle tecniche di creazione e modifica

Quando si scrive il proprio provider di tipi, si potrebbe voler usare le seguenti tecniche aggiuntive.

### <a name="creating-types-and-members-on-demand"></a>Creazione di tipi e membri On Demand

L'API ProvidedType è posticipata le versioni di AddMember.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

Queste versioni consentono di creare spazi on demand di tipi.

### <a name="providing-array-types-and-generic-type-instantiations"></a>Che fornisce i tipi di matrice e le creazioni di istanze di tipo generico

Come specificato di membri (le cui firme includono i tipi di matrice, tipi byref e le creazioni di istanze di tipi generici) usando il normale `MakeArrayType`, `MakePointerType`, e `MakeGenericType` in qualsiasi istanza di <xref:System.Type>, tra cui `ProvidedTypeDefinitions`.

> [!NOTE]
> In alcuni casi potrebbe essere necessario usare l'helper in `ProvidedTypeBuilder.MakeGenericType`.  Vedere le [documentazione del SDK del Provider di tipo](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) per altri dettagli.

### <a name="providing-unit-of-measure-annotations"></a>Fornendo l'unità di misura annotazioni

L'API ProvidedTypes fornisce gli helper per fornire le annotazioni di misure. Ad esempio, specificare il tipo `float<kg>`, usare il codice seguente:

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  Specificare il tipo `Nullable<decimal<kg/m^2>>`, usare il codice seguente:

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>L'accesso alle risorse locali del progetto o Script locali

Ogni istanza di un provider di tipi può essere assegnato un `TypeProviderConfig` valore durante la costruzione. Questo valore contiene la "cartella di risoluzione" per il provider (vale a dire, la cartella di progetto per la compilazione o la directory che contiene uno script), l'elenco di assembly di riferimento e altre informazioni.

### <a name="invalidation"></a>Invalidamento

I provider possono generare segnali di invalidamento per notificare al servizio di linguaggio F # che hanno modificato i presupposti dello schema. Quando si verifica l'invalidamento, viene eseguito il rollforward un typecheck se il provider è ospitato in Visual Studio. Questo segnale verrà ignorato quando il provider è ospitato in F # Interactive o dal compilatore F # (fsc.exe).

### <a name="caching-schema-information"></a>La memorizzazione nella cache le informazioni sullo Schema

I provider devono spesso memorizzare nella cache di accesso alle informazioni sullo schema. I dati memorizzati nella cache devono essere archiviati tramite un nome file che viene fornito come parametro statico o come dati utente. Un esempio di memorizzazione nella cache dello schema è il `LocalSchemaFile` parametro nel provider di tipi nel `FSharp.Data.TypeProviders` assembly. Nell'implementazione di questi provider, questo parametro statico indirizza il provider di tipi da utilizzare le informazioni dello schema nel file locale specificato anziché l'accesso all'origine dati in rete. Per usare le informazioni sullo schema memorizzato nella cache, è necessario impostare anche il parametro static `ForceUpdate` a `false`. È possibile utilizzare una tecnica simile per consentire l'accesso ai dati online e offline.

### <a name="backing-assembly"></a>Assembly di supporto

Quando si compila un `.dll` o `.exe` file, il file con estensione DLL di supporto per i tipi generati viene collegato staticamente all'assembly risultante. Questo collegamento viene creato copiando le definizioni dei tipi di linguaggio intermedio (IL) e le risorse gestite dall'assembly sottostante nell'assembly finale. Quando si usa F # Interactive, il file con estensione DLL di backup non vengono copiato e invece viene caricato direttamente nel processo di F # Interactive.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>Le eccezioni e diagnostica dal provider di tipi

Tutti gli usi di tutti i membri di tipi specificati possono generare eccezioni. In tutti i casi, se un provider di tipi genera un'eccezione, il compilatore host attributi l'errore per un provider di tipi specifici.

- Le eccezioni di tipo provider non devono mai comportare errori interni del compilatore.

- Provider di tipi non possono segnalare gli avvisi.

- Quando un provider di tipi è ospitato nel compilatore F #, un ambiente di sviluppo F # o F # Interactive, vengono rilevate tutte le eccezioni da tale provider. La proprietà del messaggio è sempre il testo dell'errore e viene visualizzata nessuna analisi dello stack. Se si intende generare un'eccezione, è possibile generare gli esempi seguenti: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.

#### <a name="providing-generated-types"></a>Che fornisce i tipi generati

Finora, questo documento ha descritto come specificare i tipi cancellati. È anche possibile usare il meccanismo di provider in F # per fornire tipi generati, che vengono aggiunti come definizioni di tipi .NET reali in programma degli utenti. È necessario farvi riferimento generato tipi forniti tramite una definizione di tipo.

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

Il codice helper ProvidedTypes-0.2 che fa parte della versione F # 3.0 offre solo supporto limitato per fornire tipi generati. Le istruzioni seguenti devono essere soddisfatte per una definizione di tipo generato:

- `isErased` deve essere impostata su `false`.

- Il tipo generato deve essere aggiunto a un oggetto appena costruito `ProvidedAssembly()`, che rappresenta un contenitore per i frammenti di codice generato.

- Il provider deve disporre di un assembly con un file con estensione dll .NET sottostante effettiva con un file con estensione DLL corrispondente sul disco.

## <a name="rules-and-limitations"></a>Regole e limitazioni

Quando si scrivono i provider di tipi, tenere le seguenti regole e le limitazioni presenti.

### <a name="provided-types-must-be-reachable"></a>Tipi forniti devono essere raggiungibili

Tutti forniti tipi devono essere raggiungibili dai tipi non annidata. I tipi annidati non vengono forniti nella chiamata ai `TypeProviderForNamespaces` costruttore o una chiamata a `AddNamespace`. Ad esempio, se il provider fornisce un tipo `StaticClass.P : T`, è necessario assicurarsi che T è un tipo non annidato o annidati in uno.

Ad esempio, per alcuni provider esistono una classe statica, ad esempio `DataTypes` che contengono questi `T1, T2, T3, ...` tipi. In caso contrario, l'errore indica che è stato trovato un riferimento al tipo T in un assembly, ma non è stato possibile trovare il tipo in tale assembly. Se viene visualizzato questo errore, verificare che tutti i sottotipi possono essere raggiunto dai tipi di provider. Nota: Queste `T1, T2, T3...` tipi sono definiti i *in tempo reale* tipi. Ricordarsi di inserirle in uno spazio dei nomi accessibile o un tipo di elemento padre.

### <a name="limitations-of-the-type-provider-mechanism"></a>Limitazioni del meccanismo di Provider di tipo

Il meccanismo di provider in F # presenta le limitazioni seguenti:

- L'infrastruttura sottostante per il provider di tipi in F # non supporta la condizione generica tipi o metodi generici forniti.

- Il meccanismo non supporta i tipi annidati con parametri statici.

## <a name="development-tips"></a>Suggerimenti per lo sviluppo

Si potrebbero risultare utili i suggerimenti seguenti durante il processo di sviluppo.

### <a name="run-two-instances-of-visual-studio"></a>Eseguire due istanze di Visual Studio

È possibile sviluppare il provider di tipi in un'unica istanza e testare il provider negli altri perché il test dell'IDE richiederà un blocco sul file con estensione dll che impedisce il provider di tipi di ricompilazione. Di conseguenza, è necessario chiudere la seconda istanza di Visual Studio mentre il provider è incorporato nella prima istanza e quindi è necessario aprire nuovamente la seconda istanza dopo il provider di compilazione.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>Eseguire il debug di provider di tipi utilizzando le chiamate di fsc.exe

È possibile richiamare i provider di tipi utilizzando gli strumenti seguenti:

- FSC.exe (compilatore della riga di comando di F #)

- fsi.exe (compilatore The F # Interactive)

- devenv.exe (Visual Studio)

Si possono spesso il debug di provider di tipi più facilmente usando fsc.exe in un file di script di test (ad esempio, script. fsx). È possibile avviare un debugger al prompt dei comandi.

```
  devenv /debugexe fsc.exe script.fsx
```

  È possibile usare la registrazione di stampa-a-stdout.

## <a name="see-also"></a>Vedere anche

- [Provider di tipi](index.md)
- [il SDK del Provider di tipo](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
