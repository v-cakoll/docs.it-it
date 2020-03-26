---
title: Tipi di valori nullable
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249682"
---
# <a name="nullable-value-types-visual-basic"></a>Tipi di valori nullable (Visual Basic)

A volte si lavora con un tipo di valore che non ha un valore definito in determinate circostanze. Ad esempio, un campo in un database potrebbe essere necessario distinguere tra avere un valore assegnato che è significativo e non avere un valore assegnato. I tipi di valore possono essere estesi per accettare i valori normali o un valore null. Tale estensione viene definita *tipo nullable*.

Ogni tipo di valore nullable <xref:System.Nullable%601> viene costruito dalla struttura generica. Si consideri un database che tiene traccia delle attività correlate al lavoro. Nell'esempio seguente viene `Boolean` creato un tipo nullable e viene dichiarata una variabile di tale tipo. È possibile scrivere la dichiarazione in tre modi:You can write the declaration in three ways:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

La `ridesBusToWork` variabile può contenere un valore pari `True`a , un valore pari `False`a o nessun valore. Il suo valore predefinito iniziale non è affatto un valore, il che in questo caso potrebbe significare che le informazioni non sono ancora state ottenute per questa persona. Al contrario, `False` potrebbe significare che le informazioni sono state ottenute e la persona non guida l'autobus per andare al lavoro.

È possibile dichiarare variabili e proprietà con tipi di valore nullable ed è possibile dichiarare una matrice con elementi di un tipo di valore nullable. È possibile dichiarare routine con tipi di valore nullable come parametri `Function` ed è possibile restituire un tipo di valore nullable da una routine.

Non è possibile costruire un tipo nullable su `String`un tipo di riferimento, ad esempio una matrice, un oggetto o una classe. Il tipo sottostante deve essere un tipo di valore. Per altre informazioni, vedere [Value Types and Reference Types](value-types-and-reference-types.md).

## <a name="using-a-nullable-type-variable"></a>Utilizzo di una variabile di tipo nullableUsing a Nullable Type Variable

I membri più importanti di un <xref:System.Nullable%601.HasValue%2A> tipo <xref:System.Nullable%601.Value%2A> di valore nullable sono le relative proprietà e . Per una variabile di un <xref:System.Nullable%601.HasValue%2A> tipo di valore nullable, indica se la variabile contiene un valore definito. Se <xref:System.Nullable%601.HasValue%2A> `True`è , è possibile <xref:System.Nullable%601.Value%2A>leggere il valore da . Si noti <xref:System.Nullable%601.Value%2A> `ReadOnly` che entrambe <xref:System.Nullable%601.HasValue%2A> e sono proprietà.

### <a name="default-values"></a>Valori predefiniti

Quando si dichiara una variabile con un <xref:System.Nullable%601.HasValue%2A> tipo di valore `False`nullable, la relativa proprietà ha un valore predefinito di . Ciò significa che per impostazione predefinita la variabile non ha alcun valore definito, anziché il valore predefinito del relativo tipo di valore sottostante. Nell'esempio seguente, `numberOfChildren` la variabile inizialmente non ha alcun valore `Integer` definito, anche se il valore predefinito del tipo è 0.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Un valore null è utile per indicare un valore non definito o sconosciuto. Se `numberOfChildren` fosse stato `Integer`dichiarato come , non vi sarebbe alcun valore che possa indicare che le informazioni non sono attualmente disponibili.

### <a name="storing-values"></a>Memorizzazione dei valori

Archiviare un valore in una variabile o proprietà di un tipo di valore nullable nel modo tipico. Nell'esempio seguente viene assegnato `numberOfChildren` un valore alla variabile dichiarata nell'esempio precedente.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Se una variabile o una proprietà di un tipo di valore nullable contiene un valore definito, è possibile fare in modo che venga ripristinato allo stato iniziale di non avere un valore assegnato. A tale scopo, impostare `Nothing`la variabile o la proprietà su , come illustrato nell'esempio seguente.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Sebbene sia `Nothing` possibile assegnare a una variabile di un `Nothing` tipo di valore nullable, non è possibile testarla utilizzando il segno di uguale. Confronto che utilizza il `someVar = Nothing`segno di `Nothing`uguale, , restituisce sempre . È possibile verificare <xref:System.Nullable%601.HasValue%2A> la `False`proprietà della variabile `Is` per `IsNot` o test utilizzando l'operatore or .

### <a name="retrieving-values"></a>Recupero di valoriRetrieving Values

Per recuperare il valore di una variabile di un tipo <xref:System.Nullable%601.HasValue%2A> di valore nullable, è innanzitutto necessario testare la relativa proprietà per verificare che abbia un valore. Se si tenta di <xref:System.Nullable%601.HasValue%2A> leggere `False`il valore quando <xref:System.InvalidOperationException> è , Visual Basic genera un'eccezione. Nell'esempio seguente viene illustrato il `numberOfChildren` modo consigliato per leggere la variabile degli esempi precedenti.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Confronto di tipi nullableComparing Nullable Types

Quando le `Boolean` variabili nullable vengono utilizzate nelle `True` `False`espressioni `Nothing`booleane, il risultato può essere , , o . Di seguito è riportata la tabella della verità per `And` e `Or`. Perché `b1` `b2` e ora hanno tre valori possibili, ci sono nove combinazioni da valutare.

|b1|B2|b1 E b2|b1 O b2|
|--------|--------|---------------|--------------|
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|
|`Nothing`|`True`|`Nothing`|`True`|
|`Nothing`|`False`|`False`|`Nothing`|
|`True`|`Nothing`|`Nothing`|`True`|
|`True`|`True`|`True`|`True`|
|`True`|`False`|`False`|`True`|
|`False`|`Nothing`|`False`|`Nothing`|
|`False`|`True`|`False`|`True`|
|`False`|`False`|`False`|`False`|

Quando il valore di una `Nothing`variabile booleana `true` `false`o di un'espressione è , non è né né . Si consideri l'esempio seguente.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

In questo `b1 And b2` esempio vengono `Nothing`valutati . Di conseguenza, `Else` la clausola `If` viene eseguita in ogni istruzione e l'output è il seguente:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso`e `OrElse`, che utilizzano la valutazione del corto circuito, devono valutare `Nothing`il secondo operandi quando il primo restituisce .

## <a name="propagation"></a>Propagazione

Se uno o entrambi gli operandi di un'operazione aritmetica, di confronto, di spostamento o di tipo è un tipo di valore nullable, il risultato dell'operazione è anche un tipo di valore nullable. Se entrambi gli operandi `Nothing`hanno valori che non lo sono , l'operazione viene eseguita sui valori sottostanti degli operandi, come se nessuno dei due fosse un tipo di valore nullable. Nell'esempio seguente, `compare1` `sum1` le variabili e sono tipizzate in modo implicito. Se si posiziona il puntatore del mouse su di essi, si noterà che il compilatore deduce i tipi di valore nullable per entrambi.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Se uno o entrambi gli operandi hanno un valore pari `Nothing`a , il risultato sarà `Nothing`.

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Utilizzo di tipi nullable con i datiUsing Nullable Types with Data

Un database è una delle posizioni più importanti in cui utilizzare i tipi di valore nullable. Non tutti gli oggetti di database supportano attualmente i tipi di valore nullable, ma gli adattatori di tabella generati dalla finestra di progettazione. Vedere [Supporto TableAdapter per i tipi nullable](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).

## <a name="see-also"></a>Vedere anche

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Tipi di dati](index.md)
- [Tipi valore e tipi di riferimento](value-types-and-reference-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](troubleshooting-data-types.md)
- [Compilare i set di dati usando oggetti TableAdapter](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [Operatore If](../../../language-reference/operators/if-operator.md)
- [Inferenza del tipo di variabile locale](../variables/local-type-inference.md)
- [Operatore Is](../../../language-reference/operators/is-operator.md)
- [Operatore IsNot](../../../language-reference/operators/isnot-operator.md)
- [Tipi di valore nullable (c ')](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
