---
title: Dim (istruzione)
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: 1b0c3089c366c417af926c8c0703cea021674432
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744731"
---
# <a name="dim-statement-visual-basic"></a>Istruzione Dim (Visual Basic)

Dichiara e alloca lo spazio di archiviazione per una o più variabili.

## <a name="syntax"></a>Sintassi

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a>Parti

- `attributelist`

  Facoltativa. Vedere [elenco attributi](attribute-list.md).

- `accessmodifier`

  Facoltativa. Può essere uno dei collegamenti seguenti:

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Private](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  Vedere [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `Shared`

  Facoltativa. Vedere [Shared](../modifiers/shared.md).

- `Shadows`

  Facoltativa. Vedere [Shadows](../modifiers/shadows.md).

- `Static`

  Facoltativa. Vedere [static](../modifiers/static.md).

- `ReadOnly`

  Facoltativa. Vedere [ReadOnly](../modifiers/readonly.md).

- `WithEvents`

  Facoltativa. Specifica che si tratta di variabili oggetto che fanno riferimento a istanze di una classe in grado di generare eventi. Vedere [WithEvents](../modifiers/withevents.md).

- `variablelist`

  Obbligatoria. Elenco delle variabili dichiarate in questa istruzione.

  `variable [ , variable ... ]`

  Ogni `variable` presenta la sintassi e le parti seguenti:

  `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`

  |Parte|Descrizione|
  |---|---|
  |`variablename`|Obbligatoria. Nome della variabile. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
  |`boundslist`|Facoltativa. Elenco di limiti di ogni dimensione di una variabile di matrice.|
  |`New`|Facoltativa. Crea una nuova istanza della classe quando viene eseguita l'istruzione `Dim`.|
  |`datatype`|Facoltativa. Tipo di dati della variabile.|
  |`With`|Facoltativa. Introduce l'elenco di inizializzatori di oggetto.|
  |`propertyname`|Facoltativa. Nome di una proprietà nella classe di cui si sta creando un'istanza.|
  |`propinitializer`|Obbligatorio dopo `propertyname` =. Espressione valutata e assegnata al nome della proprietà.|
  |`initializer`|Facoltativo se `New` non è specificato. Espressione valutata e assegnata alla variabile al momento della creazione.|

## <a name="remarks"></a>Note

Il compilatore Visual Basic utilizza l'istruzione `Dim` per determinare il tipo di dati della variabile e altre informazioni, ad esempio il codice che può accedere alla variabile. Nell'esempio seguente viene dichiarata una variabile per includere un valore `Integer`.

```vb
Dim numberOfStudents As Integer
```

È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

Per un tipo riferimento, usare la parola chiave `New` per creare una nuova istanza della classe o della struttura specificata dal tipo di dati. Se si utilizza `New`, non viene utilizzata un'espressione di inizializzazione. Vengono invece forniti gli argomenti, se necessari, al costruttore della classe da cui si crea la variabile.

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

È possibile dichiarare una variabile in una routine, un blocco, una classe, una struttura o un modulo. Non è possibile dichiarare una variabile in un file di origine, uno spazio dei nomi o un'interfaccia. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

Una variabile dichiarata a livello di modulo, all'esterno di qualsiasi routine, è una *variabile membro* o un *campo*. Le variabili membro sono nell'ambito della classe, della struttura o del modulo. Una variabile dichiarata a livello di routine è una *variabile locale*. Le variabili locali si trovano nell'ambito solo all'interno della routine o del blocco.

I modificatori di accesso seguenti vengono utilizzati per dichiarare le variabili all'esterno di una routine: `Public`, `Protected`, `Friend`, `Protected Friend`e `Private`. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

La parola chiave `Dim` è facoltativa e in genere omessa se si specifica uno dei modificatori seguenti: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`o `WithEvents`.

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

Se `Option Explicit` è on (impostazione predefinita), il compilatore richiede una dichiarazione per ogni variabile utilizzata. Per altre informazioni, vedere [istruzione Option Explicit](option-explicit-statement.md).

## <a name="specifying-an-initial-value"></a>Specifica di un valore iniziale

È possibile assegnare un valore a una variabile al momento della creazione. Per un tipo di valore, si usa un *inizializzatore* per fornire un'espressione da assegnare alla variabile. L'espressione deve restituire una costante che può essere calcolata in fase di compilazione.

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

Se viene specificato un inizializzatore e non viene specificato un tipo di dati in una clausola `As`, viene utilizzata l' *inferenza del tipo* per dedurre il tipo di dati dall'inizializzatore. Nell'esempio seguente `num1` e `num2` sono fortemente tipizzati come numeri interi. Nella seconda dichiarazione, l'inferenza del tipo deduce il tipo dal valore 3.

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

L'inferenza del tipo si applica a livello di routine. Non si applica all'esterno di una routine in una classe, una struttura, un modulo o un'interfaccia. Per ulteriori informazioni sull'inferenza del tipo, vedere l' [istruzione Option deduce](option-infer-statement.md) e l' [inferenza del tipo locale](../../programming-guide/language-features/variables/local-type-inference.md).

Per informazioni su cosa accade quando un tipo di dati o un inizializzatore non viene specificato, vedere [valori e tipi di dati predefiniti](dim-statement.md#default) più avanti in questo argomento.

È possibile utilizzare un *inizializzatore di oggetto* per dichiarare istanze di tipi denominati e anonimi. Il codice seguente crea un'istanza di una classe `Student` e usa un inizializzatore di oggetto per inizializzare le proprietà.

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

Per altre informazioni sugli inizializzatori di oggetto, vedere [procedura: dichiarare un oggetto usando un inizializzatore di](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)oggetto, [inizializzatori di oggetto: tipi denominati e anonimi](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)e [tipi anonimi](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).

## <a name="declaring-multiple-variables"></a>Dichiarazione di più variabili

È possibile dichiarare diverse variabili in un'unica istruzione di dichiarazione, specificando il nome della variabile per ciascuna di esse e seguendo ogni nome di matrice con le parentesi. Nel caso di più variabili, è possibile separarle mediante virgole.

```vb
Dim lastTime, nextTime, allTimes() As Date
```

Se si dichiara più di una variabile con una clausola `As`, non è possibile fornire un inizializzatore per quel gruppo di variabili.

È possibile specificare tipi di dati diversi per variabili diverse utilizzando una clausola `As` separata per ogni variabile dichiarata. Ogni variabile accetta il tipo di dati specificato nella prima clausola `As` rilevata dopo la relativa parte `variablename`.

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a>Matrici

È possibile dichiarare una variabile in modo che contenga una *matrice*, che può includere più valori. Per specificare che una variabile include una matrice, seguire immediatamente la `variablename` con le parentesi. Per altre informazioni sulle matrici, vedere [Matrici](../../programming-guide/language-features/arrays/index.md).

È possibile specificare il limite inferiore e superiore di ogni dimensione di una matrice. A tale scopo, includere un `boundslist` all'interno delle parentesi. Per ogni dimensione, il `boundslist` specifica il limite superiore e, facoltativamente, il limite inferiore. Il limite inferiore è sempre zero, indipendentemente dal fatto che sia specificato o meno. Ogni indice può variare da zero al valore del limite superiore.

Le due istruzioni seguenti sono equivalenti. Ogni istruzione dichiara una matrice di 21 elementi `Integer`. Quando si accede alla matrice, l'indice può variare da 0 a 20.

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

Nell'istruzione seguente viene dichiarata una matrice bidimensionale di tipo `Double`. La matrice include 4 righe (3 + 1) di 6 colonne (5 + 1) ognuna. Si noti che un limite superiore rappresenta il valore massimo possibile per l'indice e non la lunghezza della dimensione. La lunghezza della dimensione è il limite superiore più uno.

```vb
Dim matrix2(3, 5) As Double
```

Una matrice può avere dimensioni da 1 a 32.

È possibile lasciare vuoti tutti i limiti in una dichiarazione di matrice. In tal caso, la matrice ha il numero di dimensioni specificate, ma non è inizializzata. Ha un valore di `Nothing` fino a quando non si inizializzano almeno alcuni dei relativi elementi. Nell'istruzione `Dim` devono essere specificati i limiti per tutte le dimensioni o per nessuna dimensione.

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

Se la matrice ha più di una dimensione, è necessario includere virgole tra le parentesi per indicare il numero di dimensioni.

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

È possibile dichiarare una *matrice di lunghezza zero* dichiarando una delle dimensioni della matrice come-1. Una variabile che contiene una matrice di lunghezza zero non ha il valore `Nothing`. Le matrici di lunghezza zero sono richieste da alcune funzioni Common Language Runtime. Se si tenta di accedere a una matrice di questo tipo, si verifica un'eccezione in fase di esecuzione. Per altre informazioni, vedere [Matrici](../../programming-guide/language-features/arrays/index.md).

È possibile inizializzare i valori di una matrice usando un valore letterale di matrice. A tale scopo, racchiudere i valori di inizializzazione tra parentesi graffe (`{}`).

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

Per le matrici multidimensionali, l'inizializzazione di ogni dimensione separata è racchiusa tra parentesi graffe nella dimensione esterna. Gli elementi vengono specificati in ordine di riga.

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

Per ulteriori informazioni sui valori letterali di matrice, vedere [matrici](../../programming-guide/language-features/arrays/index.md).

## <a name="default"></a>Tipi di dati e valori predefiniti

Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e dell'inizializzatore in un'istruzione `Dim`.

|Tipo di dati specificato?|Inizializzatore specificato?|Esempio|Risultato|
|---|---|---|---|
|No|No|`Dim qty`|Se [Option Strict](option-strict-statement.md) è disattivato (impostazione predefinita), la variabile viene impostata su `Nothing`.<br /><br /> Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|
|No|Sì|`Dim qty = 5`|Se l' [opzione deduce](option-infer-statement.md) è on (impostazione predefinita), la variabile accetta il tipo di dati dell'inizializzatore. Vedere [inferenza del tipo locale](../../programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.<br /><br /> Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|
|Sì|No|`Dim qty As Integer`|La variabile viene inizializzata sul valore predefinito per il tipo di dati. Vedere la tabella più avanti in questa sezione.|
|Sì|Sì|`Dim qty  As Integer = 5`|Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.|

Se si specifica un tipo di dati ma non si specifica un inizializzatore, Visual Basic inizializza la variabile sul valore predefinito per il tipo di dati. Nella tabella seguente vengono illustrati i valori di inizializzazione predefiniti.

|Tipo di dati|Valore predefinito|
|---|---|
|Tutti i tipi numerici (inclusi `Byte` e `SByte`)|0|
|`Char`|Binario 0|
|Tutti i tipi di riferimento (inclusi `Object`, `String`e tutte le matrici)|`Nothing`|
|`Boolean`|`False`|
|`Date`|12:00 del 1 ° gennaio dell'anno 1 (01/01/0001 12:00:00 AM)|

Ogni elemento di una struttura viene inizializzato come se fosse una variabile separata. Se si dichiara la lunghezza di una matrice senza inizializzarne gli elementi, ogni elemento viene inizializzato come se fosse una variabile separata.

## <a name="static-local-variable-lifetime"></a>Durata variabile locale statica

Una `Static` variabile locale ha una durata maggiore di quella della routine in cui è dichiarata. I limiti della durata della variabile dipendono dalla posizione in cui la procedura viene dichiarata e dal fatto che sia `Shared`.

|Dichiarazione di routine|Variabile inizializzata|La variabile smette di esistere|
|---|---|---|
|In un modulo|La prima volta che viene chiamata la stored procedure|Quando il programma interrompe l'esecuzione|
|In una classe o una struttura, la procedura è `Shared`|La prima volta che la stored procedure viene chiamata su un'istanza specifica o sulla classe o sulla struttura stessa|Quando il programma interrompe l'esecuzione|
|In una classe o una struttura, la routine non è `Shared`|La prima volta che la stored procedure viene chiamata su un'istanza specifica|Quando l'istanza viene rilasciata per Garbage Collection (GC)|

## <a name="attributes-and-modifiers"></a>Attributi e modificatori

È possibile applicare attributi solo alle variabili membro e non alle variabili locali. Un attributo fornisce informazioni ai metadati dell'assembly, che non è significativo per l'archiviazione temporanea, ad esempio le variabili locali.

A livello di modulo, non è possibile usare il modificatore `Static` per dichiarare le variabili membro. A livello di procedura, non è possibile utilizzare `Shared`, `Shadows`, `ReadOnly`, `WithEvents`o qualsiasi modificatore di accesso per dichiarare le variabili locali.

È possibile specificare quale codice può accedere a una variabile fornendo un `accessmodifier`. Le variabili membro della classe e del modulo (all'esterno di qualsiasi routine) sono predefinite per l'accesso privato e le variabili membro della struttura sono predefinite per l'accesso pubblico. È possibile modificare i livelli di accesso con i modificatori di accesso. Non è possibile usare i modificatori di accesso per le variabili locali (all'interno di una routine).

È possibile specificare `WithEvents` solo sulle variabili membro, non sulle variabili locali all'interno di una routine. Se si specifica `WithEvents`, il tipo di dati della variabile deve essere un tipo di classe specifico, non `Object`. Non è possibile dichiarare una matrice con `WithEvents`. Per ulteriori informazioni sugli eventi, vedere [eventi](../../programming-guide/language-features/events/index.md).

> [!NOTE]
> Il codice esterno a una classe, una struttura o un modulo deve qualificare il nome di una variabile membro con il nome della classe, della struttura o del modulo. Il codice esterno a una procedura o a un blocco non può fare riferimento ad alcuna variabile locale all'interno di tale procedura o blocco.

## <a name="releasing-managed-resources"></a>Rilascio di risorse gestite

Il .NET Framework Garbage Collector elimina le risorse gestite senza alcuna codifica aggiuntiva da parte dell'utente. Tuttavia, è possibile forzare l'eliminazione di una risorsa gestita anziché attendere il Garbage Collector.

Se una classe dispone di una risorsa particolarmente preziosa e limitata (ad esempio una connessione al database o un handle di file), è possibile che non si desideri attendere fino al Garbage Collection successivo per eliminare un'istanza di classe che non è più in uso. Una classe può implementare l'interfaccia <xref:System.IDisposable> per fornire un modo per rilasciare le risorse prima di un Garbage Collection. Una classe che implementa tale interfaccia espone un metodo di `Dispose` che può essere chiamato per forzare il rilascio immediato di risorse preziose.

L'istruzione `Using` automatizza il processo di acquisizione di una risorsa, l'esecuzione di un set di istruzioni e quindi l'eliminazione della risorsa. Tuttavia, la risorsa deve implementare l'interfaccia <xref:System.IDisposable>. Per altre informazioni, vedere [Istruzione using](using-statement.md).

## <a name="example"></a>Esempio

Nell'esempio seguente vengono dichiarate le variabili usando l'istruzione `Dim` con varie opzioni.

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a>Esempio

Nell'esempio seguente vengono elencati i numeri primi compresi tra 1 e 30. L'ambito delle variabili locali è descritto nei commenti del codice.

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a>Esempio

Nell'esempio seguente, la variabile `speedValue` viene dichiarata a livello di classe. La parola chiave `Private` viene utilizzata per dichiarare la variabile. È possibile accedere alla variabile da qualsiasi routine della classe `Car`.

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Const](const-statement.md)
- [Istruzione ReDim](redim-statement.md)
- [Istruzione Option Explicit](option-explicit-statement.md)
- [Istruzione Option Infer](option-infer-statement.md)
- [Istruzione Option Strict](option-strict-statement.md)
- [Pagina Compilazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Dichiarazione di variabile](../../programming-guide/language-features/variables/variable-declaration.md)
- [Array](../../programming-guide/language-features/arrays/index.md)
- [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Tipi anonimi](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [Inferenza del tipo di variabile locale](../../programming-guide/language-features/variables/local-type-inference.md)
