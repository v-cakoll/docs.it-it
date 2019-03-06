---
title: Matrici in Visual Basic
ms.date: 12/06/2017
f1_keywords:
  - vb.Array
helpviewer_keywords:
  - 'arrays [Visual Basic]'
  - 'Visual Basic, arrays'
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
---

# <a name="arrays-in-visual-basic"></a>Matrici in Visual Basic

Una matrice è un set di valori, che sono suddivisi *elementi*, che sono correlate logicamente tra loro. Ad esempio, può essere costituito da una matrice del numero di studenti iscritti a ciascun anno scolastico di una scuola elementare; ogni elemento della matrice è il numero di studenti in un singolo livello. Analogamente, può essere costituito da una matrice di voti di uno studente per una classe. ogni elemento della matrice è un singolo livello.

È possibile singole variabili per archiviare ogni elementi di dati. Ad esempio, se l'applicazione analizza valutazioni dello studente, è possibile usare una variabile separata per ogni valutazione dello studente, ad esempio `englishGrade1`, `englishGrade2`e così via. Questo approccio presenta tre limitazioni principali:

- È necessario sapere in fase di progettazione esattamente quante valutazioni dobbiamo gestire.
- Gestisce un numero elevato di voti rapidamente diventa difficile da gestire. Ciò rende a sua volta un'applicazione molto più probabile contenere bug gravi.
- È difficile da gestire. Ogni livello nuovo che aggiungiamo richiede che l'applicazione essere modificata, ricompilata e ridistribuita.

Usando una matrice, è possibile fare riferimento a questi valori correlati mediante lo stesso nome e usare un numero che viene chiamato un' *indice* oppure *pedice* per identificare un singolo elemento in base alla posizione nella matrice. Gli indici di una matrice sono compresi tra 0 per il numero totale di elementi della matrice meno uno. Quando si usa Visual Basic sintassi per definire le dimensioni di una matrice, specificare il relativo indice più alto, non il numero totale di elementi nella matrice. È possibile usare la matrice come un'unità e la possibilità di eseguire l'iterazione dei relativi elementi si evita di dover conoscere esattamente quanti elementi in esso contenuti in fase di progettazione.

Di seguito sono riportati alcuni esempi:

```vb
' Declare a single-dimension array of 5 numbers.
Dim numbers(4) As Integer

'Declare a single-dimension array and set its 4 values.
Dim numbers = New Integer() {1, 2, 4, 8}

' Change the size of an existing array to 16 elements and retain the current values.
ReDim Preserve numbers(15)

' Redefine the size of an existing array and reset the values.
ReDim numbers(15)

' Declare a 6 x 6 multidimensional array.
Dim matrix(5, 5) As Double

' Declare a 4 x 3 multidimensional array and set array element values.
Dim matrix = New Integer(3, 2) {{1, 2, 3}, {2, 3, 4}, {3, 4, 5}, {4, 5, 6}}

' Declare a jagged array
Dim sales()() As Double = New Double(11)() {}
```

## <a name="array-elements-in-a-simple-array"></a>Elementi della matrice in una matrice semplice

È possibile creare una matrice denominata `students` per archiviare il numero degli studenti iscritti a ciascun anno scolastico di una scuola elementare. Gli indici degli elementi sono compresi tra 0 e 6. L'uso di questa matrice è più semplice rispetto alla dichiarazione di sette variabili.

La figura seguente illustra il `students` matrice. Per ogni elemento della matrice:

- L'indice dell'elemento rappresenta l'anno scolastico (l'indice 0 rappresenta l'asilo).

- Il valore contenuto nell'elemento rappresenta il numero degli studenti iscritti a tale anno scolastico.

![Immagine di matrice che illustra il numero di studenti](../../language-features/arrays/media/arrayexampleschool.gif "ArrayExampleSchool") elementi della matrice "students"

L'esempio seguente contiene il codice Visual Basic che crea e Usa la matrice:

[!code-vb[simple-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]

L'esempio effettua tre operazioni:

- Dichiara un `students` matrice con sette elementi. Il numero `6` nella matrice di dichiarazione indica l'ultimo indice nella matrice; uno è minore del numero di elementi nella matrice.
- Assegna valori a ogni elemento nella matrice. Gli elementi della matrice sono accessibili tramite il nome della matrice e includendo l'indice dell'elemento singole racchiuso tra parentesi.
- Elenca ogni valore della matrice. L'esempio Usa un' [ `For` ](../../../language-reference/statements/for-next-statement.md) istruzione per accedere a ogni elemento della matrice dal relativo numero di indice.

Il `students` matrice nell'esempio precedente è una matrice unidimensionale, perché usa un indice. Matrice che usa più di un indice o indice viene chiamata *multidimensionali*. Per altre informazioni, vedere il resto di questo articolo e [Array Dimensions in Visual Basic](../../language-features/arrays/array-dimensions.md).

## <a name="creating-an-array"></a>Creazione di una matrice

È possibile definire le dimensioni della matrice in diversi modi:

- È possibile specificare le dimensioni quando la matrice viene dichiarata:

  [!code-vb[creating1](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]

- È possibile usare un `New` clausola per specificare la dimensione di una matrice al momento della creazione:

  [!code-vb[creating2](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]

Se si dispone di una matrice esistente, è possibile ridefinirne la dimensione utilizzando la [ `ReDim` ](../../../language-reference/statements/redim-statement.md) istruzione. È possibile specificare che il `ReDim` istruzione mantenere i valori nella matrice o è possibile specificare la creazione di una matrice vuota. L'esempio seguente illustra vari modi di usare l'istruzione `ReDim` per modificare la dimensione di una matrice esistente.

[!code-vb[redimensioning](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]

Per altre informazioni, vedere la [istruzione ReDim](../../../language-reference/statements/redim-statement.md).

## <a name="storing-values-in-an-array"></a>Archiviazione di valori in una matrice

È possibile accedere a ogni posizione in una matrice usando un indice di tipo `Integer`. È possibile archiviare e recuperare i valori in una matrice facendo riferimento a ogni posizione della matrice tramite il relativo indice racchiuso tra parentesi. Gli indici per le matrici multidimensionali sono separati da virgole (,). È necessario un indice per ogni dimensione della matrice.

Nell'esempio seguente illustra alcune istruzioni che archiviano e recuperano i valori nelle matrici.

[!code-vb[store-and-retrieve](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]

## <a name="populating-an-array-with-array-literals"></a>Popolamento di una matrice con valori letterali di matrice

Usando un valore letterale di matrice, è possibile popolare una matrice con un set iniziale di valori nello stesso momento creazione. Un valore letterale di matrice è costituito da un elenco di valori delimitati da virgole racchiusi tra parentesi graffe (`{}`).

Quando si usa un valore letterale di matrice per creare una matrice, è possibile specificare il tipo o usare l'inferenza del tipo per determinare il tipo di matrice. Nell'esempio seguente illustra entrambe le opzioni.

[!code-vb[create-with-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]

Quando si usa l'inferenza del tipo, il tipo della matrice è determinato dal *tipo dominante* nell'elenco di valori letterali. Il tipo dominante è il tipo a cui è possono ingrandire tutti gli altri tipi nella matrice. Se non è possibile determinare il tipo univoco, il tipo dominante è il tipo univoco in cui possono restringersi tutti gli altri tipi nella matrice. Se nessuno di questi tipi univoci può essere determinato, il tipo dominante è `Object`. Se, ad esempio, l'elenco di valori fornito al valore letterale di matrice contiene valori di tipo `Integer`, `Long`e `Double`, la matrice risultante è di tipo `Double`. In quanto `Integer` e `Long` possono ampliarsi solo nel `Double`, `Double` è il tipo dominante. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../language-features/data-types/widening-and-narrowing-conversions.md).

> [!NOTE]
> È possibile usare l'inferenza del tipo solo per le matrici che sono definite come variabili locali in un membro del tipo. Se è presente una definizione di tipo esplicito, le matrici definite con valori letterali di matrice a livello di classe sono di tipo `Object[]`. Per altre informazioni, vedere [inferenza del tipo locale](../variables/local-type-inference.md).

Si noti che nell'esempio precedente viene definito `values` come una matrice di tipo `Double` anche se tutti i valori letterali della matrice sono di tipo `Integer`. È possibile creare questa matrice perché i valori nel valore letterale di matrice possono ampliarsi `Double` valori.

È anche possibile creare e popolare una matrice multidimensionale usando *valori letterali di matrice annidati*. Valori letterali di matrice annidati devono avere un numero di dimensioni che è coerenza con la matrice risultante. L'esempio seguente crea una matrice bidimensionale di interi con valori letterali di matrice annidati.

[!code-vb[nested-array-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]

Quando si usano valori letterali di matrice annidati per creare e popolare una matrice, si verifica un errore se il numero di elementi nei valori letterali di matrice annidati non corrisponda. Si verifica un errore anche se si dichiara in modo esplicito la variabile di matrice per avere un numero diverso di dimensioni rispetto a valori letterali della matrice.

Proprio come per le matrici unidimensionali, è possibile basarsi sull'inferenza del tipo durante la creazione di una matrice multidimensionale con valori letterali di matrice annidati. Il tipo dedotto è il tipo dominante per tutti i valori in tutti i valori letterali di matrice per tutti i livello di nidificazione. L'esempio seguente crea una matrice bidimensionale di tipo `Double[,]` dai valori di tipo `Integer` e `Double`.

[!code-vb[nested-type-inference](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]

Per altri esempi, vedere [come: Inizializzare una variabile di matrice in Visual Basic](../../language-features/arrays/how-to-initialize-an-array-variable.md).

## <a name="iterating-through-an-array"></a>Iterazione su una matrice

Quando si scorre una matrice, accedere a ogni elemento nella matrice dall'indice più basso al più elevato o dal valore massimo a quello minimo. In genere, utilizzare il [per... Istruzione successiva](../../../language-reference/statements/for-next-statement.md) o il [For Each... Istruzione Next](../../../language-reference/statements/for-each-next-statement.md) per scorrere gli elementi della matrice. Quando non si conoscono i limiti superiori della matrice, è possibile chiamare il <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> metodo per ottenere il valore massimo dell'indice. Anche se il valore di indice più basso è quasi sempre 0, è possibile chiamare il <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> metodo per ottenere il valore più basso dell'indice.

Nell'esempio seguente scorre una matrice unidimensionale usando il [ `For...Next` ](../../../language-reference/statements/for-next-statement.md) istruzione.

[!code-vb[iterate-one-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]

Nell'esempio seguente scorre una matrice multidimensionale usando un [ `For...Next` ](../../../language-reference/statements/for-next-statement.md) istruzione. Il metodo <xref:System.Array.GetUpperBound%2A> ha un parametro che specifica la dimensione. `GetUpperBound(0)` Restituisce l'indice più alto della prima dimensione, e `GetUpperBound(1)` restituisce l'indice più alto della seconda dimensione.

[!code-vb[iterate-two-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]

L'esempio seguente usa un [For Each... Istruzione Next](../../../language-reference/statements/for-each-next-statement.md)per scorrere una matrice unidimensionale e una matrice bidimensionale.

[!code-vb[iterate-for-each-next](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]

## <a name="array-size"></a>Dimensione della matrice

La dimensione di una matrice è il prodotto delle lunghezze di tutte le relative dimensioni e rappresenta il numero totale di elementi attualmente contenuti nella matrice.  Ad esempio, nell'esempio seguente dichiara una matrice bidimensionale con 2 con quattro elementi in ogni dimensione. Come illustrato nell'output dell'esempio, le dimensioni della matrice sono 16 (o (3 + 1) * (3 + 1).

[!code-vb[array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]

> [!NOTE]
> Questa discussione di dimensione della matrice non è applicabile per le matrici di matrici. Per informazioni sulle matrici di matrici e determinare le dimensioni di una matrice di matrici, vedere la [matrici irregolari](#jagged-arrays) sezione.

È possibile determinare le dimensioni di una matrice usando la proprietà <xref:System.Array.Length%2A?displayProperty=nameWithType>. È possibile trovare la lunghezza di ogni dimensione di una matrice multidimensionale usando il <xref:System.Array.GetLength%2A?displayProperty=nameWithType> (metodo).

È possibile ridimensionare una variabile di matrice tramite l'assegnazione di un nuovo oggetto matrice ad esso o usando il [ `ReDim` istruzione](../../../language-reference/statements/redim-statement.md) istruzione. L'esempio seguente usa il `ReDim` istruzione per modificare una matrice di 100 elementi in una matrice di elementi 51.

[!code-vb[resize-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]

Di seguito sono indicati alcuni elementi importanti relativi alla dimensione di una matrice.

|||
|---|---|
|Lunghezza delle dimensioni|L'indice di ogni dimensione è basato su 0, ovvero che compreso tra 0 e il limite superiore. Pertanto, la lunghezza di una determinata dimensione è maggiore di uno rispetto al limite superiore dichiarato di tale dimensione.|
|Limiti di lunghezza|La lunghezza di ogni dimensione di una matrice è limitata al valore massimo dei `Integer` tipo di dati, ovvero <xref:System.Int32.MaxValue?displayProperty=nameWithType> o (2 ^ 31) - 1. La dimensione totale di una matrice, tuttavia, è limitata anche dalla memoria disponibile nel sistema. Se si tenta di inizializzare una matrice che supera la quantità di memoria disponibile, il runtime genera un <xref:System.OutOfMemoryException>.|
|Dimensione ed elementi della matrice|La dimensione di una matrice è indipendente dal tipo di dati dei relativi elementi. La dimensione rappresenta sempre il numero totale di elementi, non il numero di byte che consumano una quantità di memoria.|
|Consumo di memoria|Non è possibile fare ipotesi sulla modalità di archiviazione di una matrice in memoria. L'archiviazione dipende dalla larghezza dei dati delle diverse piattaforme. Di conseguenza, è possibile che l'archiviazione di una stessa matrice richieda più memoria in un sistema a 64 bit che in un sistema a 32 bit. A seconda della configurazione di sistema al momento dell'inizializzazione di una matrice, Common Language Runtime (CLR) può assegnare la memoria in modo da compattare al massimo gli elementi oppure in modo da allinearli tutti in base ai limiti dell'hardware. Per le informazioni di controllo di una matrice è richiesto un sovraccarico di archiviazione che aumenta con ogni dimensione aggiunta.|

## <a name="the-array-type"></a>Il tipo di matrice

Ogni matrice ha un tipo di dati che è diverso dal tipo di dati dei relativi elementi. Non esiste un singolo tipo di dati per tutte le matrici. Il tipo di dati di una matrice viene invece determinato dal numero di dimensioni, o *rango*, della matrice e dal tipo di dati degli elementi nella matrice. Due variabili di matrice sono degli stessi dati digitare solo se hanno lo stesso rango e i relativi elementi hanno gli stessi dati di tipo. Le lunghezze delle dimensioni di una matrice non influenzano il tipo di dati della matrice.

Ogni matrice eredita dalla classe <xref:System.Array?displayProperty=nameWithType>. È possibile dichiarare una variabile di tipo `Array`, ma non è possibile creare una matrice di tipo `Array`. Ad esempio, anche se il codice seguente viene dichiarata la `arr` variabile di tipo `Array` e chiama il <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> metodo per creare un'istanza di matrice, il tipo della matrice è senza dubbio Object [].

[!code-vb[array-class](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)]

L'[istruzione ReDim](../../../language-reference/statements/redim-statement.md) non può inoltre operare su una variabile dichiarata di tipo `Array`. Per questi motivi e indipendente dai tipi, è consigliabile dichiarare ogni matrice come un tipo specifico.

È possibile determinare il tipo di dati di una matrice o dei relativi elementi in diversi modi.

- È possibile chiamare il <xref:System.Object.GetType%2A> metodo sulla variabile per ottenere un <xref:System.Type> oggetto che rappresenta il tipo di runtime della variabile. Nelle proprietà e nei metodi dell'oggetto <xref:System.Type> sono presenti informazioni complete.
- È possibile passare la variabile per il <xref:Microsoft.VisualBasic.Information.TypeName%2A> funzione per ottenere un `String` con il nome del tipo di runtime.

Nell'esempio seguente chiama la sia la `GetType` (metodo) e il `TypeName` funzione per determinare il tipo di matrice. Il tipo di matrice è `Byte(,)`. Si noti che il <xref:System.Type.BaseType%2A?displayProperty=nameWithType> proprietà indica anche che il tipo di base della matrice di byte è il <xref:System.Array> classe.

[!code-vb[array-type](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]

## <a name="arrays-as-return-values-and-parameters"></a>Matrici come valori restituiti e parametri

Per restituire una matrice da una routine `Function`, specificare il tipo di dati della matrice e il numero di dimensioni come tipo restituito dell'[istruzione Function](../../../language-reference/statements/function-statement.md). All'interno della funzione dichiarare una variabile di matrice locale con lo stesso tipo di dati degli elementi e lo stesso numero di dimensioni. Includere la variabile di matrice locale senza parentesi nell'[istruzione Return](../../../language-reference/statements/return-statement.md).

Per specificare una matrice come parametro in una routine `Sub` o `Function` , definire il parametro come matrice con un tipo di dati e un numero di dimensioni specificati. Nella chiamata alla procedura, passare una variabile di matrice con lo stesso tipo di dati e il numero di dimensioni.

Nell'esempio seguente, il `GetNumbers` funzione restituisce un `Integer()`, una matrice unidimensionale di tipo `Integer`. La routine `ShowNumbers` accetta un argomento `Integer()` .

[!code-vb[return-value-and-params](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]

Nell'esempio seguente, il `GetNumbersMultiDim` funzione restituisce un `Integer(,)`, una matrice bidimensionale di tipo `Integer`.  La routine `ShowNumbersMultiDim` accetta un argomento `Integer(,)` .

[!code-vb[multidimensional-return-value](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]

## <a name="jagged-arrays"></a>Matrici di matrici

In alcuni casi la struttura dei dati nell'applicazione è bidimensionale, ma non rettangolare. Ad esempio, si potrebbe usare una matrice per archiviare i dati sulla temperatura massima di ogni giorno del mese. La prima dimensione della matrice rappresenta il mese, ma la seconda dimensione rappresenta il numero di giorni e il numero di giorni in un mese non è uniforme. Oggetto *matrice di matrici*, che viene chiamato anche un' *matrice di matrici*, è progettato per questi scenari. Una matrice irregolare è una matrice i cui elementi sono anche le matrici. Una matrice irregolare e ogni elemento di una matrice irregolare possono avere una o più dimensioni.

L'esempio seguente usa una matrice di mesi, ogni elemento del quale è una matrice di giorni. L'esempio Usa una matrice di matrici in quanto mesi diversi hanno numeri di giorni diversi.  Nell'esempio viene illustrato come creare una matrice di matrici, assegnare i valori e recuperare e visualizzare i relativi valori.

[!code-vb[jagged-arrays](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]

Nell'esempio precedente assegna valori alla matrice di matrici in un elemento per elemento di base usando un `For...Next` ciclo. È anche possibile assegnare valori agli elementi di una matrice di matrici tramite valori letterali di matrice annidati. Tuttavia, il tentativo di usare annidati valori letterali di matrice (ad esempio, `Dim valuesjagged = {{1, 2}, {2, 3, 4}}`) genera l'errore del compilatore [BC30568](../../../,,/../misc/bc30568.md). Per correggere l'errore, racchiudere i valori letterali di matrice interni tra parentesi. Le parentesi forzano l'espressione letterale di matrice deve essere valutata e i valori risultanti vengono usati con la matrice esterna letterale, come illustrato nell'esempio seguente.

[!code-vb[jagged-array-initialization](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)]

Una matrice di matrici è una matrice unidimensionale il cui elementi contengono le matrici. Pertanto, il <xref:System.Array.Length%2A?displayProperty=nameWithType> proprietà e il `Array.GetLength(0)` metodo restituisce il numero di elementi nella matrice unidimensionale, e `Array.GetLength(1)` genera un <xref:System.IndexOutOfRangeException> perché una matrice di matrici non è multidimensionale. Determinare il numero di elementi in ogni matrice secondaria recuperando il valore di ogni sottomatrice <xref:System.Array.Length%2A?displayProperty=nameWithType> proprietà. L'esempio seguente illustra come determinare il numero di elementi in una matrice di matrici.

[!code-vb[jagged-array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)]

## <a name="zero-length-arrays"></a>Matrici di lunghezza zero

Visual Basic consente di distinguere tra una matrice non inizializzata (una matrice il cui valore è `Nothing`) e una *matrice di lunghezza zero* oppure matrice vuota (una matrice senza elementi). Una matrice non inizializzata è uno che non è stata dimensionata o avevano tutti i valori assegnati a esso. Ad esempio:

```vb
Dim arr() As String
```

Una matrice di lunghezza zero è dichiarata con una dimensione di -1. Ad esempio:

```vb
Dim arrZ(-1) As String
```

Potrebbe essere necessario creare una matrice di lunghezza zero nelle circostanze seguenti:

- Senza rischiare un <xref:System.NullReferenceException> eccezione, il codice deve accedere ai membri del <xref:System.Array> classe, ad esempio <xref:System.Array.Length%2A> oppure <xref:System.Array.Rank%2A>, o chiamare una funzione di Visual Basic, ad esempio <xref:Microsoft.VisualBasic.Information.UBound%2A>.

- Si vuole mantenere il codice semplice da non dover cercare `Nothing` come caso speciale.

- Il codice interagisce con un'API (Application Programming Interface) che richiede il passaggio di una matrice di lunghezza zero a una o più routine oppure che restituisce una matrice di lunghezza zero da una o più routine.

## <a name="splitting-an-array"></a>Suddivisione di una matrice

In alcuni casi, potrebbe essere necessario suddividere una singola matrice più array. Ciò comporta che identifica il punto o i punti in corrispondenza del quale la matrice deve essere suddiviso e quindi sputare della matrice in due o più matrici separate.

> [!NOTE]
> In questa sezione non viene illustrata la suddivisione di una singola stringa in una matrice di stringhe in base a un delimitatore. Per informazioni sulla suddivisione di una stringa, vedere il <xref:System.String.Split%2A?displayProperty=nameWithType> (metodo).

I criteri più comuni per la suddivisione di una matrice sono:

- Numero di elementi nella matrice. Ad esempio, è possibile suddividere una matrice di più di un numero specificato di elementi in un numero di circa parti uguali. A tale scopo, è possibile usare il valore restituito in uno dei modi il <xref:System.Array.Length%2A?displayProperty=nameWithType> o <xref:System.Array.GetLength%2A?displayProperty=nameWithType> (metodo).

- Il valore di un elemento, che funge da un delimitatore che indica dove la matrice deve essere suddivisa. È possibile cercare un valore specifico chiamando il <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> e <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> metodi.

Dopo aver determinato l'indice o gli indici in corrispondenza del quale la matrice deve essere suddiviso, quindi è possibile creare matrici singole chiamando il <xref:System.Array.Copy%2A?displayProperty=nameWithType> (metodo).

Nell'esempio seguente suddivide una matrice in due matrici di dimensioni simili. (Se il numero totale di elementi della matrice è dispari, la prima matrice ha un elemento in più rispetto al secondo).

[!code-vb[splitting-an-array-by-length](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)]

Nell'esempio seguente suddivide una matrice di stringhe in due matrici in base alla presenza di un elemento il cui valore è "zzz", che viene utilizzata come delimitatore di matrice. Le nuove matrici non includono l'elemento che contiene il delimitatore.

[!code-vb[splitting-an-array-by-delimiter](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)]

## <a name="joining-arrays"></a>Aggiunta di matrici

È anche possibile combinare un numero di matrici in una singola matrice di dimensioni maggiori. A tale scopo, utilizziamo inoltre il <xref:System.Array.Copy%2A?displayProperty=nameWithType> (metodo).

> [!NOTE]
> In questa sezione non viene illustrata l'aggiunta di una matrice di stringhe in un'unica stringa. Per informazioni sull'aggiunta di una matrice di stringhe, vedere il <xref:System.String.Join%2A?displayProperty=nameWithType> (metodo).

Prima di copiare gli elementi di ogni matrice nella matrice di nuovo, è necessario assicurarsi che è stata inizializzata la matrice in modo che sia grande abbastanza da contenere la nuova matrice. Questa operazione può essere eseguita in due modi:

- Usare la [ `ReDim Preserve` ](../../../language-reference/statements/redim-statement.md) espandere in modo dinamico la matrice prima di aggiungervi nuovi elementi dell'istruzione. Si tratta della tecnica più semplice, ma può comportare una riduzione delle prestazioni e utilizzo di memoria eccessiva quando si copiano le matrici di grandi dimensioni.
- Calcolare il numero totale di elementi necessari per la nuova matrice di grandi dimensioni, quindi aggiungere gli elementi di ogni matrice di origine a esso.

Nell'esempio seguente usa il secondo approccio per aggiungere quattro matrici con dieci elementi in una singola matrice.

[!code-vb[joining-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)]

Poiché in questo caso le matrici di origine sono tutti piccole, è possibile espandere inoltre in modo dinamico la matrice man mano che si aggiungono gli elementi di ogni nuova matrice a esso. Nell'esempio seguente viene eseguita questa operazione.

[!code-vb[joining-an-array-dynamically](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)]

## <a name="collections-as-an-alternative-to-arrays"></a>Raccolte come alternativa alle matrici

Le matrici sono estremamente utili per la creazione e l'uso di un numero fisso di oggetti fortemente tipizzati. Le raccolte consentono di lavorare in modo più flessibile con gruppi di oggetti. A differenza delle matrici, che richiede che si modificano in modo esplicito le dimensioni di una matrice con il [ `ReDim` istruzione](../../../language-reference/statements/redim-statement.md), raccolte di aumentare e diminuire dinamicamente in base alle esigenze di un'applicazione viene modificata.

Quando si usa `ReDim` per ridimensionare una matrice, Visual Basic crea una nuova matrice e rilascia in quella precedente. Questa operazione causa un aumento del tempo di esecuzione. Pertanto, se il numero di elementi che si sta lavorando cambia spesso oppure è possibile prevedere il numero massimo di elementi che necessari, è in genere sarà ottenere prestazioni migliori usando una raccolta.

Per alcune raccolte è possibile assegnare una chiave a qualsiasi oggetto inserito nella raccolta in modo da recuperare rapidamente l'oggetto usando la chiave.

Se la raccolta contiene elementi di un solo tipo di dati, è possibile usare una delle classi nello spazio dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType> . In una raccolta generica viene imposta l'indipendenza dai tipi, in modo da impedire che vengano aggiunti altri tipi di dati alla raccolta.

Per altre informazioni sulle raccolte, vedere [Raccolte](../../concepts/collections.md).

## <a name="related-topics"></a>Argomenti correlati

|Termine|Definizione|
|----------|----------------|
|[Array Dimensions in Visual Basic](../../language-features/arrays/array-dimensions.md)|Illustra il numero di dimensioni, o rango, e le dimensioni delle matrici.|
|[Procedura: Inizializzare una variabile di matrice in Visual Basic](../../language-features/arrays/how-to-initialize-an-array-variable.md)|Descrive come popolare le matrici con valori iniziali.|
|[Procedura: Sort An Array in Visual Basic](../../language-features/arrays/how-to-sort-an-array.md)|Illustra come ordinare alfabeticamente gli elementi di una matrice.|
|[Procedura: Assegnare una matrice a un'altra matrice](../../language-features/arrays/how-to-assign-one-array-to-another-array.md)|Descrive regole e passaggi per l'assegnazione di una matrice a un'altra variabile di matrice.|
|[Risoluzione dei problemi relativi alle matrici](../../language-features/arrays/troubleshooting-arrays.md)|Illustra alcuni problemi comuni che si verificano quando si usano le matrici.|

## <a name="see-also"></a>Vedere anche

- <xref:System.Array?displayProperty=nameWithType>
- [Istruzione Dim](../../../language-reference/statements/dim-statement.md)
- [Istruzione ReDim](../../../language-reference/statements/redim-statement.md)
