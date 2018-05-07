---
title: Tuple in Visual Basic
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b2c8205dd413b1749d181daa8d0e84d62534e28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="tuples-visual-basic"></a>Tuple (Visual Basic)

A partire da Visual Basic 2017, il linguaggio Visual Basic offre supporto incorporato per le tuple che rende la creazione di tuple e accedere agli elementi di tuple più semplice. Una tupla è una struttura di dati più semplice con un numero specifico e la sequenza di valori. Quando si crea un'istanza di tupla, si definisce il numero e il tipo di dati di ogni valore (o elemento). Ad esempio, una tupla con 2 elementi (o coppia) dispone di due elementi. Potrebbe essere il primo un `Boolean` valore, mentre il secondo è un `String`. Poiché le tuple semplificano archiviare più valori in un singolo oggetto, vengono spesso utilizzati come un modo semplice per restituire più valori da un metodo.

> [!IMPORTANT]
> Supporto di tuple richiede il <xref:System.ValueTuple> tipo. Se non è installato il 4.7 di .NET Framework, è necessario aggiungere il pacchetto NuGet `System.ValueTuple`, che è disponibile nella raccolta NuGet. Senza questo pacchetto, è possibile che venga visualizzato un errore di compilazione simile a "Tipo predefinito 'ValueTuple(Of,,,)' non è definito né importato."

## <a name="instantiating-and-using-a-tuple"></a>Creazione e utilizzo di una tupla

L'istanza di una tupla racchiudendo le sue parentesi im valori delimitato da virgole. Tali valori diventa quindi un campo della tupla. Ad esempio, il codice seguente definisce una triple (o una tupla con 3 elementi) con un `Date` come primo valore, un `String` come il secondo e un `Boolean` come il rispettivo terzo.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

Per impostazione predefinita, il nome di ogni campo in una tupla è costituita da stringa `Item` insieme posizione in base 1 del campo nella tupla. Per questo tupla con 3 elementi, il `Date` campo è `Item1`, `String` campo è `Item2`e `Boolean` campo è `Item3`. L'esempio seguente mostra i valori dei campi della tupla creata nella riga di codice precedente

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

I campi di una tupla di Visual Basic sono di lettura-scrittura. Dopo aver creato l'istanza di una tupla, è possibile modificare i relativi valori. Nell'esempio seguente modifica due dei tre campi della tupla creata nell'esempio precedente e viene visualizzato il risultato.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Creazione di un'istanza e l'utilizzo di una tupla denominata

Anziché utilizzare i nomi predefiniti per i campi di una tupla, è possibile creare un'istanza di un *denominato tupla* assegnando nomi personalizzati agli elementi della tupla. I campi della tupla è possibile accedere tramite i nomi assegnati *o* con i relativi nomi predefinito. Nell'esempio seguente viene creata un'istanza la tupla di 3 stesso come in precedenza, ad eccezione del fatto che determina in modo esplicito il nome del primo campo `EventDate`, il secondo `Name`e il terzo `IsHoliday`. Quindi Visualizza i valori dei campi, li modifica e visualizza i valori dei campi nuovamente.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>Nomi di elemento dedotto tupla

A partire da 15.3 Visual Basic, Visual Basic in grado di dedurre i nomi di elementi di tupla. non è necessario assegnare loro in modo esplicito. Nomi derivati tupla sono utili quando si Inizializza una tupla da un set di variabili e si desidera che il nome dell'elemento tupla per corrispondere al nome della variabile. 

Nell'esempio seguente viene creato un `stateInfo` tupla che contiene tre in modo esplicito elementi, denominati `state`, `stateName`, e `capital`. Si noti che, quando si assegna gli elementi, l'istruzione di inizializzazione di tupla, viene semplicemente assegnata agli elementi denominati i valori delle variabili denominate in modo identico.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
Poiché gli elementi e le variabili hanno lo stesso nome, il compilatore Visual Basic può dedurre i nomi dei campi, come illustrato nell'esempio seguente.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Per abilitare i nomi degli elementi interred tupla, è necessario definire la versione del compilatore Visual Basic da utilizzare nel progetto Visual Basic (\*. vbproj) file: 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 
```

Il numero di versione può essere qualsiasi versione del compilatore Visual Basic a partire da 15.3. Anziché a livello di codice una specifica versione del compilatore, è inoltre possibile specificare "Più recente" come valore di `LangVersion` per la compilazione con la versione più recente del compilatore Visual Basic installato nel sistema.

In alcuni casi, il compilatore Visual Basic non è possibile dedurre il nome dell'elemento tupla dal nome del candidato, e il campo di tupla può fare riferimento solo utilizzando il nome predefinito, ad esempio `Item1`, `Item2`e così via. Sono inclusi:

- Il nome candidato è identico al nome di un membro di tupla, ad esempio `Item3`, `Rest`, o `ToString`.

- Il nome del candidato è duplicato nella tupla.
 
Quando l'inferenza del nome di campo non riesce, non genera un errore del compilatore Visual Basic, né è un'eccezione generata in fase di esecuzione. Invece, i campi di tupla devono fare riferimento i nomi predefiniti, ad esempio `Item1` e `Item2`. 
  
## <a name="tuples-versus-structures"></a>Tuple e strutture

Una tupla di Visual Basic è un tipo di valore che rappresenta un'istanza di uno dell'un **System.ValueTuple** tipi generici. Ad esempio, il `holiday` tupla definita nell'esempio precedente è un'istanza del <xref:System.ValueTuple%603> struttura. È progettato per essere un semplice contenitore di dati. Poiché la tupla mira a semplificare creare un oggetto con più elementi di dati, mancano alcune delle funzionalità che potrebbe avere una struttura personalizzata. Sono inclusi:

- Membri personalizzati. È possibile definire la propria proprietà, metodi o eventi per una tupla.

- Convalida. È possibile convalidare i dati assegnati ai campi.

- Immutabilità. Tuple di Visual Basic sono modificabili. Al contrario, una struttura personalizzata consente di controllare se un'istanza è modificabile o non modificabile.

Se l'immutabilità, proprietà e la convalida dei campi o membri personalizzati sono importanti, è necessario utilizzare Visual Basic [struttura](../../../language-reference/statements/structure-statement.md) istruzione per definire un tipo di valore personalizzato.

Una tupla di Visual Basic ereditano i membri del relativo **ValueTuple** tipo. Oltre ai relativi campi, tra cui i metodi seguenti:

| Member | Descrizione |
| ---|---|
| CompareTo | Confronta la tupla corrente a un altro tupla con lo stesso numero di elementi. |
| Equals | Determina se la tupla corrente è uguale a un altro oggetto o di tupla. |
| GetHashCode | Calcola il codice hash per l'istanza corrente. |
| ToString | Restituisce la rappresentazione di stringa di questo tupla, che assume il formato `(Item1, Item2...)`, dove `Item1` e `Item2` rappresentano i valori dei campi della tupla. |

Inoltre, il **ValueTuple** tipi implementano <xref:System.Collections.IStructuralComparable> e <xref:System.Collections.IStructuralEquatable> interfacce che consentono di definire gli operatori di confronto di cliente.

## <a name="assignment-and-tuples"></a>Assegnazione e tuple

Visual Basic supporta l'assegnazione tra i tipi di tupla che hanno lo stesso numero di campi. I tipi di campo possono essere convertiti in presenza di una delle operazioni seguenti:

- Il campo di origine e destinazione sono dello stesso tipo.

- Una conversione widening (o implicita) del tipo di origine al tipo di destinazione è definita. 

- `Option Strict` è `On`, e viene definita una conversione di narrowing (o esplicita) del tipo di origine al tipo di destinazione. Questa conversione può generare un'eccezione se il valore di origine è compreso nell'intervallo del tipo di destinazione.

Non sono considerate altre conversioni per le assegnazioni. Esaminiamo i tipi di assegnazioni consentiti tra i tipi di tupla.

Considerare le variabili usate negli esempi seguenti:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

Le prime due variabili `unnamed` e `anonymous`, non hanno nomi semantici forniti per i campi. I nomi di campo sono il valore predefinito `Item1` e `Item2`. Le ultime due variabili, `named` e `differentName` hanno nomi di campo semantica. Si noti che queste due tuple presentano nomi diversi per i campi.

Tutte e quattro le tuple hanno lo stesso numero di campi (detto 'grado') e i tipi di tali campi sono identici. Pertanto, tutte queste assegnazioni funzionano:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Si noti che non sono assegnati i nomi delle tuple. I valori dei campi vengono assegnati seguendo l'ordine dei campi nella tupla.

Infine, si noti che è possibile assegnare il `named` tupla per la `conversion` tupla, anche se il primo campo di `named` è un `Integer`e il primo campo di `conversion` è un `Long`. Questa assegnazione viene completata perché la conversione di un `Integer` per un `Long` è una conversione di ampliamento.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuple con numeri diversi di campi non sono assegnabili:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Tuple come valori restituiti dal metodo

Un metodo può restituire un solo valore. Spesso, tuttavia, si desidera che una chiamata al metodo per restituire più valori. Esistono diversi modi per risolvere questa limitazione:

- È possibile creare una classe personalizzata o una struttura le cui proprietà o campi rappresentano i valori restituiti dal metodo. In questo modo è una soluzione ad alta densità; è necessario definire un tipo personalizzato, il cui unico scopo consiste nel recuperare i valori da una chiamata al metodo.

- È possibile restituire un solo valore dal metodo e restituire i valori rimanenti dal passaggio per riferimento al metodo. Ciò comporta l'overhead di un'istanza di una variabile e i rischi per la sovrascrittura accidentale del valore della variabile che viene passato per riferimento.

- È possibile utilizzare una tupla, che fornisce una soluzione semplice per il recupero di più valori restituiti.

Ad esempio, il **TryParse** metodi ritorno .NET un `Boolean` valore che indica se l'operazione di analisi ha avuto esito positivo. In una variabile passata per riferimento al metodo viene restituito il risultato dell'operazione di analisi. In genere, una chiamata a di un metodo di analisi, ad esempio <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> sarà simile alla seguente:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

È possibile tornare una tupla da operazione di analisi, si esegue il wrapping della chiamata al <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> nel metodo di un metodo. Nell'esempio seguente, `NumericLibrary.ParseInteger` chiamate di <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> (metodo) e restituisce una tupla con due elementi denominata. 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

È quindi possibile chiamare il metodo con il codice seguente:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Tuple di Visual Basic e le tuple in .NET Framework

Una tupla di Visual Basic è un'istanza di uno del **System.ValueTuple** tipi generici, che sono stati introdotti i 4.7 di .NET Framework. .NET Framework include anche un set di generico **System. Tuple** classi. Queste classi, tuttavia, diversi da tuple di Visual Basic e **System.ValueTuple** tipi generici in diversi modi:

- Gli elementi del **tupla** classi sono le proprietà denominate `Item1`, `Item2`e così via. In Visual Basic tuple e **ValueTuple** campi sono i tipi, degli elementi della tupla.

- Non è possibile assegnare nomi significativi per gli elementi di un **tupla** istanza o di un **ValueTuple** istanza. Visual Basic consente di assegnare i nomi con comunicano il significato dei campi.

- Le proprietà di un **tupla** istanza sono di sola lettura; le tuple sono modificabili. In Visual Basic tuple e **ValueTuple** tipi, campi di tupla sono di lettura / scrittura; le tuple sono modificabili.

- Il tipo generico **tupla** tipi sono tipi di riferimento. Utilizzo di queste **tupla** tipi significa allocazione di oggetti. Nei percorsi critici, ciò può avere un impatto notevole sulle prestazioni dell'applicazione. Visual Basic tuple e **ValueTuple** tipi sono tipi di valore.

Metodi di estensione di <xref:System.TupleExtensions> classe rendono più facile eseguire la conversione tra .NET e Visual Basic Tuple **tupla** oggetti. Il **ToTuple** metodo converte una tupla di Visual Basic .NET **tupla** oggetto e **ToValueTuple** metodo converte .NET **tupla** oggetto da una tupla di Visual Basic.

L'esempio seguente crea una tupla, viene convertito in .NET **tupla** oggetto e converte di nuovo in una tupla di Visual Basic. Nell'esempio viene quindi confrontato con questo tupla con quello originale per verificare che siano uguali.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Vedere anche

[Riferimenti per il linguaggio Visual Basic](index.md)  
