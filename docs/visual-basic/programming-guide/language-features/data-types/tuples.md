---
title: Tuple in Visual Basic
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: 146e9c2360cea153d2f487769d5b983516861e8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694727"
---
# <a name="tuples-visual-basic"></a>Tuple (Visual Basic)

A partire da Visual Basic 2017, il linguaggio Visual Basic offre supporto predefinito per le tuple che rende la creazione di tuple e l'accesso a elementi delle tuple più semplice. Una tupla è una struttura dei dati leggero con un numero e una sequenza di valori. Quando si crea un'istanza di tupla, si definisce il numero e il tipo di dati di ogni valore (o elemento). Ad esempio, una tupla con 2 elementi (o coppia) dispone di due elementi. Il primo potrebbe essere un' `Boolean` valore, mentre il secondo è un `String`. Poiché le tuple rendono più semplice archiviare più valori in un singolo oggetto, vengono spesso usati come un modo semplice per restituire più valori da un metodo.

> [!IMPORTANT]
> Supporto per le tuple richiede il <xref:System.ValueTuple> tipo. Se non è installato .NET Framework 4.7, è necessario aggiungere il pacchetto NuGet `System.ValueTuple`, che è disponibile nella raccolta NuGet. Senza questo pacchetto, è possibile ottenere un errore di compilazione simile a "Tipo predefinito 'ValueTuple(Of,,,)' non è definito né importato."

## <a name="instantiating-and-using-a-tuple"></a>Creazione e uso di una tupla

Si crea un'istanza di una tupla racchiudendo le sue parentesi messaggistica immediata di valori delimitato da virgole. Tali valori diventa quindi un campo di tupla. Ad esempio, il codice seguente definisce una tripla (o 3 tuple) con un `Date` come primo valore, una `String` come il secondo e un `Boolean` come il rispettivo terzo.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

Per impostazione predefinita, il nome di ogni campo in una tupla è costituita da stringa `Item` insieme a posizione del campo in base uno della tupla. Per questa tupla con 3 elementi, il `Date` campo viene `Item1`, il `String` campo è `Item2`e il `Boolean` campo è `Item3`. L'esempio seguente mostra i valori dei campi della tupla di creare un'istanza nella riga di codice precedente

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

I campi di una tupla di Visual Basic sono in lettura / scrittura; Dopo aver creato l'istanza di una tupla, è possibile modificare i relativi valori. Nell'esempio seguente modifica due dei tre campi della tupla creato nell'esempio precedente e visualizza il risultato.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Creazione di un'istanza e l'utilizzo di una tupla con nome

Invece di usare i nomi predefiniti per i campi della tupla di valori, è possibile creare un'istanza di un *tupla denominata* assegnando nomi personalizzati agli elementi della tupla. I campi della tupla è accessibile tramite i nomi assegnati *o* con i relativi nomi predefiniti. Nell'esempio seguente crea un'istanza di 3 tuple stesso come in precedenza, ad eccezione del fatto che specifica esplicitamente il primo campo `EventDate`, il secondo `Name`e il terzo `IsHoliday`. Quindi Visualizza i valori dei campi, li modifica e visualizza i valori dei campi nuovamente.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>Nomi di elemento di tupla dedotti

A partire da Visual Basic 15.3, Visual Basic in grado di dedurre i nomi di elementi di tupla. non è necessario assegnare loro in modo esplicito. I nomi di tupla dedotti sono utili quando si Inizializza una tupla da un set di variabili e si desidera che il nome dell'elemento tupla da corrispondere al nome della variabile. 

L'esempio seguente crea una `stateInfo` elementi, denominati tupla che contiene tre in modo esplicito `state`, `stateName`, e `capital`. Si noti che, nei nomi di elementi, l'istruzione di inizializzazione della tupla assegna semplicemente gli elementi denominati i valori delle variabili con nome identico.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
Poiché gli elementi e le variabili hanno lo stesso nome, il compilatore Visual Basic può dedurre i nomi dei campi, come illustrato nell'esempio seguente.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Per abilitare i nomi degli elementi di tupla dedotti, è necessario definire la versione del compilatore Visual Basic da utilizzare nel progetto Visual Basic (\*vbproj) file: 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 
```

Il numero di versione può essere qualsiasi versione del compilatore Visual Basic 15.3 a partire. Anziché impostare come hardcoded una versione del compilatore specifici, è possibile specificare anche "Latest" come valore di `LangVersion` per la compilazione con la versione più recente del compilatore Visual Basic installato nel sistema.

Per altre informazioni, vedere [impostando la versione del linguaggio Visual Basic](../../../language-reference/configure-language-version.md).

In alcuni casi, il compilatore Visual Basic non è possibile dedurre il nome dell'elemento tupla dal nome candidato e il campo di tupla può fare riferimento solo utilizzando il nome predefinito, ad esempio `Item1`, `Item2`e così via. Sono inclusi:

- Il nome candidato è identico al nome di un membro, tupla, ad esempio `Item3`, `Rest`, o `ToString`.

- Il nome candidato è duplicato nella tupla.
 
Quando l'inferenza del nome di campo non riesce, non genera un errore del compilatore Visual Basic, né è un'eccezione generata in fase di esecuzione. Al contrario, campi della tupla devono fare riferimento i relativi nomi predefiniti, ad esempio `Item1` e `Item2`. 
  
## <a name="tuples-versus-structures"></a>Tuple e strutture

Una tupla di Visual Basic è un tipo di valore che rappresenta un'istanza di uno di un **System. valuetuple** tipi generici. Ad esempio, il `holiday` tupla definita nell'esempio precedente è un'istanza del <xref:System.ValueTuple%603> struttura. È progettato per essere utilizzato come contenitore leggero per i dati. Poiché la tupla mira a semplificare creare un oggetto con più elementi di dati, alcune delle funzionalità che potrebbe avere una struttura personalizzata manca. Sono inclusi:

- Membri personalizzati. È possibile definire il proprio le proprietà, metodi o eventi da una tupla.

- Convalida. È possibile convalidare i dati assegnati ai campi.

- Immutabilità. Le tuple di Visual Basic sono modificabili. Al contrario, una struttura personalizzata consente di controllare se un'istanza è modificabile o non modificabili.

Se membri personalizzati, proprietà e la convalida del campo o immutabilità è importante, è consigliabile usare Visual Basic [struttura](../../../language-reference/statements/structure-statement.md) istruzione per definire un tipo di valore personalizzato.

Una tupla di Visual Basic ereditano i membri del relativo **ValueTuple** tipo. Oltre ai relativi campi, tra i metodi seguenti:

| Member | Descrizione |
| ---|---|
| CompareTo | Confronta la tupla corrente da un'altra tupla con lo stesso numero di elementi. |
| Equals | Determina se la tupla corrente è uguale a un altro oggetto o di tupla. |
| GetHashCode | Calcola il codice hash per l'istanza corrente. |
| ToString | Restituisce la rappresentazione di stringa di questa tupla, che assume la forma `(Item1, Item2...)`, dove `Item1` e `Item2` rappresentano i valori dei campi della tupla. |

Inoltre, il **ValueTuple** tipi implementano <xref:System.Collections.IStructuralComparable> e <xref:System.Collections.IStructuralEquatable> interfacce che consentono di definire operatori di confronto dei clienti.

## <a name="assignment-and-tuples"></a>Assegnazione e tuple

Visual Basic supporta l'assegnazione tra tipi di tupla che hanno lo stesso numero di campi. I tipi di campo possono essere convertiti se viene soddisfatta una delle operazioni seguenti:

- Il campo di origine e destinazione sono dello stesso tipo.

- Viene definita una conversione widening (o implicita) del tipo di origine al tipo di destinazione. 

- `Option Strict` è `On`, e viene definita una conversione narrowing (o esplicita) del tipo di origine al tipo di destinazione. Questa conversione può generare un'eccezione se il valore di origine è compreso nell'intervallo del tipo di destinazione.

Non sono considerate altre conversioni per le assegnazioni. Esaminiamo i tipi di assegnazioni consentiti tra i tipi di tupla.

Considerare le variabili usate negli esempi seguenti:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

Le prime due variabili `unnamed` e `anonymous`, non hanno nomi semantici forniti per i campi. I nomi di campo sono il valore predefinito `Item1` e `Item2`. Le ultime due variabili `named` e `differentName` hanno nomi semantici campo. Si noti che queste due tuple presentano nomi diversi per i campi.

Tutte e quattro le tuple hanno lo stesso numero di campi (detto "grado") e i tipi di tali campi sono identici. Pertanto, tutte queste assegnazioni funzionano:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Si noti che non sono assegnati i nomi delle tuple. I valori dei campi vengono assegnati seguendo l'ordine dei campi nella tupla.

Infine, si noti che è possibile assegnare il `named` tupla per il `conversion` tupla, anche se il primo campo di `named` è un `Integer`e nel primo campo della `conversion` è un `Long`. Questa assegnazione ha esito positivo perché la conversione di un `Integer` a un `Long` è una conversione verso un.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Le tuple con numeri diversi di campi non sono assegnabili:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Tuple come valori restituiti dal metodo

Un metodo può restituire un solo valore. Spesso, tuttavia, si desidera che una chiamata al metodo per restituire più valori. Esistono diversi modi per aggirare questa limitazione:

- È possibile creare una classe personalizzata o una struttura le cui proprietà o campi rappresentano i valori restituiti dal metodo. In questo modo è una soluzione ad alta densità. richiede la definizione di un tipo personalizzato di cui solo scopo consiste nel recuperare i valori da una chiamata al metodo.

- È possibile restituire un solo valore dal metodo e restituire i valori rimanenti dal passaggio per riferimento al metodo. Ciò comporta l'overhead di un'istanza di una variabile e i rischi di sovrascrivere inavvertitamente il valore della variabile che viene passato per riferimento.

- È possibile usare una tupla, che offre una soluzione semplice per il recupero di più valori restituiti.

Ad esempio, il **TryParse** metodi Return .NET un `Boolean` valore che indica se l'operazione di analisi ha avuto esito positivo. In una variabile passata per riferimento al metodo viene restituito il risultato dell'operazione di analisi. In genere, una chiamata a di un metodo di analisi, ad esempio <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> simile al seguente:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

È possibile restituire una tupla dall'operazione di analisi, se si esegue il wrapping della chiamata al <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> metodo nel nostro metodo. Nell'esempio riportato di seguito `NumericLibrary.ParseInteger` chiama il <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> metodo e restituisce una tupla con nome con due elementi. 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

È quindi possibile chiamare il metodo con codice simile al seguente:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Le tuple di Visual Basic e le tuple in .NET Framework

Una tupla di Visual Basic è un'istanza di uno dei **System. valuetuple** tipi generici, che sono state introdotte in .NET Framework 4.7. .NET Framework include anche un set del tipo generico **System. Tuple** classi. Queste classi, tuttavia, è diverso da tuple di Visual Basic e il **System. valuetuple** tipi generici in diversi modi:

- Gli elementi del **tupla** classi sono le proprietà denominate `Item1`, `Item2`e così via. In Visual Basic le tuple e il **ValueTuple** tipi, gli elementi di tupla sono campi.

- Non è possibile assegnare nomi significativi per gli elementi di un **tupla** istanza o di un **ValueTuple** istanza. Visual Basic consente di assegnare nomi comunicano il significato dei campi.

- Le proprietà di un **tupla** istanza sono di sola lettura, le tuple non sono modificabili. In Visual Basic le tuple e il **ValueTuple** tipi, campi della tupla sono in lettura / scrittura, le tuple sono modificabili.

- Il tipo generico **tupla** tipi sono tipi riferimento. Usando queste **tupla** tipi traduce nell'allocazione di oggetti. Nei percorsi critici, ciò può avere un impatto notevole sulle prestazioni dell'applicazione. Le tuple di Visual Basic e il **ValueTuple** tipi sono tipi valore.

Metodi di estensione il <xref:System.TupleExtensions> classe rendono più semplice eseguire la conversione tra .NET e Visual Basic Tuple **tupla** oggetti. Il **ToTuple** metodo converte una tupla di Visual Basic per .NET **tupla** oggetto e il **ToValueTuple** metodo converte .NET **tupla** oggetto da una tupla di Visual Basic.

L'esempio seguente crea una tupla, lo converte in .NET **tupla** oggetto e converte di nuovo in una tupla di Visual Basic. L'esempio confronta quindi la tupla con quello originale per verificare che siano uguali.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio Visual Basic](index.md)
