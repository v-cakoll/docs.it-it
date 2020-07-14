---
title: Tuple
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: 378ee4e7d3a3b106b719e5da819b09f336ff218e
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226660"
---
# <a name="tuples-visual-basic"></a>Tuple (Visual Basic)

A partire da Visual Basic 2017, il linguaggio Visual Basic offre supporto incorporato per le tuple che semplificano la creazione di tuple e l'accesso agli elementi delle tuple. Una tupla è una struttura di dati leggera con un numero e una sequenza di valori specifici. Quando si crea un'istanza della tupla, si definiscono il numero e il tipo di dati di ogni valore (o elemento). Ad esempio, una tupla con 2 elementi (o coppia) dispone di due elementi. Il primo può essere un `Boolean` valore, mentre il secondo è `String` . Poiché le tuple semplificano l'archiviazione di più valori in un singolo oggetto, vengono spesso usati come metodo semplice per restituire più valori da un metodo.

> [!IMPORTANT]
> Il supporto della tupla richiede il <xref:System.ValueTuple> tipo. Se il .NET Framework 4,7 non è installato, è necessario aggiungere il pacchetto NuGet `System.ValueTuple` , disponibile nella raccolta NuGet. Senza questo pacchetto, potrebbe essere presente un errore di compilazione simile a "il tipo predefinito ' ValueTuple (of,,,)' non è definito né importato".

## <a name="instantiating-and-using-a-tuple"></a>Creazione di istanze e utilizzo di una tupla

Si crea un'istanza di una tupla racchiudendo tra parentesi i valori delimitati da virgole. Ognuno di questi valori diventa quindi un campo della tupla. Il codice seguente, ad esempio, definisce una tripla (o una tupla con 3 elementi) con un `Date` come primo valore, un `String` come secondo e un `Boolean` come terzo.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

Per impostazione predefinita, il nome di ogni campo in una tupla è costituito dalla stringa `Item` insieme alla posizione in base 1 del campo nella tupla. Per questa tupla con 3 elementi, il campo è `Date` `Item1` , il campo `String` è `Item2` e il `Boolean` campo è `Item3` . Nell'esempio seguente vengono visualizzati i valori dei campi della tupla di cui è stata creata un'istanza nella riga di codice precedente

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

I campi di una tupla Visual Basic sono di lettura/scrittura; Dopo avere creato un'istanza di una tupla, è possibile modificarne i valori. Nell'esempio seguente vengono modificati due dei tre campi della tupla creata nell'esempio precedente e viene visualizzato il risultato.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Creazione di istanze e utilizzo di una tupla denominata

Anziché utilizzare nomi predefiniti per i campi di una tupla, è possibile creare un'istanza di una *tupla denominata* assegnando nomi personalizzati agli elementi della tupla. È possibile accedere ai campi della tupla in base ai nomi assegnati *o* ai nomi predefiniti. Nell'esempio seguente viene creata un'istanza della stessa tupla con 3 elementi, ad eccezione del fatto che assegna in modo esplicito il nome del primo campo `EventDate` , il secondo `Name` e il terzo `IsHoliday` . Visualizza quindi i valori dei campi, li modifica e visualizza di nuovo i valori dei campi.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>Nomi di elemento di tupla dedotti

A partire da Visual Basic 15,3, Visual Basic possibile dedurre i nomi degli elementi della tupla. non è necessario assegnarli in modo esplicito. I nomi di tupla dedotti sono utili quando si Inizializza una tupla da un set di variabili e si desidera che il nome dell'elemento di tupla corrisponda al nome della variabile.

Nell'esempio seguente viene creata una `stateInfo` tupla contenente tre elementi denominati in modo esplicito,, `state` `stateName` e `capital` . Si noti che, nella denominazione degli elementi, l'istruzione di inizializzazione della tupla assegna semplicemente gli elementi denominati ai valori delle variabili denominate in modo identico.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]

Poiché gli elementi e le variabili hanno lo stesso nome, il Visual Basic compilatore può dedurre i nomi dei campi, come illustrato nell'esempio riportato di seguito.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Per abilitare i nomi di elementi di tupla derivati, è necessario definire la versione del compilatore Visual Basic da usare nel file del progetto di Visual Basic ( \* . vbproj):

```xml
<PropertyGroup>
  <LangVersion>15.3</LangVersion>
</PropertyGroup>
```

Il numero di versione può essere qualsiasi versione del compilatore Visual Basic a partire da 15,3. Anziché impostare come hardcoded una versione specifica del compilatore, è anche possibile specificare "più recente" come valore di `LangVersion` per la compilazione con la versione più recente del compilatore di Visual Basic installato nel sistema.

Per ulteriori informazioni, vedere [impostazione della versione della lingua Visual Basic](../../../language-reference/configure-language-version.md).

In alcuni casi, il compilatore Visual Basic non è in grado di dedurre il nome dell'elemento di tupla dal nome del candidato e il campo tupla può essere usato solo con il nome predefinito, ad esempio, e così `Item1` `Item2` via. Sono incluse le seguenti:

- Il nome del candidato corrisponde al nome di un membro di tupla, ad esempio `Item3` , `Rest` o `ToString` .

- Il nome candidato viene duplicato nella tupla.

Quando l'inferenza del nome campo ha esito negativo, Visual Basic non genera un errore del compilatore, né un'eccezione generata in fase di esecuzione. Al contrario, è necessario fare riferimento ai campi di tupla con i relativi nomi predefiniti, ad esempio `Item1` e `Item2` .

## <a name="tuples-versus-structures"></a>Tuple e strutture

Una tupla Visual Basic è un tipo di valore che è un'istanza di uno dei tipi generici **System. ValueTuple** . Ad esempio, la `holiday` tupla definita nell'esempio precedente è un'istanza della <xref:System.ValueTuple%603> struttura. È progettato per essere un contenitore leggero per i dati. Poiché la tupla ha lo scopo di semplificare la creazione di un oggetto con più elementi di dati, mancano alcune delle funzionalità che possono avere una struttura personalizzata. Tra queste sono incluse:

- Membri personalizzati. Non è possibile definire proprietà, metodi o eventi personalizzati per una tupla.

- Convalida. Non è possibile convalidare i dati assegnati ai campi.

- Immutabilità. Visual Basic tuple sono modificabili. Una struttura personalizzata, invece, consente di controllare se un'istanza è modificabile o non modificabile.

Se i membri personalizzati, la convalida di proprietà e campi o l'immutabilità sono importanti, è consigliabile utilizzare l'istruzione Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) per definire un tipo di valore personalizzato.

Una tupla Visual Basic eredita i membri del tipo **ValueTuple** . Oltre ai relativi campi, includono i metodi seguenti:

| Membro | Descrizione |
| ---|---|
| CompareTo | Confronta la tupla corrente con un'altra tupla con lo stesso numero di elementi. |
| Uguale a | Determina se la tupla corrente è uguale a un'altra tupla o a un altro oggetto. |
| GetHashCode | Calcola il codice hash per l'istanza corrente. |
| ToString | Restituisce la rappresentazione di stringa di questa tupla, che assume il formato `(Item1, Item2...)` , dove `Item1` e `Item2` rappresentano i valori dei campi della tupla. |

Inoltre, i tipi **ValueTuple** implementano <xref:System.Collections.IStructuralComparable> le <xref:System.Collections.IStructuralEquatable> interfacce e, che consentono di definire gli operatori di confronto dei clienti.

## <a name="assignment-and-tuples"></a>Assegnazione e tuple

Visual Basic supporta l'assegnazione tra tipi di tupla che hanno lo stesso numero di campi. I tipi di campo possono essere convertiti se si verifica una delle condizioni seguenti:

- Il campo di origine e di destinazione sono dello stesso tipo.

- Viene definita una conversione verso un tipo di dati più ampio o implicito del tipo di origine nel tipo di destinazione.

- `Option Strict`è `On` e viene definita una conversione verso un tipo di dati più piccolo (o esplicito) del tipo di origine nel tipo di destinazione. Questa conversione può generare un'eccezione se il valore di origine non è compreso nell'intervallo del tipo di destinazione.

Non sono considerate altre conversioni per le assegnazioni. Esaminiamo i tipi di assegnazioni consentiti tra i tipi di tupla.

Considerare le variabili usate negli esempi seguenti:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

Le prime due variabili, `unnamed` e `anonymous` , non hanno nomi semantici forniti per i campi. I nomi dei campi sono i valori predefiniti `Item1` e `Item2` . Le ultime due variabili `named` e `differentName` hanno nomi di campo semantico. Si noti che queste due tuple presentano nomi diversi per i campi.

Tutte e quattro le tuple hanno lo stesso numero di campi (definito "grado") e i tipi di tali campi sono identici. Pertanto, tutte queste assegnazioni funzionano:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Si noti che non sono assegnati i nomi delle tuple. I valori dei campi vengono assegnati seguendo l'ordine dei campi nella tupla.

Si noti infine che è possibile assegnare la `named` tupla alla `conversion` tupla, anche se il primo campo di `named` è un `Integer` e il primo campo di `conversion` è `Long` . Questa assegnazione ha esito positivo perché `Integer` la conversione di un oggetto in è una conversione verso un tipo di oggetto più `Long` ampio

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Le tuple con numeri diversi di campi non possono essere assegnate:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Tuple come valori restituiti dal metodo

Un metodo può restituire solo un valore singolo. Spesso, tuttavia, si vuole che una chiamata al metodo restituisca più valori. Esistono diversi modi per ovviare a questa limitazione:

- È possibile creare una classe o una struttura personalizzata le cui proprietà o campi rappresentano i valori restituiti dal metodo. Quindi è una soluzione pesante; è necessario definire un tipo personalizzato il cui unico scopo è recuperare i valori da una chiamata al metodo.

- È possibile restituire un singolo valore dal metodo e restituire i valori rimanenti passandoli per riferimento al metodo. Questo implica il sovraccarico della creazione di un'istanza di una variabile e rischia di sovrascrivere inavvertitamente il valore della variabile passata per riferimento.

- È possibile utilizzare una tupla, che fornisce una soluzione leggera per il recupero di più valori restituiti.

Ad esempio, i metodi **TryParse** in .NET restituiscono un `Boolean` valore che indica se l'operazione di analisi ha avuto esito positivo. Il risultato dell'operazione di analisi viene restituito in una variabile passata per riferimento al metodo. In genere, una chiamata al metodo di analisi, ad esempio, ha un <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> aspetto simile al seguente:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

Se si esegue il wrapping della chiamata al <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> metodo nel metodo personalizzato, è possibile restituire una tupla dall'operazione di analisi. Nell'esempio seguente viene `NumericLibrary.ParseInteger` chiamato il <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> metodo e viene restituita una tupla denominata con due elementi.

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

È quindi possibile chiamare il metodo con codice simile al seguente:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Visual Basic Tuple e Tuple nell'.NET Framework

Una tupla Visual Basic è un'istanza di uno dei tipi generici **System. ValueTuple** introdotti nella .NET Framework 4,7. Il .NET Framework include anche un set di classi **System. Tuple** generiche. Queste classi, tuttavia, differiscono da Visual Basic Tuple e dai tipi generici **System. ValueTuple** in diversi modi:

- Gli elementi delle classi **Tuple** sono proprietà denominate `Item1` , `Item2` e così via. In Visual Basic Tuple e i tipi **ValueTuple** , gli elementi della tupla sono campi.

- Non è possibile assegnare nomi significativi agli elementi di un'istanza di **tupla** o di un'istanza di **ValueTuple** . Visual Basic consente di assegnare nomi che comunicano il significato dei campi.

- Le proprietà di un'istanza di **tupla** sono di sola lettura. le tuple non sono modificabili. In Visual Basic Tuple e i tipi **ValueTuple** , i campi di tupla sono di lettura/scrittura; le tuple sono modificabili.

- I tipi di **tupla** generici sono tipi di riferimento. L'utilizzo di questi tipi di **tupla** indica l'allocazione di oggetti. Nei percorsi critici, ciò può avere un impatto notevole sulle prestazioni dell'applicazione. Visual Basic Tuple e i tipi **ValueTuple** sono tipi di valore.

I metodi di estensione nella <xref:System.TupleExtensions> classe facilitano la conversione tra Visual Basic Tuple e gli oggetti **tupla** .NET. Il metodo **ToTuple** converte una tupla di Visual Basic in un oggetto **tupla** .NET e il metodo **ToValueTuple** converte un oggetto **tupla** .NET in una tupla di Visual Basic.

Nell'esempio seguente viene creata una tupla, viene convertita in un oggetto **tupla** .NET e riconvertita in una tupla Visual Basic. Nell'esempio viene quindi confrontata la tupla con quella originale per verificare che siano uguali.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti al linguaggio Visual Basic](index.md)
