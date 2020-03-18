---
title: Classi e oggetti in C# - Panoramica del linguaggio C#
description: Introduzione a C# Leggere questa panoramica di classi, oggetti ed ereditarietàRead this overview of classes, objects, and inheritance
ms.date: 02/27/2020
ms.assetid: 63a89bde-0f05-4bc4-b0cd-4f693854f0cd
ms.openlocfilehash: c178e11b5667905f75538555c8a309e2fdb4a9ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78159182"
---
# <a name="classes-and-objects"></a>Classi e oggetti

Le *classi* sono il tipo C# più importante. Una classe è una struttura di dati che combina in una singola unità lo stato (campi) e le azioni (metodi e altri membri di funzione). Una classe fornisce una definizione per *istanze* della classe create dinamicamente, note anche come *oggetti*. Le classi supportano l'*ereditarietà* e il *polimorfismo*, meccanismi in base ai quali le *classi derivate* possono estendere e specializzare le *classi di base*.

Le nuove classi vengono create tramite dichiarazioni di classe. Una dichiarazione di classe inizia con un'intestazione che specifica gli attributi e i modificatori della classe, il nome della classe, la classe di base (se disponibile) e le interfacce implementate dalla classe. L'intestazione è seguita dal corpo della classe, costituito da un elenco di dichiarazioni di membro scritte tra i delimitatori `{` e `}`.

Nel codice seguente viene illustrata `Point`una dichiarazione di una classe semplice denominata :

[!code-csharp[PointClass](~/samples/snippets/csharp/tour/classes-and-objects/Point.cs#L3-L11)]

Le istanze delle classi vengono create usando l'operatore `new`, che alloca memoria per una nuova istanza, richiama un costruttore per inizializzare l'istanza e restituisce un riferimento all'istanza. Le istruzioni seguenti creano due oggetti Point e archiviano i riferimenti agli oggetti in due variabili:

[!code-csharp[PointExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L9-L10)]

La memoria occupata da un oggetto viene automaticamente recuperata nel momento in cui l'oggetto non è più raggiungibile. Non è né necessario né possibile deallocare in modo esplicito gli oggetti in C .

## <a name="members"></a>Members

I membri di una classe possono essere membri statici o membri di istanza. I primi appartengono a classi, mentre i secondi appartengono a oggetti, ovvero a istanze di classi.

Nell'elenco seguente viene fornita una panoramica dei tipi di membri che una classe può contenere.

- Costanti
  - Valori costanti associati alla classe
- Campi
  - Variabili della classe
- Metodi
  - Calcoli e azioni che possono essere eseguiti dalla classe
- Proprietà
  - Azioni associate alla lettura e alla scrittura di proprietà denominate della classe
- Indicizzatori
  - Azioni associate all'indicizzazione di istanze della classe, come una matrice
- Eventi
  - Notifiche che possono essere generate dalla classe
- Operatori
  - Conversioni e operatori di espressione supportati dalla classe
- Costruttori
  - Azioni necessarie per inizializzare istanze della classe o la classe stessa
- Finalizzatori
  - Azioni da eseguire prima che istanze della classe vengano eliminate in modo permanente
- Tipi
  - Tipi annidati dichiarati dalla classe

## <a name="accessibility"></a>Accessibilità

A ogni membro di una classe è associata un'accessibilità, che controlla le aree del testo del programma che possono accedere al membro. Esistono sei diverse forme di accessibilità, I modificatori di accesso sono riepilogati di seguito.

- `public`
  - L'accesso non è limitato.
- `protected`
  - L'accesso è limitato a questa classe o alle classi derivate da questa classe.
- `internal`
  - L'accesso è limitato all'assembly corrente (.exe, .dll e così via).
- `protected internal`
  - L'accesso è limitato alla classe contenitore, alle classi derivate dalla classe o alle classi che lo contengono all'interno dello stesso assembly.
- `private`
  - L'accesso è limitato a questa classe.
- `private protected`
  - L'accesso è limitato alla classe o alle classi che lo contengono derivate dal tipo che lo contiene all'interno dello stesso assembly.

## <a name="type-parameters"></a>Parametri di tipo

Una definizione di classe può specificare un set di parametri di tipo se si fa seguire il nome della classe da un elenco di nomi di parametri di tipo, racchiuso tra parentesi uncinate. I parametri di tipo possono essere quindi usati nel corpo delle dichiarazioni di classe per definire i membri della classe. Nell'esempio seguente i parametri di tipo di `Pair` sono `TFirst` e `TSecond`:

[!code-csharp[Pair](~/samples/snippets/csharp/tour/classes-and-objects/Pair.cs#L3-L7)]

Un tipo di classe dichiarato per accettare parametri di tipo prende il nome di *tipo di classe generico*. Anche i tipi struct, interfaccia e delegato possono essere generici.
Quando si usa la classe generica, è necessario specificare argomenti di tipo per ogni parametro di tipo:

[!code-csharp[PairExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L15-L17)]

Un tipo generico per il quale sono stati specificati argomenti di tipo, come `Pair<int,string>` nell'esempio precedente, prende il nome di *tipo costruito*.

## <a name="base-classes"></a>Classi di base

Una dichiarazione di classe può specificare una classe di base se si fa seguire il nome della classe e i parametri di tipo dai due punti e dal nome della classe di base. L'omissione della specifica della classe di base equivale alla derivazione dal tipo `object`. Nell'esempio seguente la classe di base di `Point3D` è `Point` e quella di `Point` è `object`:

[!code-csharp[Point3DClass](~/samples/snippets/csharp/tour/classes-and-objects/Point.cs#L3-L20)]

Una classe eredita i membri della relativa classe di base. L'ereditarietà prevede che una classe contenga in modo implicito tutti i membri della relativa classe di base (ad eccezione dell'istanza e dei costruttori statici) e i relativi finalizzatori. Una classe derivata può aggiungere nuovi membri ai membri che eredita, ma non può rimuovere la definizione di un membro ereditato. Nell'esempio precedente `Point3D` eredita i campi `x` e `y` da `Point` e ogni istanza di `Point3D` contiene tre campi: `x`, `y` e `z`.

Un tipo di classe viene implicitamente convertito in uno dei relativi tipi di classe di base. Una variabile di un tipo di classe può fare riferimento a un'istanza di tale classe o a un'istanza di qualsiasi classe derivata. Nel caso delle dichiarazioni di classe precedenti, ad esempio, una variabile di tipo `Point` può fare riferimento a `Point` o `Point3D`:

[!code-csharp[Point3DExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L22-L23)]

## <a name="fields"></a>Campi

Un *campo* è una variabile associata a una classe o a un'istanza di una classe.

Un campo dichiarato con il modificatore static definisce un campo statico, che identifica esattamente una posizione di memoria. Indipendentemente dal numero di istanze di una classe vengono create, è presente una sola copia di un campo statico.

Un campo dichiarato senza il modificatore static definisce un campo di istanza. Ogni istanza di una classe contiene una copia separata di tutti i campi di istanza della classe.

Nell'esempio seguente ogni istanza `Color` della classe dispone `r`di `g`una `b` copia separata dei campi di istanza `Black` `White`, `Red` `Green`, ma è presente una sola copia dei campi , , , e `Blue` statica :

[!code-csharp[ColorClass](~/samples/snippets/csharp/tour/classes-and-objects/Color.cs#L3-L17)]

Come illustrato nell'esempio precedente, i *campi di sola lettura* possono essere dichiarati con un modificatore `readonly`. L'assegnazione a un campo `readonly` può avvenire solo nell'ambito della dichiarazione del campo o in un costruttore della stessa classe.

## <a name="methods"></a>Metodi

Un *metodo* è un membro che implementa un calcolo o un'azione che può essere eseguita da un oggetto o una classe. I *metodi statici* sono accessibili tramite la classe, mentre i *metodi di istanza* sono accessibili tramite istanze della classe.

I metodi possono avere un elenco di *parametri*, che rappresentano valori o riferimenti a variabili passati al metodo, e un *tipo restituito*, che specifica il tipo di valore calcolato e restituito dal metodo. Il tipo restituito di `void` un metodo è se non restituisce un valore.

Come i tipi, anche i metodi possono avere un set di parametri di tipo per i quali è necessario specificare argomenti di tipo quando vengono chiamati. A differenza dei tipi, gli argomenti di tipo possono essere spesso dedotti dagli argomenti di una chiamata al metodo e non devono essere assegnati in modo esplicito.

La *firma* di un metodo deve essere univoca nell'ambito della classe in cui viene dichiarato il metodo. La firma di un metodo è costituita dal nome del metodo, dal numero di parametri di tipo e dal numero, dai modificatori e dai tipi dei rispettivi parametri. La firma di un metodo non include il tipo restituito.

### <a name="parameters"></a>Parametri

I parametri consentono di passare ai metodi valori o riferimenti a variabili. I parametri di un metodo ottengono i valori effettivi dagli *argomenti* specificati quando viene richiamato il metodo. Esistono quattro tipi di parametri: parametri di valore, parametri di riferimento, i parametri di output e matrici di parametri.

Un *parametro di valore* viene usato per passare argomenti di input. Corrisponde a una variabile locale che ottiene il valore iniziale dall'argomento passato per il parametro. Le modifiche apportate a un parametro value non influiscono sull'argomento passato per il parametro.

I parametri di valore possono essere facoltativi specificando un valore predefinito. In questo caso gli argomenti corrispondenti possono essere omessi.

Un *parametro di riferimento* viene usato per passare argomenti per riferimento. L'argomento passato per un parametro di riferimento deve essere una variabile con un valore definito e, durante l'esecuzione del metodo, il parametro di riferimento rappresenta lo stesso percorso di archiviazione della variabile di argomento. Un parametro di riferimento viene dichiarato con il modificatore `ref`. Nell'esempio seguente viene illustrato l'uso di parametri `ref`.

[!code-csharp[swapExample](~/samples/snippets/csharp/tour/classes-and-objects/RefExample.cs#L3-L18)]

Un *parametro di output* viene usato per passare argomenti per riferimento. È simile a un parametro di riferimento, ad eccezione del fatto che non è necessario assegnare in modo esplicito un valore per l'argomento specificato dal chiamante. Un parametro di output viene dichiarato con il modificatore `out`. L'esempio seguente illustra come usare i parametri `out` con la sintassi introdotta in C# 7.

[!code-csharp[OutExample](~/samples/snippets/csharp/tour/classes-and-objects/OutExample.cs#L3-L17)]

Una *matrice di parametri* consente di passare un numero variabile di argomenti a un metodo. Una matrice di parametri viene dichiarata con il modificatore `params`. Solo l'ultimo parametro di un metodo può essere costituito da una matrice di parametri, che deve essere sempre di tipo unidimensionale. I metodi Write e WriteLine della classe <xref:System.Console?displayProperty=nameWithType> sono ottimi esempi per illustrare l'uso delle matrici di parametri. Sono dichiarati come segue.

[!code-csharp[ConsoleExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L78-L83)]

All'interno di un metodo, una matrice di parametri si comporta esattamente come un normale parametro di tipo matrice. Tuttavia, in una chiamata di un metodo con una matrice di parametri, è possibile passare un singolo argomento del tipo di matrice di parametri o un numero qualsiasi di argomenti del tipo di elemento della matrice di parametri. Nel secondo caso, un'istanza di matrice viene automaticamente creata e inizializzata con gli argomenti specificati. Questo esempio

[!code-csharp[StringFormat](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L55-L55)]

è equivalente alla sintassi seguente.

[!code-csharp[StringFormat2](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L30-L35)]

### <a name="method-body-and-local-variables"></a>Corpo del metodo e variabili locali

Il corpo di un metodo specifica le istruzioni da eseguire quando viene richiamato il metodo.

Il corpo di un metodo può dichiarare variabili specifiche per la chiamata del metodo. Queste variabili prendono il nome di *variabili locali*. Una dichiarazione di variabile locale specifica un nome di tipo, un nome di variabile e possibilmente un valore iniziale. Nell'esempio seguente viene dichiarata una variabile locale `i` con un valore iniziale pari a zero e una variabile locale `j` senza valore iniziale.

[!code-csharp[Squares](~/samples/snippets/csharp/tour/classes-and-objects/Squares.cs#L3-L17)]

In C# è necessario *assegnare esplicitamente* una variabile locale prima di poterne ottenere il valore. Ad esempio, se la `i` dichiarazione del precedente non include un valore iniziale, il `i` `i` compilatore segnalerà un errore per gli utilizzi successivi di perché non verrebbe assegnato in modo definito in quei punti del programma.

Un metodo può usare istruzioni `return` per restituire il controllo al chiamante. In un metodo `void` `return` che restituisce , le istruzioni non possono specificare un'espressione. In un metodo che restituisce un valore diverso da void, le istruzioni `return` devono includere un'espressione che calcola il valore restituito.

### <a name="static-and-instance-methods"></a>Metodi statici e di istanza

Un metodo dichiarato con un modificatore static è un *metodo statico*. Un metodo statico non opera su un'istanza specifica e può accedere solo direttamente ai membri statici.

Un metodo dichiarato senza un modificatore static è un *metodo di istanza*. Questo metodo agisce su un'istanza specifica e può accedere a membri statici e di istanza. L'istanza in cui è stato richiamato un metodo di istanza è accessibile in modo esplicito come `this`. È un errore a `this` cui fare riferimento in un metodo statico.

La classe `Entity` seguente contiene sia membri statici sia membri di istanza.

[!code-csharp[Entity](~/samples/snippets/csharp/tour/classes-and-objects/Entity.cs#L16-L36)]

Ogni `Entity` istanza contiene un numero di serie (e presumibilmente alcune altre informazioni che non sono mostrate qui). Il costruttore `Entity` (simile a un metodo di istanza) inizializza la nuova istanza con il successivo numero di serie disponibile. Poiché il costruttore è un membro di `serialNo` istanza, è `nextSerialNo` consentito accedere sia al campo di istanza che al campo statico.

I metodi statici `GetNextSerialNo` e `SetNextSerialNo` possono accedere al campo statico `nextSerialNo`, ma si verificherebbe un errore se accedessero direttamente al campo di istanza `serialNo`.

Nell'esempio seguente viene illustrato l'uso della classe Entity.

[!code-csharp[EntityExample](~/samples/snippets/csharp/tour/classes-and-objects/Entity.cs#L3-L15)]

I `SetNextSerialNo` `GetNextSerialNo` metodi e statici vengono richiamati sulla classe, mentre il `GetSerialNo` metodo di istanza viene richiamato sulle istanze della classe.

### <a name="virtual-override-and-abstract-methods"></a>Metodi virtuali, di override e astratti

Se una dichiarazione di metodo di istanza include un modificatore `virtual`, il metodo viene definito *metodo virtuale*. Se non è presente alcun modificatore virtual, il metodo diventa un *metodo non virtuale*.

Quando viene richiamato un metodo virtuale, il *tipo in fase di esecuzione* dell'istanza per cui viene eseguita la chiamata determina l'implementazione effettiva del metodo da richiamare. In una chiamata a un metodo non virtuale, il fattore determinante è il *tipo in fase di compilazione* dell'istanza.

Un metodo virtuale può essere *sottoposto a override* in una classe derivata. Se una dichiarazione di metodo di istanza include un modificatore override, il metodo esegue l'override di un metodo virtuale ereditato con la stessa firma. Mentre una dichiarazione di metodo virtuale introduce un nuovo metodo, una dichiarazione di metodo di override specializza un metodo virtuale ereditato esistente specificando una nuova implementazione del metodo.

Un *metodo astratto* è un metodo virtuale senza implementazione. Viene dichiarato con il modificatore abstract ed è consentito solo in una classe anch'essa dichiarata astratta. Un metodo astratto deve essere sottoposto a override in ogni classe derivata non astratta.

Nell'esempio seguente viene dichiarata una classe astratta, `Expression`, che rappresenta un nodo dell'albero delle espressioni, e tre classi derivate, `Constant`, `VariableReference` e `Operation`, che implementano i nodi dell'albero delle espressioni relativi a costanti, riferimenti a variabili e operazioni aritmetiche. (Questo esempio è simile, ma non deve essere confuso con i tipi di struttura ad albero dell'espressione).

[!code-csharp[ExpressionClass](~/samples/snippets/csharp/tour/classes-and-objects/Expressions.cs#L3-L61)]

Le quattro classi precedenti possono essere usate per modellare espressioni aritmetiche. Usando istanze di queste classi, l'espressione `x + 3`, ad esempio, può essere rappresentata come illustrato di seguito.

[!code-csharp[ExpressionExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L40-L43)]

Il metodo `Evaluate` di un'istanza `Expression` viene richiamato per valutare l'espressione specificata e generare un valore `double`. Il metodo accetta un argomento `Dictionary` che contiene nomi di variabili (come chiavi delle voci) e valori (come valori delle voci). Poiché `Evaluate` è un metodo astratto, le classi non astratte derivate da `Expression` devono eseguire l'override di `Evaluate`.

L'implementazione di un valore `Constant` del metodo `Evaluate` restituisce semplicemente la costante memorizzata. L'implementazione di un valore `VariableReference` cerca il nome della variabile nel dizionario e restituisce il valore ottenuto. L'implementazione di un valore `Operation` valuta prima gli operandi sinistro e destro (richiamando in modo ricorsivo i metodi `Evaluate`) e quindi esegue l'operazione aritmetica specificata.

Il programma seguente usa le classi `Expression` per valutare l'espressione `x * (y + 2)` per valori diversi di `x` e `y`.

[!code-csharp[ExpressionUsage](~/samples/snippets/csharp/tour/classes-and-objects/Expressions.cs#L66-L89)]

### <a name="method-overloading"></a>Overload di un metodo

L'*overload* di un metodo consente a più metodi della stessa classe di avere lo stesso nome, purché abbiano firme univoche. Quando si compila una chiamata di un metodo di overload, il compilatore usa la *risoluzione dell'overload* per determinare il metodo specifico da richiamare. La risoluzione dell'overload trova il metodo che meglio corrisponde agli argomenti o segnala un errore se non riesce a trovare alcuna corrispondenza. Nell'esempio seguente viene illustrato il funzionamento effettivo della risoluzione dell'overload. Il commento per ogni `UsageExample` chiamata nel metodo mostra quale metodo viene richiamato.

[!code-csharp[OverloadUsage](~/samples/snippets/csharp/tour/classes-and-objects/Overloading.cs#L3-L41)]

Come illustrato nell'esempio, è sempre possibile selezionare un metodo specifico eseguendo in modo esplicito il cast degli argomenti ai tipi di parametro corretti e/o specificando in modo esplicito gli argomenti di tipo.

## <a name="other-function-members"></a>Altri membri di funzione

I membri che contengono codice eseguibile sono noti come *membri funzione* di una classe. Nella sezione precedente vengono descritti i metodi, che sono i tipi principali dei membri funzione. In questa sezione vengono descritti altri membri di funzione supportati da C#: costruttori, proprietà, indicizzatori, eventi, operatori e finalizzatori.

Nell'esempio seguente viene `MyList<T>`illustrata una classe generica denominata , che implementa un elenco di oggetti che può essere creato. Nella classe sono contenuti alcuni esempi di membri di funzione più comuni.

> [!NOTE]
> Questo esempio crea una classe `MyList` che non corrisponde alla classe <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> .NET standard. Illustra i concetti necessari per questa presentazione, ma non può essere usata in sostituzione di tale classe.

[!code-csharp[ListClass](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L4-L89)]

### <a name="constructors"></a>Costruttori

C# supporta sia costruttori di istanza sia costruttori statici. Un *costruttore di istanza* è un membro che implementa le azioni necessarie per inizializzare un'istanza di una classe, Un *costruttore statico* è un membro che implementa le azioni necessarie per inizializzare una classe stessa quando viene caricata per la prima volta.

Un costruttore viene dichiarato come un metodo, senza tipo restituito e con lo stesso nome della classe in cui è contenuto. Se una dichiarazione di costruttore include un modificatore static, dichiara un costruttore statico. In caso contrario, dichiara un costruttore di istanza.

I costruttori di istanza possono essere sottoposti a overload e avere parametri facoltativi. La classe `MyList<T>`, ad esempio, dichiara un costruttore di istanza con un singolo parametro `int` facoltativo. I costruttori di istanza vengono richiamati con l'operatore `new`. Le istruzioni seguenti allocano due istanze `MyList<string>` usando il costruttore della classe `MyList` con e senza l'argomento facoltativo.

[!code-csharp[ListExample1](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L95-L96)]

A differenza di altri membri, i costruttori di istanza non vengono ereditati e una classe non dispone di costruttori di istanza diversi da quelli effettivamente dichiarati nella classe. Se per una classe non è specificato alcun costruttore di istanza, ne viene automaticamente fornito uno vuoto senza parametri.

### <a name="properties"></a>Proprietà

Le *proprietà* sono una naturale estensione dei campi. Entrambi sono membri denominati con tipi associati e la sintassi per accedere ai campi e alle proprietà è identica. Tuttavia, a differenza dei campi, le proprietà non indicano le posizioni di archiviazione. ma hanno *funzioni di accesso* che specificano le istruzioni da eseguire nel momento in cui ne vengono letti o scritti i valori.

Una proprietà viene dichiarata come un campo, con la sola differenza che la dichiarazione termina con una funzione di accesso get e/o set scritta tra i delimitatori `{` e `}`, anziché con un punto e virgola. Una proprietà che include entrambe le funzioni di accesso get e set è una *proprietà di lettura/scrittura*, una proprietà che include solo una funzione di accesso get è una *proprietà di sola lettura* e una proprietà che include solo una funzione di accesso set è una *proprietà di sola scrittura*.

Una funzione di accesso get corrisponde a un metodo senza parametri con un valore restituito del tipo di proprietà. Quando in un'espressione si fa riferimento a una proprietà, ma non come destinazione di un'assegnazione, la funzione di accesso get della proprietà viene richiamata per calcolare il valore della proprietà.

Una funzione di accesso set corrisponde a un metodo con un singolo valore di parametro denominato e senza tipo restituito. Quando si fa riferimento a una proprietà come destinazione di un'assegnazione o come operando di ++ o --, la funzione di accesso set viene richiamata con un argomento che fornisce il nuovo valore.

La classe `MyList<T>` dichiara due proprietà, `Count` e `Capacity`, che sono rispettivamente di sola lettura e di lettura/scrittura. Il codice seguente è un esempio di utilizzo di queste proprietà:The following code is an example of use of these properties:

[!code-csharp[ListExample2](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L101-L104)]

Come per i campi e i metodi, C# supporta sia proprietà di istanza sia proprietà statiche. Le proprietà statiche vengono dichiarate con il modificatore static, mentre le proprietà di istanza vengono dichiarate senza tale modificatore.

Le funzioni di accesso di una proprietà possono essere virtuali. Se una dichiarazione di proprietà contiene un modificatore `virtual`, `abstract` o `override`, questo viene applicato anche alle funzioni di accesso della proprietà.

### <a name="indexers"></a>Indicizzatori

Un *indicizzatore* è un membro che consente di indicizzare gli oggetti esattamente come una matrice. Un indicizzatore viene dichiarato come una proprietà, ma a differenza di questa il nome del membro è `this` seguito da un elenco di parametri scritti tra i delimitatori `[` e `]`. I parametri sono disponibili nelle funzioni di accesso dell'indicizzatore. Analogamente alle proprietà, gli indicizzatori possono essere di lettura/scrittura, di sola lettura o di sola scrittura e le funzioni di accesso di un indicizzatore possono essere virtuali.

La classe `MyList<T>` dichiara un indicizzatore di lettura/scrittura che accetta un parametro `int` e consente di indicizzare istanze `MyList<T>` con valori `int`. Ad esempio:

[!code-csharp[ListExample3](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L109-L117)]

Gli indicizzatori possono essere sottoposti a overload, ovvero una classe può dichiarare più indicizzatori purché includano un numero o tipi diversi di parametri.

### <a name="events"></a>Eventi

Un *evento* è un membro che consente a una classe o a un oggetto di inviare notifiche. Un evento viene dichiarato come un campo, con la sola differenza che la dichiarazione deve includere una parola chiave evento e il tipo deve essere un tipo delegato.

All'interno di una classe che dichiara un membro dell'evento, l'evento si comporta come un campo di un tipo delegato (purché l'evento non sia astratto e non dichiari funzioni di accesso). Il campo archivia un riferimento a un delegato che rappresenta i gestori eventi aggiunti all'evento. Se non è presente alcun gestore eventi, il campo è `null`.

La classe `MyList<T>` dichiara un singolo membro di evento denominato `Changed`, con cui si indica che un nuovo elemento è stato aggiunto all'elenco. L'evento Changed viene generato dal metodo virtuale `OnChanged`, che prima controlla se l'evento è `null`, ovvero se non è presente alcun gestore. Generare un evento equivale a richiamare il delegato rappresentato dall'evento. Non sono quindi necessari speciali costrutti di linguaggio per generare eventi.

I client rispondono agli eventi tramite *gestori eventi*, che possono essere aggiunti con l'operatore `+=` e rimossi con l'operatore `-=`. Nell'esempio seguente un gestore eventi viene aggiunto all'evento `Changed` di `MyList<string>`.

[!code-csharp[EventExample](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L132-L148)]

Per gli scenari avanzati in cui si desidera il controllo dell'archiviazione sottostante di un evento, una dichiarazione di evento può fornire `add` in modo esplicito e `remove` funzioni di accesso, che sono simili alla `set` funzione di accesso di una proprietà.

### <a name="operators"></a>Operatori

Un *operatore* è un membro che definisce il significato dell'applicazione di un particolare operatore di espressione alle istanze di una classe. È possibile definire tre tipi di operatori: unari, binari e di conversione. Tutti gli operatori devono essere dichiarati come `public` e `static`.

La classe `MyList<T>` dichiara due operatori, `operator ==` e `operator !=`, attribuendo così un nuovo significato alle espressioni che applicano questi operatori alle istanze di `MyList`. In particolare, gli operatori definiscono l'uguaglianza di due istanze di `MyList<T>`, confrontando ognuno degli oggetti contenuti con i rispettivi metodi Equals. Nell'esempio seguente viene usato l'operatore `==` per confrontare due istanze di `MyList<int>`.

[!code-csharp[OperatorExample](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L121-L129)]

Il primo `Console.WriteLine` restituisce `True` perché i due elenchi contengono lo stesso numero di oggetti con gli stessi valori e nello stesso ordine. Se in `MyList<T>` non fosse stato definito l'operatore `operator ==`, il primo `Console.WriteLine` avrebbe restituito `False` perché `a` e `b` fanno riferimento a istanze di `MyList<int>` diverse.

### <a name="finalizers"></a>Finalizzatori

Un *finalizzatore* è un membro che implementa le azioni necessarie per finalizzare un'istanza di una classe. I finalizzatori non possono avere parametri, non possono avere modificatori di accessibilità e non possono essere richiamati in modo esplicito. Il finalizzatore di un'istanza viene richiamato automaticamente durante la procedura di Garbage Collection.

Al Garbage Collector viene lasciata ampia scelta per decidere quando raccogliere oggetti ed eseguire finalizzatori. In particolare, la tempistica delle chiamate del finalizzatore non è deterministica e i finalizzatori possono essere eseguiti su qualsiasi thread. Per questi e altri motivi, le classi devono implementare finalizzatori solo se non è praticabile nessun'altra soluzione.

L'istruzione `using` offre una soluzione più efficace per l'eliminazione di oggetti.

> [!div class="step-by-step"]
> [Successivo](statements.md)
> [precedente](arrays.md)
