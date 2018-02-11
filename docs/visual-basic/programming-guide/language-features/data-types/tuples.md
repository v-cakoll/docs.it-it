---
title: Tuple in Visual Basic
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2653b9dc8a6ecbcb718c20be8bd6275edf4cfb6e
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2018
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

The version number can be any version of the Visual Basic compiler starting with 15.3. Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.

In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:

- The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.

- The candidate name is duplicated in the tuple.
 
When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime. Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`. 
  
## Tuples versus structures

A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types. For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure. It is designed to be a lightweight container for data. Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have. These include:

- Customer members. You cannot define your own properties, methods, or events for a tuple.

- Validation. You cannot validate the data assigned to fields.

- Immutability. Visual Basic tuples are mutable. In contrast, a custom structure allows you to control whether an instance is mutable or immutable.

If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.

A Visual Basic tuple does inherit the members of its **ValueTuple** type. In addition to its fields, these include the following methods:

| Member | Description |
| ---|---|
| CompareTo | Compares the current tuple to another tuple with the same number of elements. |
| Equals | Determines whether the current tuple is equal to another tuple or object. |
| GetHashCode | Calculates the hash code for the current instance. |
| ToString | Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields. |

In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.

## Assignment and tuples

Visual Basic supports assignment between tuple types that have the same number of fields. The field types can be converted if one of the following is true:

- The source and target field are of the same type.

- A widening (or implicit) conversion of the source type to the target type is defined. 

- `Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined. This conversion can throw an exception if the source value is outside the range of the target type.

Other conversions are not considered for assignments. Let's look at the kinds of assignments that are allowed between tuple types.

Consider these variables used in the following examples:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields. Their field names are the default `Item1` and `Item2`. The last two variables, `named` and `differentName` have semantic field names. Note that these two tuples have different names for the fields.

All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical. Therefore, all of these assignments work:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Notice that the names of the tuples are not assigned. The values of the fields are assigned following the order of the fields in the tuple.

Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`. This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuples with different numbers of fields are not assignable:

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
