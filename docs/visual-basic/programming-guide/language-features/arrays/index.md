---
title: Matrici
ms.date: 12/06/2017
f1_keywords:
- vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
ms.openlocfilehash: 5093f28f05c5b72294dce9a4e69723acafb31a9f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413092"
---
# <a name="arrays-in-visual-basic"></a>Matrici in Visual Basic

Una matrice è un set di valori, che sono *elementi*definiti, che sono logicamente correlati tra loro. Una matrice, ad esempio, può essere costituita dal numero di studenti di ogni classe in una scuola elementare; ogni elemento della matrice è il numero di studenti in un singolo livello. Analogamente, una matrice può contenere i voti di uno studente per una classe; ogni elemento della matrice è un singolo livello.

È possibile che singole variabili memorizzino tutti gli elementi di dati. Se, ad esempio, l'applicazione analizza i voti degli studenti, è possibile usare una variabile separata per ogni livello di studente, ad esempio `englishGrade1` , `englishGrade2` e così via. Questo approccio presenta tre limitazioni principali:

- Dobbiamo capire in fase di progettazione esattamente il numero di voti da gestire.
- La gestione rapida di un numero elevato di voti diventa poco ingombrante. Questa operazione a sua volta rende molto più probabile che un'applicazione presenti bug gravi.
- È difficile da gestire. Ogni nuovo livello aggiunto richiede che l'applicazione venga modificata, ricompilata e ridistribuita.

Usando una matrice, è possibile fare riferimento a questi valori correlati con lo stesso nome e usare un numero denominato *Indice* o *pedice* per identificare un singolo elemento in base alla relativa posizione nella matrice. Gli indici di una matrice variano da 0 a uno inferiore al numero totale di elementi nella matrice. Quando si usa Visual Basic sintassi per definire la dimensione di una matrice, è necessario specificare l'indice più alto, non il numero totale di elementi nella matrice. È possibile utilizzare la matrice come un'unità e la possibilità di iterare gli elementi evita di dover capire esattamente il numero di elementi che contiene in fase di progettazione.

Di seguito sono riportati alcuni esempi:

```vb
' Declare a single-dimension array of 5 numbers.
Dim numbers(4) As Integer

' Declare a single-dimension array and set its 4 values.
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

## <a name="array-elements-in-a-simple-array"></a>Elementi di matrice in una matrice semplice

Viene ora creata una matrice denominata `students` per archiviare il numero di studenti in ogni classe di una scuola elementare. Gli indici degli elementi sono compresi tra 0 e 6. L'uso di questa matrice è più semplice rispetto alla dichiarazione di sette variabili.

Nella figura seguente viene illustrata la `students` matrice. Per ogni elemento della matrice:

- L'indice dell'elemento rappresenta l'anno scolastico (l'indice 0 rappresenta l'asilo).

- Il valore contenuto nell'elemento rappresenta il numero degli studenti iscritti a tale anno scolastico.

![Diagramma che mostra una matrice di numeri di studenti](./media/index/students-array-elements.gif)

L'esempio seguente contiene il codice Visual Basic che crea e usa la matrice:

[!code-vb[simple-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]

Nell'esempio vengono eseguite tre operazioni:

- Dichiara una `students` matrice con sette elementi. Il numero `6` nella dichiarazione di matrice indica l'ultimo indice nella matrice, ovvero uno inferiore al numero di elementi nella matrice.
- Assegna i valori a ogni elemento nella matrice. Gli elementi della matrice sono accessibili usando il nome della matrice e includendo l'indice del singolo elemento tra parentesi.
- Elenca ogni valore della matrice. Nell'esempio viene utilizzata un' [`For`](../../../language-reference/statements/for-next-statement.md) istruzione per accedere a ogni elemento della matrice in base al numero di indice.

La `students` matrice nell'esempio precedente è una matrice unidimensionale perché usa un indice. Una matrice che usa più indici o indici è detta *multidimensionale*. Per ulteriori informazioni, vedere il resto di questo articolo e le [dimensioni delle matrici in Visual Basic](array-dimensions.md).

## <a name="creating-an-array"></a>Creazione di una matrice

È possibile definire le dimensioni di una matrice in diversi modi:

- È possibile specificare la dimensione quando la matrice viene dichiarata:

  [!code-vb[creating1](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]

- È possibile usare una `New` clausola per specificare la dimensione di una matrice al momento della creazione:

  [!code-vb[creating2](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]

Se si dispone di una matrice esistente, è possibile ridefinirne la dimensione usando l' [`ReDim`](../../../language-reference/statements/redim-statement.md) istruzione. È possibile specificare che l' `ReDim` istruzione mantenga i valori presenti nella matrice oppure è possibile specificare che crei una matrice vuota. L'esempio seguente illustra vari modi di usare l'istruzione `ReDim` per modificare la dimensione di una matrice esistente.

[!code-vb[redimensioning](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]

Per ulteriori informazioni, vedere l' [istruzione ReDim](../../../language-reference/statements/redim-statement.md).

## <a name="storing-values-in-an-array"></a>Archiviazione di valori in una matrice

È possibile accedere a ogni posizione in una matrice usando un indice di tipo `Integer`. È possibile archiviare e recuperare i valori in una matrice facendo riferimento a ogni posizione della matrice tramite il relativo indice racchiuso tra parentesi. Gli indici per le matrici multidimensionali sono separati da virgole (,). È necessario un indice per ogni dimensione della matrice.

Nell'esempio seguente vengono illustrate alcune istruzioni per l'archiviazione e il recupero di valori nelle matrici.

[!code-vb[store-and-retrieve](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]

## <a name="populating-an-array-with-array-literals"></a>Popolamento di una matrice con valori letterali di matrice

Usando un valore letterale di matrice, è possibile popolare una matrice con un set iniziale di valori nello stesso momento in cui viene creata. Un valore letterale di matrice è costituito da un elenco di valori delimitati da virgole racchiusi tra parentesi graffe (`{}`).

Quando si usa un valore letterale di matrice per creare una matrice, è possibile specificare il tipo o usare l'inferenza del tipo per determinare il tipo di matrice. Nell'esempio seguente vengono illustrate entrambe le opzioni.

[!code-vb[create-with-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]

Quando si usa l'inferenza del tipo, il tipo della matrice viene determinato dal *tipo dominante* nell'elenco di valori letterali. Il tipo dominante è il tipo in cui tutti gli altri tipi nella matrice possono ampliarsi. Se non è possibile determinare il tipo univoco, il tipo dominante è il tipo univoco in cui possono restringersi tutti gli altri tipi nella matrice. Se nessuno di questi tipi univoci può essere determinato, il tipo dominante è `Object`. Se, ad esempio, l'elenco di valori fornito al valore letterale di matrice contiene valori di tipo `Integer`, `Long`e `Double`, la matrice risultante è di tipo `Double`. Poiché `Integer` e `Long` si ampliano solo a `Double` , `Double` è il tipo dominante. Per altre informazioni, vedere [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).

> [!NOTE]
> È possibile utilizzare l'inferenza del tipo solo per le matrici definite come variabili locali in un membro di tipo. Se una definizione di tipo esplicita è assente, le matrici definite con valori letterali di matrice a livello di classe sono di tipo `Object[]` . Per altre informazioni, vedere [inferenza dei tipi locali](../variables/local-type-inference.md).

Si noti che nell'esempio precedente viene definito `values` come una matrice di tipo `Double` anche se tutti i valori letterali di matrice sono di tipo `Integer` . È possibile creare questa matrice perché i valori nel valore letterale di matrice possono ampliarsi ai `Double` valori.

È inoltre possibile creare e popolare una matrice multidimensionale tramite *valori letterali di matrice annidati*. I valori letterali di matrice annidati devono avere un certo numero di dimensioni coerenti con la matrice risultante. Nell'esempio seguente viene creata una matrice bidimensionale di numeri interi utilizzando valori letterali di matrice annidati.

[!code-vb[nested-array-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]

Quando si usano valori letterali di matrice annidati per creare e popolare una matrice, si verifica un errore se il numero di elementi nei valori letterali di matrice annidati non corrisponde. Si verifica un errore anche se la variabile di matrice viene dichiarata in modo esplicito con un numero diverso di dimensioni rispetto ai valori letterali di matrice.

Come è possibile per le matrici unidimensionali, è possibile basarsi sull'inferenza del tipo durante la creazione di una matrice multidimensionale con valori letterali di matrice annidati. Il tipo dedotto è il tipo dominante per tutti i valori in tutti i valori letterali di matrice per tutti i livelli di annidamento. Nell'esempio seguente viene creata una matrice bidimensionale di tipo `Double[,]` da valori di tipo `Integer` e `Double` .

[!code-vb[nested-type-inference](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]

Per altri esempi, vedere [Procedura: inizializzare una variabile di matrice in Visual Basic](how-to-initialize-an-array-variable.md).

## <a name="iterating-through-an-array"></a>Iterazione in una matrice

Quando si scorre una matrice, si accede a ogni elemento nella matrice dall'indice più basso al più alto o dal più alto al più basso. In genere, usare l'oggetto [per... Istruzione Next](../../../language-reference/statements/for-next-statement.md) o [per each... Istruzione Next](../../../language-reference/statements/for-each-next-statement.md) per scorrere gli elementi di una matrice. Quando non si conoscono i limiti superiori della matrice, è possibile chiamare il <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> metodo per ottenere il valore massimo dell'indice. Sebbene il valore di indice più basso sia quasi sempre 0, è possibile chiamare il <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> metodo per ottenere il valore più basso dell'indice.

Nell'esempio seguente viene eseguita l'iterazione di una matrice unidimensionale utilizzando l' [`For...Next`](../../../language-reference/statements/for-next-statement.md) istruzione.

[!code-vb[iterate-one-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]

Nell'esempio seguente viene eseguita l'iterazione di una matrice multidimensionale usando un' [`For...Next`](../../../language-reference/statements/for-next-statement.md) istruzione. Il metodo <xref:System.Array.GetUpperBound%2A> ha un parametro che specifica la dimensione. `GetUpperBound(0)`Restituisce l'indice più alto della prima dimensione e `GetUpperBound(1)` restituisce l'indice più alto della seconda dimensione.

[!code-vb[iterate-two-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]

Nell'esempio seguente viene usato un oggetto [per ogni... Istruzione successiva](../../../language-reference/statements/for-each-next-statement.md)per scorrere una matrice unidimensionale e una matrice bidimensionale.

[!code-vb[iterate-for-each-next](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]

## <a name="array-size"></a>Dimensioni della matrice

La dimensione di una matrice è il prodotto delle lunghezze di tutte le relative dimensioni e rappresenta il numero totale di elementi attualmente contenuti nella matrice.  Nell'esempio seguente viene dichiarata una matrice bidimensionale con quattro elementi in ogni dimensione. Come illustrato nell'output dell'esempio, le dimensioni della matrice sono pari a 16 (o (3 + 1) * (3 + 1).

[!code-vb[array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]

> [!NOTE]
> Questa discussione sulle dimensioni della matrice non si applica alle matrici irregolari. Per informazioni sulle matrici irregolari e sulla determinazione delle dimensioni di una matrice di matrici, vedere la sezione [matrici](#jagged-arrays) di matrici.

È possibile determinare le dimensioni di una matrice usando la proprietà <xref:System.Array.Length%2A?displayProperty=nameWithType>. È possibile trovare la lunghezza di ogni dimensione di una matrice multidimensionale usando il <xref:System.Array.GetLength%2A?displayProperty=nameWithType> metodo.

È possibile ridimensionare una variabile di matrice assegnando un nuovo oggetto matrice o usando l'istruzione [ `ReDim` Statement](../../../language-reference/statements/redim-statement.md) . Nell'esempio seguente viene utilizzata l' `ReDim` istruzione per modificare una matrice di 100 elementi in una matrice di elementi 51.

[!code-vb[resize-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]

Di seguito sono indicati alcuni elementi importanti relativi alla dimensione di una matrice.

|||
|---|---|
|Lunghezza delle dimensioni|L'indice di ogni dimensione è in base 0, ovvero è compreso tra 0 e il relativo limite superiore. La lunghezza di una determinata dimensione è quindi maggiore di uno rispetto al limite superiore dichiarato di tale dimensione.|
|Limiti di lunghezza|La lunghezza di ogni dimensione di una matrice è limitata al valore massimo del tipo di `Integer` dati, ovvero <xref:System.Int32.MaxValue?displayProperty=nameWithType> o (2 ^ 31)-1. La dimensione totale di una matrice, tuttavia, è limitata anche dalla memoria disponibile nel sistema. Se si tenta di inizializzare una matrice che supera la quantità di memoria disponibile, il runtime genera un'eccezione <xref:System.OutOfMemoryException> .|
|Dimensione ed elementi della matrice|La dimensione di una matrice è indipendente dal tipo di dati dei relativi elementi. La dimensione rappresenta sempre il numero totale di elementi e non il numero di byte utilizzati in memoria.|
|Consumo di memoria|Non è possibile fare ipotesi sulla modalità di archiviazione di una matrice in memoria. L'archiviazione dipende dalla larghezza dei dati delle diverse piattaforme. Di conseguenza, è possibile che l'archiviazione di una stessa matrice richieda più memoria in un sistema a 64 bit che in un sistema a 32 bit. A seconda della configurazione di sistema al momento dell'inizializzazione di una matrice, Common Language Runtime (CLR) può assegnare la memoria in modo da compattare al massimo gli elementi oppure in modo da allinearli tutti in base ai limiti dell'hardware. Per le informazioni di controllo di una matrice è richiesto un sovraccarico di archiviazione che aumenta con ogni dimensione aggiunta.|

## <a name="the-array-type"></a>Tipo di matrice

Ogni matrice ha un tipo di dati che differisce dal tipo di dati dei relativi elementi. Non esiste un singolo tipo di dati per tutte le matrici. Il tipo di dati di una matrice viene invece determinato dal numero di dimensioni, o *rango*, della matrice e dal tipo di dati degli elementi nella matrice. Due variabili di matrice hanno lo stesso tipo di dati solo se hanno lo stesso rango e i relativi elementi hanno lo stesso tipo di dati. La lunghezza delle dimensioni di una matrice non influisce sul tipo di dati della matrice.

Ogni matrice eredita dalla classe <xref:System.Array?displayProperty=nameWithType>. È possibile dichiarare una variabile di tipo `Array`, ma non è possibile creare una matrice di tipo `Array`. Ad esempio, anche se il codice seguente dichiara `arr` che la variabile è di tipo `Array` e chiama il <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> metodo per creare un'istanza della matrice, il tipo della matrice viene dimostrato come oggetto [].

[!code-vb[array-class](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)]

L'[istruzione ReDim](../../../language-reference/statements/redim-statement.md) non può inoltre operare su una variabile dichiarata di tipo `Array`. Per questi motivi, e per l'indipendenza dai tipi, è consigliabile dichiarare ogni matrice come un tipo specifico.

È possibile determinare il tipo di dati di una matrice o dei relativi elementi in diversi modi.

- È possibile chiamare il <xref:System.Object.GetType%2A> Metodo sulla variabile per ottenere un <xref:System.Type> oggetto che rappresenta il tipo in fase di esecuzione della variabile. Nelle proprietà e nei metodi dell'oggetto <xref:System.Type> sono presenti informazioni complete.
- È possibile passare la variabile alla <xref:Microsoft.VisualBasic.Information.TypeName%2A> funzione per ottenere un oggetto `String` con il nome del tipo in fase di esecuzione.

Nell'esempio seguente vengono chiamati sia il `GetType` metodo che la `TypeName` funzione per determinare il tipo di una matrice. Il tipo di matrice è `Byte(,)` . Si noti che la <xref:System.Type.BaseType%2A?displayProperty=nameWithType> proprietà indica anche che il tipo di base della matrice di byte è la <xref:System.Array> classe.

[!code-vb[array-type](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]

## <a name="arrays-as-return-values-and-parameters"></a>Matrici come valori restituiti e parametri

Per restituire una matrice da una routine `Function`, specificare il tipo di dati della matrice e il numero di dimensioni come tipo restituito dell'[istruzione Function](../../../language-reference/statements/function-statement.md). All'interno della funzione dichiarare una variabile di matrice locale con lo stesso tipo di dati degli elementi e lo stesso numero di dimensioni. Includere la variabile di matrice locale senza parentesi nell'[istruzione Return](../../../language-reference/statements/return-statement.md).

Per specificare una matrice come parametro in una routine `Sub` o `Function` , definire il parametro come matrice con un tipo di dati e un numero di dimensioni specificati. Nella chiamata alla routine passare una variabile di matrice con lo stesso tipo di dati e il numero di dimensioni.

Nell'esempio seguente, la `GetNumbers` funzione restituisce un oggetto `Integer()` , una matrice unidimensionale di tipo `Integer` . La routine `ShowNumbers` accetta un argomento `Integer()` .

[!code-vb[return-value-and-params](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]

Nell'esempio seguente, la `GetNumbersMultiDim` funzione restituisce un oggetto `Integer(,)` , una matrice bidimensionale di tipo `Integer` .  La routine `ShowNumbersMultiDim` accetta un argomento `Integer(,)` .

[!code-vb[multidimensional-return-value](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]

## <a name="jagged-arrays"></a>Matrici di matrici

In alcuni casi la struttura dei dati nell'applicazione è bidimensionale, ma non rettangolare. Ad esempio, è possibile usare una matrice per archiviare i dati relativi alla temperatura elevata di ogni giorno del mese. La prima dimensione della matrice rappresenta il mese, ma la seconda dimensione rappresenta il numero di giorni e il numero di giorni in un mese non è uniforme. Una *matrice irregolare*, definita anche *matrice di matrici*, è progettata per scenari di questo tipo. Una matrice irregolare è una matrice i cui elementi sono anche matrici. Una matrice irregolare e ogni elemento di una matrice irregolare possono avere una o più dimensioni.

Nell'esempio seguente viene utilizzata una matrice di mesi, ogni elemento di che è una matrice di giorni. Nell'esempio viene utilizzata una matrice di matrici perché i mesi diversi hanno un numero di giorni diverso.  Nell'esempio viene illustrato come creare una matrice di matrici, assegnarvi valori e recuperare e visualizzare i relativi valori.

[!code-vb[jagged-arrays](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]

Nell'esempio precedente i valori vengono assegnati alla matrice di matrici in base a un elemento per elemento tramite un `For...Next` ciclo. È anche possibile assegnare valori agli elementi di una matrice irregolare usando valori letterali di matrice annidati. Tuttavia, il tentativo di usare valori letterali di matrice annidati, ad esempio, `Dim valuesjagged = {{1, 2}, {2, 3, 4}}` genera l'errore del compilatore [BC30568](../../../misc/bc30568.md). Per correggere l'errore, racchiudere tra parentesi i valori letterali della matrice interna. Le parentesi forzano la valutazione dell'espressione letterale di matrice e i valori risultanti vengono usati con il valore letterale di matrice esterno, come illustrato nell'esempio riportato di seguito.

[!code-vb[jagged-array-initialization](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)]

Una matrice di matrici è una matrice unidimensionale i cui elementi contengono matrici. Pertanto, la <xref:System.Array.Length%2A?displayProperty=nameWithType> proprietà e il `Array.GetLength(0)` metodo restituiscono il numero di elementi nella matrice unidimensionale e `Array.GetLength(1)` genera un oggetto <xref:System.IndexOutOfRangeException> perché una matrice irregolare non è multidimensionale. Per determinare il numero di elementi in ogni sottomatrice è necessario recuperare il valore della proprietà di ogni sottomatrice <xref:System.Array.Length%2A?displayProperty=nameWithType> . Nell'esempio seguente viene illustrato come determinare il numero di elementi in una matrice di matrici.

[!code-vb[jagged-array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)]

## <a name="zero-length-arrays"></a>Matrici di lunghezza zero

Visual Basic distingue tra una matrice non inizializzata (una matrice il cui valore è `Nothing` ) e una matrice di *lunghezza zero* o una matrice vuota, ovvero una matrice priva di elementi. Una matrice non inizializzata è una matrice che non è stata dimensionata o a cui sono stati assegnati valori. Ad esempio:

```vb
Dim arr() As String
```

Una matrice di lunghezza zero viene dichiarata con una dimensione di-1. Ad esempio:

```vb
Dim arrZ(-1) As String
```

Potrebbe essere necessario creare una matrice di lunghezza zero nelle circostanze seguenti:

- Senza rischiare un' <xref:System.NullReferenceException> eccezione, il codice deve accedere ai membri della <xref:System.Array> classe, ad esempio <xref:System.Array.Length%2A> o <xref:System.Array.Rank%2A> , oppure chiamare una funzione Visual Basic quale <xref:Microsoft.VisualBasic.Information.UBound%2A> .

- Si vuole che il codice venga mantenuto semplice, non è necessario verificarlo `Nothing` come caso speciale.

- Il codice interagisce con un'API (Application Programming Interface) che richiede il passaggio di una matrice di lunghezza zero a una o più routine oppure che restituisce una matrice di lunghezza zero da una o più routine.

## <a name="splitting-an-array"></a>Suddivisione di una matrice

In alcuni casi, potrebbe essere necessario suddividere una singola matrice in più matrici. Ciò implica l'identificazione del punto o dei punti in cui deve essere divisa la matrice, quindi la copia della matrice in due o più matrici separate.

> [!NOTE]
> In questa sezione non viene illustrata la suddivisione di una singola stringa in una matrice di stringhe basata su un delimitatore. Per informazioni sulla suddivisione di una stringa, vedere il <xref:System.String.Split%2A?displayProperty=nameWithType> metodo.

I criteri più comuni per suddividere una matrice sono:

- Numero di elementi nella matrice. Ad esempio, potrebbe essere necessario suddividere una matrice di più di un numero specificato di elementi in un numero di parti approssimativamente uguali. A questo scopo, è possibile usare il valore restituito dal <xref:System.Array.Length%2A?displayProperty=nameWithType> <xref:System.Array.GetLength%2A?displayProperty=nameWithType> metodo o.

- Valore di un elemento che funge da delimitatore che indica dove deve essere suddivisa la matrice. È possibile cercare un valore specifico chiamando i <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> metodi e.

Dopo aver determinato l'indice o gli indici in corrispondenza del quale deve essere suddivisa la matrice, è possibile creare le singole matrici chiamando il <xref:System.Array.Copy%2A?displayProperty=nameWithType> metodo.

Nell'esempio seguente una matrice viene suddivisa in due matrici di dimensioni approssimativamente uguali. Se il numero totale di elementi della matrice è dispari, la prima matrice avrà un elemento maggiore del secondo.

[!code-vb[splitting-an-array-by-length](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)]

Nell'esempio seguente viene divisa una matrice di stringhe in due matrici in base alla presenza di un elemento il cui valore è "zzz", che funge da delimitatore di matrice. Le nuove matrici non includono l'elemento che contiene il delimitatore.

[!code-vb[splitting-an-array-by-delimiter](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)]

## <a name="joining-arrays"></a>Unione di matrici

È anche possibile combinare un numero di matrici in una singola matrice più grande. A tale scopo, è possibile usare anche il <xref:System.Array.Copy%2A?displayProperty=nameWithType> metodo.

> [!NOTE]
> Questa sezione non illustra l'aggiunta di una matrice di stringhe in una singola stringa. Per informazioni sull'aggiunta di una matrice di stringhe, vedere il <xref:System.String.Join%2A?displayProperty=nameWithType> metodo.

Prima di copiare gli elementi di ogni matrice nella nuova matrice, è necessario prima di tutto assicurarsi di avere inizializzato la matrice in modo che sia sufficientemente grande da contenere la nuova matrice. Questa operazione può essere eseguita in due modi:

- Usare l' [`ReDim Preserve`](../../../language-reference/statements/redim-statement.md) istruzione per espandere dinamicamente la matrice prima di aggiungervi nuovi elementi. Questa è la tecnica più semplice, ma può comportare una riduzione delle prestazioni e un utilizzo eccessivo della memoria durante la copia di matrici di grandi dimensioni.
- Calcolare il numero totale di elementi necessari per la nuova matrice di grandi dimensioni, quindi aggiungervi gli elementi di ogni matrice di origine.

Nell'esempio seguente viene usato il secondo approccio per aggiungere quattro matrici con dieci elementi ciascuno a una singola matrice.

[!code-vb[joining-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)]

Poiché in questo caso le matrici di origine sono di dimensioni ridotte, è anche possibile espandere dinamicamente la matrice quando si aggiungono gli elementi di ogni nuova matrice. Nell'esempio seguente viene eseguita questa operazione.

[!code-vb[joining-an-array-dynamically](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)]

## <a name="collections-as-an-alternative-to-arrays"></a>Raccolte come alternativa alle matrici

Le matrici sono estremamente utili per la creazione e l'uso di un numero fisso di oggetti fortemente tipizzati. Le raccolte consentono di lavorare in modo più flessibile con gruppi di oggetti. Diversamente dalle matrici, che richiedono la modifica esplicita delle dimensioni di una matrice con l' [ `ReDim` istruzione](../../../language-reference/statements/redim-statement.md), le raccolte crescono e si riducono dinamicamente in base alle esigenze di un'applicazione.

Quando si usa `ReDim` per ridimensionare una matrice, Visual Basic crea una nuova matrice e rilascia quella precedente. Questa operazione causa un aumento del tempo di esecuzione. Di conseguenza, se il numero di elementi che si utilizza cambiano di frequente oppure non è possibile prevedere il numero massimo di elementi necessari, in genere si otterranno prestazioni migliori utilizzando una raccolta.

Per alcune raccolte è possibile assegnare una chiave a qualsiasi oggetto inserito nella raccolta in modo da recuperare rapidamente l'oggetto usando la chiave.

Se la raccolta contiene elementi di un solo tipo di dati, è possibile usare una delle classi dello spazio dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType>. In una raccolta generica viene imposta l'indipendenza dai tipi, in modo da impedire che vengano aggiunti altri tipi di dati alla raccolta.

Per altre informazioni sulle raccolte, vedere [Raccolte](../../concepts/collections.md).

## <a name="related-topics"></a>Argomenti correlati

|Termine|Definizione|
|----------|----------------|
|[Array Dimensions in Visual Basic](array-dimensions.md)|Illustra il numero di dimensioni, o rango, e le dimensioni delle matrici.|
|[Procedura: Inizializzare una variabile di matrice in Visual Basic](how-to-initialize-an-array-variable.md)|Descrive come popolare le matrici con valori iniziali.|
|[Procedura: ordinare una matrice in Visual Basic](how-to-sort-an-array.md)|Illustra come ordinare alfabeticamente gli elementi di una matrice.|
|[Procedura: Assegnare una matrice a un'altra matrice](how-to-assign-one-array-to-another-array.md)|Descrive regole e passaggi per l'assegnazione di una matrice a un'altra variabile di matrice.|
|[Risoluzione dei problemi relativi alle matrici](troubleshooting-arrays.md)|Illustra alcuni problemi comuni che si verificano quando si usano le matrici.|

## <a name="see-also"></a>Vedere anche

- <xref:System.Array?displayProperty=nameWithType>
- [Istruzione Dim](../../../language-reference/statements/dim-statement.md)
- [Istruzione ReDim](../../../language-reference/statements/redim-statement.md)
