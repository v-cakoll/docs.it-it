---
title: Tipi tupla - Guida a C#
description: Informazioni sui tipi di tupla denominati e non denominati in C#
ms.date: 05/15/2018
ms.technology: csharp-fundamentals
ms.assetid: ee8bf7c3-aa3e-4c9e-a5c6-e05cc6138baa
ms.openlocfilehash: 497f95811677c300e1fadad65eb495dced7f2da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374616"
---
# <a name="c-tuple-types"></a>Tipi tupla in C#

Le tuple in C# sono tipi definiti tramite una sintassi leggera. I vantaggi includono una sintassi più semplice, regole per le conversioni basate sul numero (note come cardinalità) e sui tipi di elementi, nonché regole coerenti per copie, test di uguaglianza e assegnazioni. Lo svantaggio è che le tuple non supportano alcuni dei meccanismi orientati agli oggetti associati all'ereditarietà. È possibile ottenere una panoramica nella sezione dedicata alle tuple nell'articolo [Novità di C# 7.0](whats-new/csharp-7.md#tuples).

Questo articolo descrive le regole del linguaggio che controllano le tuple in C# 7.0 e versioni successive, i diversi modi per usarle e linee guida iniziali per l'utilizzo delle tuple.

> [!NOTE]
> Le nuove funzionalità delle tuple richiedono i tipi <xref:System.ValueTuple>.
> È necessario aggiungere il pacchetto NuGet per [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) usarlo nelle piattaforme che non includono i tipi.
>
> È simile ad altre funzionalità del linguaggio basate sui tipi resi disponibili nel framework. Alcuni esempi sono `async` e `await`, basati sull'interfaccia `INotifyCompletion`, e LINQ, basato su `IEnumerable<T>`. Tuttavia, il meccanismo di distribuzione sta cambiando perché .NET sta diventando più indipendente dalla piattaforma. .NET Framework potrebbe non essere sempre distribuito secondo la stessa cadenza del compilatore del linguaggio. Quando nuove funzionalità del linguaggio si basano su nuovi tipi, tali tipi saranno disponibili come pacchetti NuGet al momento della distribuzione delle funzionalità del linguaggio. Una volta che questi nuovi tipi vengono aggiunti all'API standard .NET e distribuiti come parte del framework, il requisito del pacchetto NuGet viene rimosso.

Per iniziare, verranno spiegati i motivi dell'aggiunta del nuovo supporto per le tuple. I metodi restituiscono un oggetto singolo. Le tuple consentono di creare più facilmente pacchetti di valori multipli in questo oggetto singolo.

.NET Framework dispone già di classi `Tuple` generiche. Queste classi, tuttavia, presentano due limitazioni principali. Da un lato, le classi `Tuple` hanno denominato le proprietà `Item1`, `Item2` e così via. Questi nomi non includono informazioni semantiche. L'uso di questi tipi `Tuple` non consente di comunicare il significato di ciascuna proprietà. Le nuove funzionalità del linguaggio consentono di dichiarare e utilizzare nomi significativi semanticamente per gli elementi in una tupla.

Le classi `Tuple` causano più problemi di prestazioni perché sono tipi riferimento. L'uso di uno dei tipi `Tuple` si traduce nell'allocazione di oggetti. Nei percorsi critici, l'allocazione di molti oggetti piccoli può avere un impatto notevole sulle prestazioni dell'applicazione. Pertanto, il supporto del linguaggio per le tuple sfrutta i nuovi struct `ValueTuple`.

Per evitare tali problematiche, è possibile creare un `class` o `struct` per supportare più elementi. Sfortunatamente, ciò comporta più lavoro per l'utente e rende poco chiare le finalità. Compilare uno `struct` o una `class` implica la definizione di un tipo con dati e comportamento. In molti casi, si desidera semplicemente archiviare più valori in un singolo oggetto.

Le funzionalità del linguaggio e gli struct `ValueTuple` generici applicano la regola che impedisce all'utente di aggiungere comportamenti (metodi) a questi tipi di tupla.
Tutti i tipi `ValueTuple` sono *struct modificabili*. Ogni campo del membro è un campo pubblico. Questo rende i campi molto leggeri. Tuttavia, ciò implica che le tuple non devono essere usate nei contesti in cui l'immutabilità è un fattore importante.

Le tuple sono contenitori di dati più semplici e flessibili rispetto ai tipi `class` e `struct`. Esaminiamo queste differenze.

## <a name="named-and-unnamed-tuples"></a>Tuple con e senza nome

Lo struct `ValueTuple` include campi denominati `Item1`, `Item2`, `Item3` e così via, simili alle proprietà definite nei tipi `Tuple` esistenti.
Questi nomi sono gli unici nomi che è possibile usare per le *tuple senza nome*. Quando non si forniscono alla tupla nomi alternativi per i campi, viene creata una tupla senza nome:

[!code-csharp[UnnamedTuple](../../samples/snippets/csharp/tuples/program.cs#01_UnNamedTuple "Unnamed tuple")]

La tupla nell'esempio precedente è stata inizializzata tramite costanti letterali e non avrà nomi di elemento creati con le *proiezioni dei nomi di campo di tupla* in C# 7.1.

Tuttavia, quando si inizializza una tupla, è possibile usare nuove funzionalità del linguaggio che assegnano a ciascun campo un nome più semplice. In questo modo viene creata una *tupla con nome*.
Le tuple con nome dispongono ancora di elementi denominati `Item1`, `Item2`, `Item3` e così via.
Hanno tuttavia anche sinonimi per eventuali elementi a cui l'utente ha assegnato un nome.
Creare una tupla con nome specificando i nomi per ogni elemento. Un modo consiste nello specificare i nomi come parte dell'inizializzazione della tupla:

[!code-csharp[NamedTuple](../../samples/snippets/csharp/tuples/program.cs#02_NamedTuple "Named tuple")]

I sinonimi vengono gestiti dal compilatore e dal linguaggio in modo che sia possibile usare efficacemente le tuple con nome. Gli editor e gli IDE possono leggere questi nomi semantici tramite le API di Roslyn. È possibile fare riferimento agli elementi di una tupla denominata tramite questi nomi semantici in qualsiasi punto dello stesso assembly. Il compilatore sostituisce i nomi definiti con equivalenti `Item*` durante la generazione dell'output compilato. Il Microsoft Intermediate Language (MSIL) compilato non include i nomi assegnati a questi elementi.

A partire da C# 7.1, i nomi dei campi per una tupla possono essere forniti dalle variabili utilizzate per inizializzare la tupla. Si parla di **[inizializzatori di proiezione tupla](#tuple-projection-initializers)**. Il codice seguente crea una tupla denominata `accumulation` con elementi `count` (integer) e `sum` (double).

[!code-csharp[ProjectedTuple](../../samples/snippets/csharp/tuples/program.cs#ProjectedTupleNames "Named tuple")]

Il compilatore deve comunicare tali nomi creati per le tuple, restituiti dalle proprietà o dai metodi pubblici. In questi casi, il compilatore aggiunge un attributo <xref:System.Runtime.CompilerServices.TupleElementNamesAttribute> al metodo. Questo attributo contiene una proprietà elenco <xref:System.Runtime.CompilerServices.TupleElementNamesAttribute.TransformNames> che presenta i nomi assegnati a ognuno degli elementi nella tupla.

> [!NOTE]
> Anche gli strumenti di sviluppo come Visual Studio consentono di leggere i metadati e di fornirli a IntelliSense e ad altre funzionalità tramite i nomi dei campi dei metadati.

È importante comprendere questi principi fondamentali delle nuove tuple e del tipo `ValueTuple` per comprendere le regole per la mutua assegnazione delle tuple con nome.

## <a name="tuple-projection-initializers"></a>Inizializzatori di proiezione tupla

In generale, gli inizializzatori di proiezione tupla funzionano utilizzando i nomi di variabile o campo dal lato destro di un'istruzione di inizializzazione della tupla.
Se viene fornito un nome esplicito, esso ha la precedenza su qualsiasi nome previsto. Nell'inizializzatore seguente, ad esempio, gli elementi sono `explicitFieldOne` e `explicitFieldTwo`, non `localVariableOne` e `localVariableTwo`:

[!code-csharp[ExplicitNamedTuple](../../samples/snippets/csharp/tuples/program.cs#ProjectionExample_Explicit "Explicitly named tuple")]

Per i campi in cui non viene specificato un nome esplicito, viene proiettato un nome implicito applicabile. Non è obbligatorio fornire nomi semantici, in modo esplicito o implicito. L'inizializzatore seguente ha nomi di campo `Item1` con valore `42`, e `stringContent` con valore "The answer to everything":

[!code-csharp[MixedTuple](../../samples/snippets/csharp/tuples/program.cs#MixedTuple "mixed tuple")]

Esistono due condizioni in cui i nomi dei campi candidati non sono previsti nel campo di tupla:

1. Quando il nome candidato è un nome di tupla riservato. Gli esempi includono `Item3` , `ToString` o `Rest` .
1. Quando il nome candidato è un duplicato di un altro nome di campo di tupla, implicito o esplicito.

Queste condizioni evitano ogni ambiguità. Questi nomi creerebbero un'ambiguità se utilizzati come nomi di campo per un campo in una tupla. Nessuna di queste condizioni causa errori in fase di compilazione. Al contrario, per gli elementi senza nomi previsti non esistono nomi semantici previsti.  Gli esempi seguenti illustrano queste condizioni:

[!code-csharp-interactive[Ambiguity](../../samples/snippets/csharp/tuples/program.cs#ProjectionAmbiguities "tuples where projections are not performed")]

Queste situazioni non causano errori del compilatore perché sarebbe una modifica di rilievo per il codice scritto con C# 7.0, quando le proiezioni dei nomi di campo di tupla non erano disponibili.

## <a name="equality-and-tuples"></a>Uguaglianza e tuple

A partire da C# 7.3, i tipi tupla supportano gli operatori `==` e `!=`. Questi operatori confrontano ogni membro dell'argomento a sinistra con ogni membro dell'argomento a destra in ordine. Questi confronti generano un corto circuito. Interromperanno la valutazione dei membri non appena una coppia è diversa. Gli esempi di codice seguenti usano `==`, ma tutte le regole di confronto si applicano anche a `!=`. L'esempio di codice seguente illustra un confronto di uguaglianza per due coppie di interi:

[!code-csharp-interactive[TupleEquality](../../samples/snippets/csharp/tuples/program.cs#Equality "Testing tuples for equality")]

Esistono diverse regole che rendono più comodi i test di uguaglianza delle tuple. I test di uguaglianza delle tuple eseguono [conversioni con elevazione](~/_csharplang/spec/conversions.md#lifted-conversion-operators) se una delle tuple è una tupla nullable, come illustrato nel codice seguente:

[!code-csharp-interactive[NullableTupleEquality](../../samples/snippets/csharp/tuples/program.cs#NullableEquality "Comparing Tuples and nullable tuples")]

I test di uguaglianza delle tuple eseguono anche conversioni implicite per ogni membro di entrambe le tuple, incluse conversioni con elevazione, conversioni verso un tipo di dati più grande o altre conversioni implicite. Gli esempi seguenti mostrano che una tupla a 2 elementi integer può essere confrontata con una tupla a 2 elementi long a causa della conversione implicita da integer a long:

[!code-csharp-interactive[SnippetMemberConversions](../../samples/snippets/csharp/tuples/program.cs#SnippetMemberConversions "converting tuples for equality tests")]

I nomi dei membri della tupla non partecipano ai test per l'uguaglianza. Tuttavia, se uno degli operandi è una valore letterale di tupla con nomi espliciti, il compilatore genera l'avviso CS8383 se tali nomi non corrispondono ai nomi dell'altro operando.
Nel caso in cui entrambi gli operandi sono valori letterali di tupla, l'avviso viene generato per l'operando di destra, come illustrato nell'esempio seguente:

[!code-csharp-interactive[MemberNames](../../samples/snippets/csharp/tuples/program.cs#SnippetMemberNames "Tuple member names do not participate in equality tests")]

Infine, le tuple possono contenere tuple annidate. L'uguaglianza delle tuple confronta la "forma" di ogni operando tramite tuple annidate, come illustrato nell'esempio seguente:

[!code-csharp-interactive[NestedTuples](../../samples/snippets/csharp/tuples/program.cs#SnippetNestedTuples "Tuples may contain nested tuples that participate in tuple equality.")]

È un errore di compilazione confrontare due tuple per verificarne l'uguaglianza (o la disuguaglianza) quando hanno forme diverse. Il compilatore non prova a decostruire le tuple annidate per confrontarle.

## <a name="assignment-and-tuples"></a>Assegnazione e tuple

Il linguaggio supporta l'assegnazione tra tipi tupla con lo stesso numero di elementi, in cui ogni elemento sul lato destro può essere convertito in modo implicito nell'elemento sul lato sinistro corrispondente. Non vengono considerate altre conversioni per le assegnazioni. È un errore in fase di compilazione assegnare una tupla a un'altra quando hanno forme diverse. Il compilatore non tenterà la decostruzione di tuple annidate per assegnarle.
Esaminiamo i tipi di assegnazioni consentiti tra i tipi di tupla.

Considerare le variabili usate negli esempi seguenti:

[!code-csharp[VariableCreation](../../samples/snippets/csharp/tuples/program.cs#03_VariableCreation "Variable creation")]

Le prime due variabili, `unnamed` e `anonymous`, non hanno nomi semantici forniti per gli elementi. I nomi dei campi sono `Item1` e `Item2`.
Le ultime due variabili, `named` e `differentName`, hanno nomi semantici attribuiti agli elementi. Queste due tuple presentano nomi diversi per gli elementi.

Tutte e quattro le tuple hanno lo stesso numero di elementi (noto come "cardinalità") e i tipi di tali elementi sono identici. Pertanto, tutte queste assegnazioni funzionano:

[!code-csharp[VariableAssignment](../../samples/snippets/csharp/tuples/program.cs#04_VariableAssignment "Variable assignment")]

Si noti che non sono assegnati i nomi delle tuple. I valori degli elementi vengono assegnati seguendo l'ordine degli elementi nella tupla.

Le tuple di tipi diversi o con numeri di elementi diversi non possono essere assegnate:

```csharp
// Does not compile.
// CS0029: Cannot assign Tuple(int,int,int) to Tuple(int, string)
var differentShape = (1, 2, 3);
named = differentShape;
```

## <a name="tuples-as-method-return-values"></a>Tuple come valori restituiti dal metodo

Uno degli usi più comuni per le tuple è come valore restituito da metodo. Di seguito viene illustrato un esempio. Si consideri il metodo che calcola la deviazione standard per una sequenza di numeri:

[!code-csharp[StandardDeviation](../../samples/snippets/csharp/tuples/statistics.cs#05_StandardDeviation "Compute Standard Deviation")]

> [!NOTE]
> Questi esempi calcolano la deviazione standard non corretta di esempio.
> La formula di deviazione standard non corretta di esempio consiste nel dividere la somma dei quadrati delle differenze rispetto al valore medio per (N-1) invece di N, come fa il metodo di estensione `Average`. Per altre informazioni sulle differenze tra queste formule di deviazione standard, consultare un testo di statistica.

Il codice precedente segue la formula canonica per la deviazione standard. Genera la risposta corretta, ma si tratta di un'implementazione inefficiente. Questo metodo enumera la sequenza due volte: una volta per produrre la media e una volta per produrre la media del quadrato della differenza della media.
Si noti che le query LINQ vengono valutate in modo differito, quindi il calcolo delle differenze rispetto al valore medio e la media tra tali differenze genera un'unica enumerazione.

Esiste una formula alternativa che calcola la deviazione standard usando solo un'enumerazione della sequenza.  Questo calcolo produce due valori durante l'enumerazione della sequenza: la somma di tutti gli elementi nella sequenza e la somma di ogni valore quadrato:

[!code-csharp[SumOfSquaresFormula](../../samples/snippets/csharp/tuples/statistics.cs#06_SumOfSquaresFormula "Compute Standard Deviation using the sum of squares")]

Questa versione enumera la sequenza esattamente una volta. Tuttavia, non si tratta di codice riutilizzabile. Continuando a lavorare, si scoprirà che numerosi calcoli statistici usano il numero di elementi nella sequenza, la somma della sequenza e la somma dei quadrati della sequenza. Eseguiamo il refactoring di questo metodo e scriviamo un metodo di utilità che produce tutti e tre questi valori. Tutti e tre i valori possono essere restituiti come tupla.

Aggiorniamo questo metodo in modo tale che i tre valori calcolati durante l'enumerazione vengano archiviati in una tupla. Questa operazione consente di creare questa versione:

[!code-csharp[TupleVersion](../../samples/snippets/csharp/tuples/statistics.cs#07_TupleVersion "Refactor to use tuples")]

Il supporto del refactoring di Visual Studio semplifica l'estrazione delle funzionalità per le statistiche principali in un metodo privato. Ciò offre un metodo `private static` che restituisce il tipo di tupla con tre valori di `Sum`, `SumOfSquares`, e `Count`:

[!code-csharp[TupleMethodVersion](../../samples/snippets/csharp/tuples/statistics.cs#08_TupleMethodVersion "After extracting utility method")]

Il linguaggio fornisce due opzioni aggiuntive che è possibile usare se si desidera apportare manualmente rapide modifiche. In primo luogo, è possibile usare la dichiarazione `var` per inizializzare il risultato della tupla dalla chiamata al metodo `ComputeSumAndSumOfSquares`. È anche possibile creare tre variabili discrete all'interno del metodo `ComputeSumAndSumOfSquares`. La versione finale è illustrata nel codice seguente:

[!code-csharp[CleanedTupleVersion](../../samples/snippets/csharp/tuples/statistics.cs#09_CleanedTupleVersion "After final cleanup")]

Questa versione finale può essere usata per qualsiasi metodo che necessiti di questi tre valori o di sottoinsiemi di essi.

Il linguaggio supporta altre opzioni per la gestione dei nomi degli elementi in questi metodi che restituiscono tuple.

È possibile rimuovere i nomi dei campi dalla dichiarazione di valore restituito e restituire una tupla senza nome:

```csharp
private static (double, double, int) ComputeSumAndSumOfSquares(IEnumerable<double> sequence)
{
    double sum = 0;
    double sumOfSquares = 0;
    int count = 0;

    foreach (var item in sequence)
    {
        count++;
        sum += item;
        sumOfSquares += item * item;
    }

    return (sum, sumOfSquares, count);
}
```

I campi di questa tupla sono denominati `Item1`, `Item2` e `Item3`.
Si consiglia di fornire nomi semantici agli elementi delle tuple restituite dai metodi.

Un altro contesto in cui le tuple possono risultare utili è durante la creazione di query LINQ. Il risultato proiettato finale spesso contiene alcune, ma non tutte le proprietà degli oggetti selezionati.

In genere, i risultati della query vengono proiettati in una sequenza di oggetti del tipo anonimo. Ciò presenta numerose limitazioni, principalmente perché i tipi anonimi non possono essere facilmente denominati nel tipo restituito per un metodo. In alternativa, usare `object` o `dynamic` come tipo del risultato offre costi significativi in termini di prestazioni.

La restituzione di una sequenza di un tipo di tupla è semplice e i nomi e i tipi degli elementi sono disponibili in fase di compilazione e tramite gli strumenti IDE.
Si consideri, ad esempio, un'applicazione ToDo. È possibile definire una classe simile alla seguente per rappresentare una singola voce nell'elenco ToDo:

[!code-csharp[ToDoItem](../../samples/snippets/csharp/tuples/projectionsample.cs#14_ToDoItem "To Do Item")]

Le applicazioni per dispositivi mobili possono supportare un modulo compresso delle voci ToDo correnti che visualizza solo il titolo. Questa query LINQ genera una proiezione che include solo l'ID e il titolo. Un metodo che restituisce una sequenza di tuple esprime in maniera accurata questa struttura:

[!code-csharp[QueryReturningTuple](../../samples/snippets/csharp/tuples/projectionsample.cs#15_QueryReturningTuple "Query returning a tuple")]

> [!NOTE]
> In C# 7.1, le proiezioni di tupla consentono di creare tuple con nome utilizzando gli elementi, in modo simile alla denominazione di proprietà in tipi anonimi. Nel codice precedente, l'istruzione `select` nella proiezione di query crea una tupla che contiene elementi `ID` e `Title`.

La tupla con nome può essere parte della firma. Consente al compilatore e agli strumenti IDE di garantire in modo statico che si sta usando correttamente il risultato. La tupla con nome contiene anche le informazioni sul tipo statico in modo da eliminare la necessità di usare le costose funzionalità di runtime quali la reflection o l'associazione dinamica al fine di lavorare con i risultati.

## <a name="deconstruction"></a>Decostruzione

È possibile decomprimere tutte le voci in una tupla *decostruendo* la tupla restituita da un metodo. Per la decostruzione delle tuple esistono tre diversi approcci.  È prima possibile dichiarare il tipo di ogni campo all'interno di parentesi per creare variabili discrete per ognuno degli elementi nella tupla:

[!code-csharp[Deconstruct](../../samples/snippets/csharp/tuples/statistics.cs#10_Deconstruct "Deconstruct")]

È anche possibile dichiarare variabili tipizzate in modo implicito per ogni campo in una tupla usando la parola chiave `var` all'esterno delle parentesi:

[!code-csharp[DeconstructToVar](../../samples/snippets/csharp/tuples/statistics.cs#11_DeconstructToVar "Deconstruct to Var")]

In aggiunta, è possibile usare la parola chiave `var` con una o tutte le dichiarazioni di variabili all'interno delle parentesi.

```csharp
(double sum, var sumOfSquares, var count) = ComputeSumAndSumOfSquares(sequence);
```

Non è possibile usare un tipo specifico all'esterno delle parentesi, anche se ogni campo nella tupla presenta lo stesso tipo.

È possibile decostruire le tuple anche con le dichiarazioni esistenti:

```csharp
public class Point
{
    public int X { get; set; }
    public int Y { get; set; }

    public Point(int x, int y) => (X, Y) = (x, y);
}
```

> [!WARNING]
> Non è possibile combinare le dichiarazioni esistenti con dichiarazioni all'interno di parentesi. Ad esempio, la dichiarazione seguente non è consentita: `(var x, y) = MyMethod();`. Questa operazione genera un errore CS8184 perché *x* è dichiarato all'interno delle parentesi e *y* è già stato dichiarato in precedenza in un'altra posizione.

### <a name="deconstructing-user-defined-types"></a>Decostruzione dei tipi definiti dall'utente

Qualsiasi tipo di tupla può essere decostruito come illustrato in precedenza. È anche semplice abilitare la decostruzione sui tipi definiti dall'utente (classi, struct o perfino interfacce).

L'autore del tipo può definire uno o più `Deconstruct` metodi che assegnano valori a un numero qualsiasi di [ `out` variabili](language-reference/keywords/out-parameter-modifier.md) che rappresentano gli elementi dati che compongono il tipo. Ad esempio, il tipo `Person` seguente definisce un metodo `Deconstruct` che decostruisce un oggetto persona negli elementi che ne rappresentano nome e cognome:

[!code-csharp[TypeWithDeconstructMethod](../../samples/snippets/csharp/tuples/person.cs#12_TypeWithDeconstructMethod "Type with a deconstruct method")]

Il metodo di decostruzione consente l'assegnazione da un `Person` a due stringhe, che rappresentano le proprietà `FirstName` e `LastName`:

[!code-csharp[Deconstruct Type](../../samples/snippets/csharp/tuples/program.cs#12A_DeconstructType "Deconstruct a class type")]

È possibile abilitare la decostruzione anche per i tipi non creati dall'utente.
Il metodo `Deconstruct` può essere un metodo di estensione che decomprime i membri di dati accessibili di un oggetto. L'esempio seguente mostra un tipo `Student`, derivato dal tipo `Person` e un metodo di estensione che decostruisce un `Student` in tre variabili, che rappresentano `FirstName`, `LastName` e `GPA`:

[!code-csharp[ExtensionDeconstructMethod](../../samples/snippets/csharp/tuples/person.cs#13_ExtensionDeconstructMethod "Type with a deconstruct extension method")]

Un oggetto `Student` dispone ora di due metodi `Deconstruct` di accesso: il metodo di estensione dichiarato per i tipi `Student` e i membri del tipo `Person`. Entrambi appartengono all'ambito, consentendo la decostruzione di un `Student` in due o tre variabili.
Se si assegna uno studente a tre variabili, vengono restituiti nome, cognome e GPA. Se si assegna uno studente a due variabili, vengono restituiti solo nome e cognome.

[!code-csharp[Deconstruct extension method](../../samples/snippets/csharp/tuples/program.cs#13A_DeconstructExtension "Deconstruct a class type using an extension method")]

È necessario prestare attenzione alla definizione di più metodi `Deconstruct` in una classe o in una gerarchia di classi. Più metodi `Deconstruct` che presentano lo stesso numero di parametri `out` possono rapidamente causare ambiguità. I chiamanti potrebbero non essere in grado di eseguire facilmente chiamate al metodo `Deconstruct` desiderato.

In questo esempio, vi è una minima possibilità di chiamata ambigua perché il metodo `Deconstruct` per `Person` ha due parametri di output e il metodo `Deconstruct` per `Student` ne ha tre.

Gli operatori di decostruzione non partecipano ai test di uguaglianza. L'esempio seguente genera l'errore di compilazione CS0019:

```csharp
Person p = new Person("Althea", "Goodwin");
if (("Althea", "Goodwin") == p)
    Console.WriteLine(p);
```

Il metodo `Deconstruct` potrebbe convertire l'oggetto `Person``p` in una tupla che contiene due stringhe, ma ciò non è applicabile nel contesto dei test di uguaglianza.

## <a name="tuples-as-out-parameters"></a>Tuple come parametri out

Le tuple possono essere utilizzate come [ `out` parametri](language-reference/keywords/out-parameter-modifier.md) *.* Da non confondere con qualsiasi ambiguità citata in precedenza nella sezione [decostruzione](#deconstruction) . In una chiamata al metodo è necessario descrivere solo la forma della tupla:

[!code-csharp[TuplesAsOutParameters](~/samples/snippets/csharp/tuples/program.cs#01_TupleAsOutVariable "Tuples as out parameters")]

In alternativa, è possibile utilizzare una tupla [_senza nome_](#named-and-unnamed-tuples) e fare riferimento ai relativi campi come `Item1` e `Item2` :

```csharp
dict.TryGetValue(2, out (int, string) pair);
// ...
Console.WriteLine($"{pair.Item1}: {pair.Item2}");
```

## <a name="conclusion"></a>Conclusioni

Il nuovo supporto per linguaggio e libreria per le tuple con nome rende più semplice lavorare con schemi che usano strutture di dati che archiviano più elementi, ma non definiscono il comportamento, come le classi e gli struct. Usare le tuple per questi tipi è semplice e veloce. Si ottengono tutti i vantaggi del controllo del tipo statico, senza la necessità di creare tipi tramite la sintassi più dettagliata `class` o `struct`. Anche in questo caso, risultano particolarmente utili per i metodi di utilità `private` o `internal`. Creare tipi definiti dall'utente, tipi `class` o `struct` quando i metodi pubblici restituiscono un valore che contiene più elementi.
