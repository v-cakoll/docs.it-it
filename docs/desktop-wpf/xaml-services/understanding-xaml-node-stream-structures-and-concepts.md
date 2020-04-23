---
title: Informazioni su strutture e concetti del flusso del nodo XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML node streams [XAML Services]
- nodes [XAML Services], XAML node stream
- XAML [XAML Services], XAML node streams
ms.assetid: 7c11abec-1075-474c-9d9b-778e5dab21c3
ms.openlocfilehash: b3de3dca029c5e676fc7cdebc7735cfdade0228a
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071619"
---
# <a name="xaml-node-stream-structures-and-concepts"></a>Concetti e strutture del flusso del nodo XAMLXAML node stream structures and concepts

I reader XAML e i writer XAML implementati nei servizi XAML di .NET si basano sul concetto di progettazione di un flusso del nodo XAML. Il flusso di nodi XAML è una concettualizzazione di un set di nodi XAML. In questa concettualizzazione, un processore XAML attraversa la struttura delle relazioni tra i nodi in XAML, una alla volta. In qualsiasi momento, in un flusso di nodi XAML aperto è presente solo un record o una posizione corrente e molti aspetti dell'API segnalano unicamente le informazioni disponibili da tale posizione. Il nodo corrente in un flusso di nodi XAML può essere descritto come un oggetto, un membro o un valore. Trattando XAML come flusso di nodi XAML, i reader XAML possono comunicare con i writer XAML e consentire a un programma di visualizzare, interagire con o modificare i contenuti di un flusso di nodi XAML durante un'operazione relativa a un percorso di salvataggio o di caricamento che usa XAML. La progettazione dell'API del lettore e del writer XAML e il concetto di flusso del nodo <xref:System.Xml.XmlReader> XAML <xref:System.Xml.XmlWriter> sono simili ai precedenti progetti e concetti del lettore e del writer correlati, ad esempio il modello DOM (Document Object Model) XML e le classi e . Questo argomento illustra i concetti correlati al flusso di nodi XAML e descrive come scrivere routine che interagiscono con rappresentazioni XAML a livello di nodi XAML.

## <a name="loading-xaml-into-a-xaml-reader"></a>Caricamento di XAML in un reader XAML

La classe base <xref:System.Xaml.XamlReader> non dichiara una tecnica particolare di caricamento del codice XAML iniziale in un reader XAML. Al contrario, una classe derivata dichiara e implementa la tecnica di caricamento, tra cui le caratteristiche generali e i vincoli dell'origine di input per XAML. Ad esempio, un oggetto <xref:System.Xaml.XamlObjectReader> legge un oggetto grafico, a partire dall'origine di input di un singolo oggetto che rappresenta la radice o base. L'oggetto <xref:System.Xaml.XamlObjectReader> produce quindi un flusso di nodi XAML dall'oggetto grafico.

La sottoclasse definita dai <xref:System.Xaml.XamlReader> servizi XAML <xref:System.Xaml.XamlXmlReader>.NET più importante è . <xref:System.Xaml.XamlXmlReader> carica il codice XAML iniziale, caricando un file di testo direttamente tramite un flusso o un percorso di file o indirettamente tramite una classe reader correlata, come <xref:System.IO.TextReader>. Si può pensare a <xref:System.Xaml.XamlReader> come a un oggetto contenente tutta l'origine di input XAML dopo il caricamento. Tuttavia, l'API di base di <xref:System.Xaml.XamlReader> è progettata in modo che il reader interagisca con un singolo nodo XAML. Quando viene eseguito il caricamento per la prima volta, il primo nodo singolo incontrato è la radice di XAML e il relativo oggetto iniziale.

### <a name="the-xaml-node-stream-concept"></a>Concetto di flusso di nodi XAML

Se si ha maggiore familiarità con un DOM, una metafora della struttura ad albero o un approccio basato su query per l'accesso alle tecnologie basate su XML, è necessario che sia disponibile un modo utile per concettualizzare un flusso di nodi XAML. Si immagini che il codice XAML caricato sia un modello DOM o un albero in cui ogni nodo possibile è espanso completamente e quindi presentato in modo lineare. Avanzando tra i nodi, si potrebbe entrare o uscire da livelli che sarebbero rilevanti per un modello DOM, ma il flusso di nodi XAML non ne tiene traccia in modo esplicito in quanto questi concetti relativi ai livelli non sono rilevanti per un flusso di nodi. Il flusso di nodi ha una posizione "corrente", ma a meno che non siano state archiviate altre parti del flusso come riferimenti, ogni aspetto del flusso di nodi al di fuori della posizione del nodo corrente non viene visualizzato.

Il concetto di flusso di nodi XAML offre il considerevole vantaggio che, se si scorre l'intero flusso di nodi, si può essere certi che sia stata elaborata l'intera rappresentazione XAML. Non è necessario preoccuparsi del fatto che in una query, un'operazione DOM o altri approcci non lineari all'elaborazione delle informazioni venga persa una parte della rappresentazione XAML completa. Per questo motivo, la rappresentazione del flusso di nodi XAML è ideale per la connessione di reader XAML e writer XAML e per fornire un sistema che consenta di inserire un proprio processo che opera tra le fasi di lettura e scrittura di un'operazione di elaborazione XAML. In molti casi, l'ordine dei nodi nel flusso di nodi XAML viene deliberatamente ottimizzato o riorganizzato dai reader XAML rispetto all'ordine che potrebbe caratterizzare l'oggetto grafico, il file binario o il testo di origine. Questo comportamento è finalizzato ad applicare un'architettura di elaborazione XAML in cui i writer XAML non si trovano mai in una posizione in cui devono tornare "indietro" nel flusso di nodi. Idealmente, tutte le operazioni di scrittura XAML devono poter essere eseguite in base al contesto dello schema e alla posizione corrente del flusso di nodi.

## <a name="a-basic-reading-node-loop"></a>Ciclo di nodi di lettura di base

Un ciclo di nodi di lettura di base per l'esame di un flusso di nodi XAML è costituito dai concetti seguenti. Ai fini dei cicli di nodi descritti in questo argomento, si presupponga di leggere un file XAML leggibile basato su testo tramite <xref:System.Xaml.XamlXmlReader>. I collegamenti in questa sezione si riferiscono all'API del ciclo di nodi XAML specifica implementata da <xref:System.Xaml.XamlXmlReader>.

- Assicurarsi di non trovarsi alla fine del flusso di nodi XAML (controllare <xref:System.Xaml.XamlXmlReader.IsEof%2A>oppure usare il valore restituito di <xref:System.Xaml.XamlXmlReader.Read%2A> ). Se ci si trova alla fine del flusso, non vi è alcun nodo corrente ed è necessario uscire.

- Controllare il tipo di nodo attualmente esposto dal flusso di nodi XAML chiamando <xref:System.Xaml.XamlXmlReader.NodeType%2A>.

- Se si dispone di un writer di oggetti XAML associato connesso direttamente, a questo punto si chiama in genere <xref:System.Xaml.XamlWriter.WriteNode%2A> .

- In base al valore <xref:System.Xaml.XamlNodeType> segnalato per il nodo corrente o il record corrente, chiamare una delle proprietà seguenti per ottenere informazioni sui contenuti del nodo:

  - Per la proprietà <xref:System.Xaml.XamlXmlReader.NodeType%2A> di <xref:System.Xaml.XamlNodeType.StartMember> o <xref:System.Xaml.XamlNodeType.EndMember>, chiamare <xref:System.Xaml.XamlXmlReader.Member%2A> per ottenere le informazioni di <xref:System.Xaml.XamlMember> su un membro. Il membro potrebbe <xref:System.Xaml.XamlDirective>essere un oggetto e pertanto non necessariamente un membro convenzionale definito dal tipo dell'oggetto precedente. Ad esempio, `x:Name` applicato a un oggetto corrisponde a un membro XAML dove <xref:System.Xaml.XamlMember.IsDirective%2A> è true e la proprietà <xref:System.Xaml.XamlMember.Name%2A> del membro è `Name`, con altre proprietà che indicano che questa direttiva si trova nello spazio dei nomi XAML del linguaggio XAML.

  - Per la proprietà <xref:System.Xaml.XamlXmlReader.NodeType%2A> di <xref:System.Xaml.XamlNodeType.StartObject> o <xref:System.Xaml.XamlNodeType.EndObject>, chiamare <xref:System.Xaml.XamlXmlReader.Type%2A> per ottenere le informazioni di <xref:System.Xaml.XamlType> su un oggetto.

  - Per la proprietà <xref:System.Xaml.XamlXmlReader.NodeType%2A> di <xref:System.Xaml.XamlNodeType.Value>, chiamare <xref:System.Xaml.XamlXmlReader.Value%2A>. Un nodo è un valore solo se è l'espressione più semplice di un valore per un membro o il testo di inizializzazione per un oggetto (tuttavia, è opportuno tenere conto del comportamento di conversione dei tipi illustrato più avanti in questo argomento).

  - Per la proprietà <xref:System.Xaml.XamlXmlReader.NodeType%2A> di <xref:System.Xaml.XamlNodeType.NamespaceDeclaration>, chiamare <xref:System.Xaml.XamlXmlReader.Namespace%2A> per ottenere informazioni sullo spazio dei nomi per un nodo spazio dei nomi.

- Chiamare <xref:System.Xaml.XamlXmlReader.Read%2A> per far avanzare il reader XAML al nodo successivo nel flusso di nodi XAML e ripetere la procedura.

Il flusso del nodo XAML fornito dai lettori XAML dei servizi XAML .NET fornisce sempre un attraversamento completo e approfondito di tutti i possibili nodi. Tra le tipiche tecniche di controllo di flusso per un ciclo di nodi XAML vi sono la definizione di un corpo in `while (reader.Read())`e l'attivazione di <xref:System.Xaml.XamlXmlReader.NodeType%2A> in corrispondenza di ogni punto nodo nel ciclo di nodi.

Se il flusso di nodi è alla fine del file, il nodo corrente è null.

Il ciclo più semplice che usa un reader e un writer è simile all'esempio riportato di seguito.

```csharp
XamlXmlReader xxr = new XamlXmlReader(new StringReader(xamlStringToLoad));
//where xamlStringToLoad is a string of well formed XAML
XamlObjectWriter xow = new XamlObjectWriter(xxr.SchemaContext);
while (xxr.Read()) {
  xow.WriteNode(xxr);
}
```

Questo esempio di base di un ciclo di nodi XAML del percorso di caricamento connette in modo trasparente il reader XAML e il writer XAML, in modo analogo a quanto avviene usando <xref:System.Xaml.XamlServices.Parse%2A?displayProperty=nameWithType>. Ma questa struttura di base viene quindi espansa per essere applicata allo scenario di lettura o scrittura. Ecco alcuni degli scenari possibili:

- Attivare <xref:System.Xaml.XamlXmlReader.NodeType%2A>. Eseguire azioni diverse a seconda del tipo di nodo letto.

- Non chiamare <xref:System.Xaml.XamlWriter.WriteNode%2A> in tutti i casi. Chiamare <xref:System.Xaml.XamlWriter.WriteNode%2A> solo per alcuni valori di <xref:System.Xaml.XamlXmlReader.NodeType%2A> .

- Nella logica per un determinato tipo di nodo, analizzare le specifiche di tale nodo e agire di conseguenza. Ad esempio, è possibile scrivere solo oggetti provenienti da un particolare spazio dei nomi XAML e quindi eliminare o rinviare tutti gli oggetti non da tale spazio dei nomi XAML. In alternativa, è possibile rimuovere o rielaborare in altro modo qualsiasi direttiva XAML non supportata dal sistema XAML come parte dell'elaborazione dei membri.

- Definire un oggetto <xref:System.Xaml.XamlObjectWriter> personalizzato che esegue l'override dei metodi `Write*` , eventualmente con un mapping dei tipi che consenta il bypass del contesto dello schema XAML.

- Costruire l'oggetto <xref:System.Xaml.XamlXmlReader> in modo da usare un contesto dello schema XAML non predefinito, affinché le differenze personalizzate nel comportamento XAML vengano usate sia dal reader sia dal writer.

### <a name="accessing-xaml-beyond-the-node-loop-concept"></a>Accesso a XAML non legato al concetto di ciclo di nodi

Vi sono altri modi, non legati al concetto di ciclo di nodi, per usare una rappresentazione XAML. Potrebbe ad esempio essere disponibile un reader XAML in grado di leggere un nodo indicizzato oppure di accedere direttamente ai nodi tramite `x:Name`, `x:Uid`o altri identificatori. I servizi XAML .NET non forniscono un'implementazione completa, ma forniscono un modello suggerito tramite servizi e tipi di supporto. Per altre informazioni, vedere <xref:System.Xaml.IXamlIndexingReader> e <xref:System.Xaml.XamlNodeList>.

## <a name="working-with-the-current-node"></a>Uso del nodo corrente

Nella maggior parte degli scenari in cui viene usato un ciclo di nodi XAML non vengono solo letti i nodi, ma vengono anche elaborati i nodi correnti e ogni nodo viene passato a un'implementazione di <xref:System.Xaml.XamlWriter>.

Nello scenario tipico di percorso di caricamento, un oggetto <xref:System.Xaml.XamlXmlReader> produce un flusso di nodi XAML, i nodi XAML vengono elaborati in base alla logica e al contesto dello schema XAML e vengono passati a un oggetto <xref:System.Xaml.XamlObjectWriter>. L'oggetto grafico risultante viene quindi integrato nell'applicazione o nel framework.

In uno scenario tipico di percorso di salvataggio, un oggetto <xref:System.Xaml.XamlObjectReader> legge l'oggetto grafico, i singoli nodi XAML vengono elaborati e un oggetto <xref:System.Xaml.XamlXmlWriter> restituisce il risultato serializzato come file di testo XAML. La chiave è che sia i percorsi che gli scenari implicano l'utilizzo di esattamente un nodo XAML alla volta e i nodi XAML sono disponibili per il trattamento in modo standardizzato definito dal sistema di tipi XAML e the.NET API dei servizi XAML.

### <a name="frames-and-scope"></a>Frame e ambito

Un ciclo di nodi XAML attraversa un flusso di nodi XAML in modo lineare. Il flusso di nodi attraversa oggetti, membri che contengono altri oggetti e così via. Spesso è utile tenere traccia dell'ambito all'interno del flusso di nodi XAML mediante l'implementazione di un concetto di frame e stack. Ciò è particolarmente utile se si modifica attivamente il flusso di nodi mentre ci si trova al suo interno. Il supporto di frame e stack implementato come parte della logica del ciclo di nodi può contare gli ambiti di `StartObject` (o `GetObject`) e `EndObject` man mano che si scende in una struttura di nodi XAML, se si pensa alla struttura da una prospettiva DOM.

## <a name="traversing-and-entering-object-nodes"></a>Attraversamento e ingresso nei nodi oggetto

Il primo nodo in un flusso quando viene aperto da un reader XAML è il nodo oggetto iniziale dell'oggetto radice. Per definizione, questo oggetto è sempre un nodo singolo senza peer. In qualsiasi esempio XAML reale, l'oggetto radice è definito con una o più proprietà che contengono più oggetti e queste proprietà presentano nodi membro. I nodi membro dispongono quindi di uno o più nodi oggetto oppure possono terminare con un nodo valore. In genere, l'oggetto radice definisce gli ambiti dei nomi XAML, che sono assegnati sintatticamente come attributi nel markup di testo XAML, ma che sono mappati a un tipo di nodo `Namescope` nella rappresentazione del flusso di nodi XAML.

Si consideri l'esempio XAML seguente (si tratta di XAML arbitrario, non supportato da tipi esistenti in .NET). Si presupponga che in questo modello a oggetti `FavorCollection` sia un oggetto `List<T>` di `Favor`, che `Balloon` e `NoiseMaker` possano essere assegnati a `Favor`, che la proprietà `Balloon.Color` sia supportata da un oggetto `Color` analogo al modo in cui WPF definisce i colori come nomi di colori noti e che `Color` supporti un convertitore di tipi per la sintassi di attributo.

|Markup XAML|Flusso di nodi XAML risultante|
|-----------------|--------------------------------|
|`<Party`|`Namespace` per `Party`|
|`xmlns="PartyXamlNamespace">`|`StartObject` per `Party`|
|`<Party.Favors>`|`StartMember` per `Party.Favors`|
||Nodo`StartObject` per l'oggetto `FavorCollection`implicito|
||Nodo`StartMember` per la proprietà degli elementi `FavorCollection` impliciti|
|`<Balloon`|`StartObject` per `Balloon`|
|`Color="Red"`|`StartMember` per `Color`<br /><br /> `Value` per la stringa di valore di attributo `"Red"`<br /><br /> `EndMember` per `Color`|
|`HasHelium="True"`|`StartMember` per `HasHelium`<br /><br /> `Value` per la stringa di valore di attributo `"True"`<br /><br /> `EndMember` per `HasHelium`|
|`>`|`EndObject` per `Balloon`|
|`<NoiseMaker>Loudest</NoiseMaker>`|`StartObject` per `NoiseMaker`<br /><br /> `StartMember` per `_Initialization`<br /><br /> `Value` per la stringa di valore di inizializzazione `"Loudest"`<br /><br /> `EndMember` per `_Initialization`<br /><br /> `EndObject` per `NoiseMaker`|
||Nodo`EndMember` per la proprietà degli elementi `FavorCollection` impliciti|
||Nodo`EndObject` per l'oggetto `FavorCollection`implicito|
|`</Party.Favors>`|`EndMember` per `Favors`|
|`</Party>`|`EndObject` per `Party`|

Nel flusso di nodi XAML è possibile fare affidamento sul comportamento illustrato di seguito:

- Se è presente un nodo `Namespace` , viene aggiunto al flusso immediatamente prima dell'oggetto `StartObject` che ha dichiarato lo spazio dei nomi XAML con `xmlns`. Osservare di nuovo la tabella precedente con il codice XAML e il flusso di nodi di esempio. Si noti che i nodi `StartObject` e `Namespace` sembrano essere invertiti rispetto alle relative posizioni di dichiarazione nel markup di testo. Ciò è rappresentativo del comportamento in base a cui i nodi spazio dei nomi vengono sempre visualizzati prima del nodo a cui si applicano nel flusso di nodi. Ciò è dovuto al fatto che le informazioni dello spazio dei nomi sono fondamentali per i writer di oggetti e devono essere note al writer prima di poter eseguire il mapping dei tipi o elaborare in altro modo l'oggetto. Il posizionamento delle informazioni dello spazio dei nomi XAML prima del relativo ambito di applicazione nel flusso semplifica l'elaborazione del flusso di nodi sempre nell'ordine di presentazione.

- Tenendo presenti le considerazioni precedenti, nella maggior parte dei casi di markup reali, quando si attraversano i nodi dall'inizio, si leggono prima uno o più nodi `Namespace` rispetto all'oggetto `StartObject` della radice.

- Un nodo `StartObject` può essere seguito da un oggetto `StartMember`, `Value`o immediatamente da `EndObject`. Non è mai seguito immediatamente da un altro oggetto `StartObject`.

- Un oggetto `StartMember` può essere seguito da un oggetto `StartObject`, `Value`o immediatamente da `EndMember`. Può essere seguito da `GetObject`, per i membri il cui valore si suppone provenire da un valore esistente dell'oggetto padre anziché da un oggetto `StartObject` che creerebbe un'istanza di un nuovo valore. Può anche essere seguito da un nodo `Namespace` , che si applica a un oggetto `StartObject`successivo. Non è mai seguito immediatamente da un altro oggetto `StartMember`.

- Un nodo `Value` rappresenta il valore stesso e non è previsto alcun oggetto "EndValue". Può essere seguito solo da un oggetto `EndMember`.

  - Il testo di inizializzazione XAML dell'oggetto come potrebbe venire usato per costruzione non comporta la creazione di una struttura oggetto-valore. Viene invece creato un nodo membro dedicato per un membro denominato `_Initialization` e tale nodo membro contiene la stringa di valore di inizializzazione. Se presente, `_Initialization` è sempre il primo oggetto `StartMember`. L'oggetto`_Initialization` può essere qualificato in alcune rappresentazioni dei servizi XAML con l'ambito dei nomi XAML del linguaggio XAML, per specificare che `_Initialization` non è una proprietà definita nei tipi di supporto.

  - Una combinazione membro-valore rappresenta un'impostazione di attributo del valore. Per l'elaborazione del valore potrebbe venire usato un convertitore di valori e il valore è una stringa semplice. Tuttavia, il valore non viene valutato fino a quando un writer di oggetti XAML non elabora il flusso di nodi. Il writer di oggetti XAML dispone del contesto dello schema XAML necessario, del mapping del sistema di tipi e di altri tipo di supporto necessari per le conversioni dei valori.

- Un nodo `EndMember` può essere seguito da un nodo `StartMember` per un membro successivo o da un nodo `EndObject` per il proprietario del membro.

- Un nodo `EndObject` può essere seguito da un nodo `EndMember` . Può anche essere seguito da un nodo `StartObject` per i casi in cui gli oggetti sono peer negli elementi di una raccolta. In alternativa, può essere seguito da un nodo `Namespace` , che si applica a un oggetto `StartObject`successivo.

  - Esclusivamente nel caso della chiusura dell'intero flusso di nodi, l'oggetto `EndObject` della radice non è seguito da niente, il reader ha raggiunto la fine del file e <xref:System.Xaml.XamlReader.Read%2A> restituisce `false`.

## <a name="value-converters-and-the-xaml-node-stream"></a>Convertitori di valori e flusso di nodi XAML

Un convertitore di valori è un termine generale per un'estensione di markup, un convertitore di tipi (inclusi i serializzatori di valori) o un'altra classe dedicata segnalata come convertitore di valori nel sistema di tipi XAML. Nel flusso di nodi XAML, l'utilizzo di un convertitore di tipi e l'utilizzo di un'estensione di markup hanno rappresentazioni molto diverse.

### <a name="type-converters-in-the-xaml-node-stream"></a>Convertitori di tipi nel flusso di nodi XAML

Un set di attributi che comporta l'utilizzo di un convertitore di tipi viene segnalato nel flusso di nodi XAML come valore di un membro. Il flusso di nodi XAML non tenta di produrre un oggetto istanza del convertitore di tipi e passare a esso il valore. Per usare un'implementazione della conversione di un convertitore di tipi è necessario richiamare il contesto dello schema XAML e usarlo per il mapping dei tipi. Anche per determinare quale classe di convertitore di tipi deve essere usata per elaborare il valore è necessario indirettamente il contesto dello schema XAML. Quando si usa il contesto dello schema XAML predefinito, tali informazioni sono disponibili dal sistema di tipi XAML. Se sono necessarie informazioni sulla classe del convertitore di tipi a livello di flusso di nodi XAML prima della connessione a un writer XAML, è possibile ottenerle dalle informazioni di <xref:System.Xaml.XamlMember> del membro che viene impostato. In caso contrario, l'input del convertitore di tipi deve essere mantenuto nel flusso del nodo XAML come valore normale fino al resto delle operazioni che richiedono il sistema di mapping dei tipi e il contesto dello schema XAML, ad esempio la creazione di oggetti da un writer di oggetti XAML.

Si consideri, ad esempio, la seguente struttura di definizione di classe e il relativo utilizzo XAML:

```csharp
public class BoardSizeConverter : TypeConverter {
  //converts from string to an int[2] by splitting on an "x" char
}
public class GameBoard {
  [TypeConverter(typeof(BoardSizeConverter))]
  public int[] BoardSize; //2x2 array, initialization not shown
}
```

```xaml
<GameBoard BoardSize="8x8"/>
```

Una rappresentazione di testo del flusso di nodi XAML per questo utilizzo può essere espressa come segue:

`StartObject` con <xref:System.Xaml.XamlType> per rappresentare `GameBoard`

`StartMember` con <xref:System.Xaml.XamlMember> per rappresentare `BoardSize`

Nodo`Value` , con stringa di testo "`8x8`"

`EndMember` corrisponde a `BoardSize`

`EndObject` corrisponde a `GameBoard`

Si noti che non è presente alcuna istanza di convertitore di tipi in questo flusso di nodi. È tuttavia possibile ottenere informazioni sul convertitore di tipi chiamando <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> su <xref:System.Xaml.XamlMember> per `BoardSize`. Se si dispone di un contesto dello schema XAML valido, è anche possibile richiamare i metodi del convertitore ottenendo un'istanza da <xref:System.Xaml.Schema.XamlValueConverter%601.ConverterInstance%2A>.

### <a name="markup-extensions-in-the-xaml-node-stream"></a>Estensioni di markup nel flusso di nodi XAML

L'utilizzo di un'estensione di markup viene segnalato nel flusso di nodi XAML come nodo oggetto all'interno di un membro, in cui l'oggetto rappresenta un'istanza dell'estensione di markup. L'utilizzo di un'estensione di markup viene presentato pertanto in modo più esplicito nella rappresentazione del flusso di nodi rispetto all'utilizzo di un convertitore di tipi e fornisce maggiori informazioni. Le informazioni di<xref:System.Xaml.XamlMember> potrebbero non aver fornito dati in relazione all'estensione di markup, poiché l'utilizzo varia in base alle situazioni e a ogni caso possibile markup e non è dedicato né implicito per ogni tipo o membro come nel caso del convertitori di tipi.

La rappresentazione del flusso di nodi delle estensioni di markup come nodi oggetto avviene anche se l'utilizzo dell'estensione di markup è stato fatto in forma di attributo nel markup di testo XAML, come spesso accade. I casi di utilizzo di un'estensione di markup in forma di elemento oggetto esplicito vengono trattati nello stesso modo.

In un nodo oggetto di un'estensione di markup possono essere presenti membri di tale estensione di markup. La rappresentazione del flusso di nodi XAML preserva l'utilizzo di tale estensione di markup, sia in caso di utilizzo di un parametro posizionale sia di utilizzo con parametri denominati espliciti.

In caso di utilizzo di un parametro posizionale, il flusso di nodi XAML contiene una proprietà `_PositionalParameters` definita dal linguaggio XAML che registra l'utilizzo. Questa proprietà è un oggetto <xref:System.Collections.Generic.List%601> generico con vincolo <xref:System.Object> . Il vincolo è un oggetto e non una stringa perché presumibilmente l'utilizzo di un parametro posizionale potrebbe contenere utilizzi di estensioni di markup annidati. Per accedere ai parametri posizionali dall'utilizzo, è possibile eseguire l'iterazione nell'elenco e usare gli indicizzatori per i singoli valori di elenco.

Per l'utilizzo di un parametro denominato, ogni parametro denominato è rappresentato come nodo membro di tale nome nel flusso di nodi. I valori dei membri non sono necessariamente stringhe, poiché potrebbe essere presente un utilizzo di estensioni di markup annidato.

L'oggetto`ProvideValue` dall'estensione di markup non è stato ancora richiamato. Viene tuttavia richiamato se si connettono un reader XAML e un writer XAML in modo che venga richiamato `WriteEndObject` nel nodo dell'estensione di markup quando lo si esamina nel flusso di nodi. Per questo motivo, è in genere necessario che sia disponibile lo stesso contesto dello schema XAML che verrebbe usato per creare l'oggetto grafico nel percorso di caricamento. In caso contrario, l'oggetto `ProvideValue` da qualsiasi estensione di markup può generare eccezioni, in quanto non sono disponibili i servizi previsti.

## <a name="xaml-and-xml-language-defined-members-in-the-xaml-node-stream"></a>Membri definiti dai linguaggi XAML e XML nel flusso di nodi XAML

Alcuni membri vengono introdotti in un flusso di nodi XAML a causa di interpretazioni e convenzioni di un reader XAML, anziché tramite una costruzione o una ricerca esplicita di <xref:System.Xaml.XamlMember> . Spesso, questi membri sono direttive XAML. In alcuni casi, è l'operazione di lettura del codice XAML che introduce la direttiva nel flusso di nodi XAML. In altre parole, il testo XAML di input originale non ha specificato in modo esplicito la direttiva del membro, ma il reader XAML inserisce la direttiva per soddisfare una convenzione XAML strutturale e le informazioni del report nel flusso del nodo XAML prima che tali informazioni vengano perse.

L'elenco seguente prende nota di tutti i casi in cui è previsto che un reader XAML introduca un nodo membro XAML della direttiva e il modo in cui tale nodo membro viene identificato nelle implementazioni dei servizi XAML .NET.

- **Testo di inizializzazione per un nodo oggetto:** il nome di questo nodo membro è `_Initialization`, rappresenta una direttiva XAML e viene definito nello spazio dei nomi XAML del linguaggio XAML. È possibile ottenere un'entità statica per esso da <xref:System.Xaml.XamlLanguage.Initialization%2A>.

- **Parametri posizionali per un'estensione di markup:** il nome di questo nodo membro è `_PositionalParameters`e viene definito nello spazio dei nomi XAML del linguaggio XAML. Contiene sempre un elenco generico di oggetti, ognuno dei quali è un parametro posizionale pre-separato con il carattere delimitatore `,` come specificato nel codice XAML di input. È possibile ottenere un'entità statica per la direttiva di parametri posizionali da <xref:System.Xaml.XamlLanguage.PositionalParameters%2A>.

- **Contenuto sconosciuto:** il nome di questo nodo membro è `_UnknownContent`. Nello specifico, si tratta di un oggetto <xref:System.Xaml.XamlDirective>e viene definito nello spazio dei nomi XAML del linguaggio XAML. Questa direttiva viene usata come elemento sentinel per i casi in cui un elemento oggetto XAML include contenuto nel codice XAML di origine, ma non è possibile determinare alcuna proprietà del contenuto nel contesto dello schema XAML attualmente disponibile. È possibile rilevare questo caso in un flusso di nodi XAML controllando la presenza di membri denominati `_UnknownContent`. Se non viene eseguita alcuna altra azione nel flusso di nodi XAML del percorso di caricamento, l'oggetto <xref:System.Xaml.XamlObjectWriter> predefinito genera un'eccezione nel caso di un tentativo di chiamare `WriteEndObject` quando viene rilevato il membro `_UnknownContent` in qualsiasi oggetto. L'oggetto <xref:System.Xaml.XamlXmlWriter> predefinito non genera un'eccezione e tratta il membro come implicito. È possibile ottenere un'entità statica per `_UnknownContent` da <xref:System.Xaml.XamlLanguage.UnknownContent%2A>.

- **Proprietà Collection di una raccolta:** Anche se il tipo CLR di supporto di una classe di raccolta utilizzata per XAML dispone in genere di una proprietà denominata dedicata che contiene gli elementi della raccolta, tale proprietà non è nota a un sistema di tipi XAML prima della risoluzione del tipo di supporto. Il flusso di nodi XAML introduce invece un segnaposto `Items` come membro del tipo XAML della raccolta. Nell'implementazione dei servizi XAML .NET, il nome `_Items`di questa direttiva o membro nel flusso del nodo è . È possibile ottenere una costante per questa direttiva da <xref:System.Xaml.XamlLanguage.Items%2A>.

    Si noti che un flusso del nodo XAML potrebbe contenere un Items proprietà con elementi che risultano non essere analizzabile in base alla risoluzione del tipo di supporto e contesto dello schema XAML. Ad esempio,

- **Membri definiti da XML:** I `xml:base` `xml:lang` `xml:space` membri e definiti in XML vengono `base`segnalati come direttive XAML denominate , `lang`, e `space` nelle implementazioni dei servizi XAML .NET. Lo spazio dei nomi per questi membri è lo spazio dei nomi XML `http://www.w3.org/XML/1998/namespace`. È possibile ottenere costanti per ognuno di essi da <xref:System.Xaml.XamlLanguage>.

## <a name="node-order"></a>Ordine dei nodi

In alcuni casi, <xref:System.Xaml.XamlXmlReader> modifica l'ordine dei nodi XAML nel flusso di nodi XAML rispetto all'ordine in cui i nodi vengono visualizzati nel markup o elaborati come XML. Lo scopo è quello di ordinare i nodi in modo tale che un oggetto <xref:System.Xaml.XamlObjectWriter> possa elaborare il flusso dei nodi solo procedendo in avanti.  Nei servizi XAML .NET, il reader XAML riordina i nodi anziché lasciare questa attività al writer XAML, come ottimizzazione delle prestazioni per i consumer del writer di oggetti XAML del flusso del nodo.

Alcune direttive sono finalizzate in modo specifico a fornire maggiori informazioni per la creazione di un oggetto da un elemento oggetto. Tali direttive sono `Initialization`, `PositionalParameters`, `TypeArguments`, `FactoryMethod`, `Arguments`. I lettori XAML dei servizi XAML di .NET tentano di inserire queste `StartObject`direttive come primi membri nel flusso del nodo che segue quello di un oggetto, per i motivi illustrati nella sezione successiva.

### <a name="xamlobjectwriter-behavior-and-node-order"></a>Comportamento di XamlObjectWriter e ordine dei nodi

`StartObject` per <xref:System.Xaml.XamlObjectWriter> non segnala necessariamente al writer di oggetti XAML di costruire immediatamente l'istanza dell'oggetto. XAML include diverse funzionalità del linguaggio che consentono di inizializzare un oggetto con input aggiuntivo e di non basarsi interamente sulla chiamata di un costruttore senza parametri per produrre l'oggetto iniziale e solo allora l'impostazione delle proprietà. Tali funzionalità includono <xref:System.Windows.Markup.XamlDeferLoadAttribute>, testo di inizializzazione, [x:TypeArguments](xtypearguments-directive.md), parametri posizionali di un'estensione di markup, metodi factory e nodi [x:Arguments](xarguments-directive.md) associati (XAML 2009). Ognuno di questi casi ritarda la costruzione effettiva dell'oggetto e, poiché il flusso del nodo viene riordinato, il writer di oggetti XAML può basarsi sul comportamento di costruzione effettiva dell'istanza ogni volta che viene rilevato un membro iniziale che non è specificamente una direttiva di costruzione per quel tipo di oggetto.

### <a name="getobject"></a>GetObject

`GetObject` rappresenta un nodo XAML in cui anziché costruire un nuovo oggetto, un writer di oggetti XAML deve ottenere il valore della proprietà che contiene l'oggetto. Un caso tipico in cui un nodo `GetObject` viene rilevato in un flusso di nodi XAML riguarda un oggetto raccolta o un oggetto dizionario, quando la proprietà che contiene l'oggetto è deliberatamente di sola lettura nel modello a oggetti del tipo di supporto. In questo scenario, la raccolta o il dizionario viene spesso creato e inizializzato (in genere come oggetto vuoto) dalla logica di inizializzazione di un tipo proprietario.

## <a name="see-also"></a>Vedere anche

- <xref:System.Xaml.XamlObjectReader>
- [Servizi XAML](index.md)
- [Spazi dei nomi XAML](namespaces.md)
