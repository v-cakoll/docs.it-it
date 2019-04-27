---
title: Tipi di valore nullable - Visual Basic
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
ms.openlocfilehash: d17d2ad3fd99c6d563c21ddd646396ccb1c1ca48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008228"
---
# <a name="nullable-value-types-visual-basic"></a>Tipi di valori nullable (Visual Basic)

In alcuni casi si lavora con un tipo di valore che non hanno un valore definito in determinate circostanze. Ad esempio, un campo in un database potrebbe essere necessario distinguere tra l'assegnazione di un valore significativo e che non presentano un valore assegnato. I tipi di valore possono essere esteso per sfruttare i relativi valori normale o un valore null. Tale estensione viene chiamato un *tipo nullable*.

Ogni tipo che ammette valori null viene costruito dal modello generico <xref:System.Nullable%601> struttura. Si consideri un database che tiene traccia delle attività correlate al lavoro. L'esempio seguente crea un valore nullable `Boolean` digitare e viene dichiarata una variabile di quel tipo. È possibile scrivere la dichiarazione in tre modi:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

La variabile `ridesBusToWork` può contenere un valore di `True`, un valore di `False`, o nessun valore. Il valore predefinito iniziale non è alcun valore, che in questo caso potrebbe significare che le informazioni non ha ancora ottenute per tale persona. Al contrario, `False` potrebbe significare che sono state ottenute le informazioni e la persona non recarsi il bus di funzionamento.

È possibile dichiarare le variabili e le proprietà con tipi nullable, ed è possibile dichiarare una matrice con elementi di un tipo nullable. È possibile dichiarare le procedure con tipi nullable come parametri, e si può restituire un tipo nullable da un `Function` procedure.

Impossibile costruire un tipo nullable in un tipo riferimento, ad esempio una matrice, un `String`, o una classe. Il tipo sottostante deve essere un tipo di valore. Per altre informazioni, vedere [Value Types and Reference Types](value-types-and-reference-types.md).

## <a name="using-a-nullable-type-variable"></a>Utilizzo di una variabile di tipo Nullable

I membri più importanti di un tipo che ammette valori null sono relativi <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A> proprietà. Per una variabile di un tipo nullable, <xref:System.Nullable%601.HasValue%2A> indica se la variabile contiene un valore definito. Se <xref:System.Nullable%601.HasValue%2A> viene `True`, è possibile leggere il valore da <xref:System.Nullable%601.Value%2A>. Si noti che entrambe <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A> sono `ReadOnly` proprietà.

### <a name="default-values"></a>Valori predefiniti

Quando si dichiara una variabile con un tipo che ammette valori null, relative <xref:System.Nullable%601.HasValue%2A> proprietà ha un valore predefinito di `False`. Ciò significa che per impostazione predefinita la variabile non ha valore definito, anziché il valore predefinito del relativo tipo di valore sottostante. Nell'esempio seguente, la variabile `numberOfChildren` inizialmente non ha valore definito, anche se il valore predefinito di `Integer` tipo è 0.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Un valore null è utile per indicare un valore sconosciuto o non definito. Se `numberOfChildren` fosse stato dichiarato come `Integer`, non vi sarà alcun valore che potrebbe indicare che le informazioni non sono attualmente disponibili.

### <a name="storing-values"></a>L'archiviazione dei valori

Archiviare un valore in una variabile o proprietà di un tipo che ammette valori null nel modo usuale. L'esempio seguente assegna un valore alla variabile `numberOfChildren` dichiarato nell'esempio precedente.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Se una variabile o una proprietà di un tipo nullable contiene un valore definito, è possibile che vengano tornerà allo stato iniziale di non avere un valore assegnato. Eseguire questa operazione impostando la variabile o proprietà `Nothing`, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Sebbene sia possibile assegnare `Nothing` a una variabile di un tipo nullable, è possibile testarlo per `Nothing` con il segno di uguale. Confronto che usa il segno di uguale `someVar = Nothing`, restituisce sempre `Nothing`. È possibile testare la variabile <xref:System.Nullable%601.HasValue%2A> proprietà per `False`, o di test usando la `Is` o `IsNot` operatore.

### <a name="retrieving-values"></a>Recupero di valori

Per recuperare il valore di una variabile di un tipo nullable, è necessario innanzitutto testare relativo <xref:System.Nullable%601.HasValue%2A> proprietà per confermare che ha un valore. Se si prova a leggere il valore quando <xref:System.Nullable%601.HasValue%2A> viene `False`, Visual Basic genera un <xref:System.InvalidOperationException> eccezione. Nell'esempio seguente viene illustrato il modo consigliato per la lettura della variabile `numberOfChildren` degli esempi precedenti.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Confronto tra i tipi Nullable

Quando nullable `Boolean` variabili vengono usate in espressioni booleane, possono verificarsi `True`, `False`, o `Nothing`. Di seguito è riportato nella tabella di verità per `And` e `Or`. In quanto `b1` e `b2` disporrà di tre valori possibili, sono presenti nove combinazioni da valutare.

|b1|b2|B1 e b2|B1 o b2|
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

Quando è il valore di una variabile booleana o espressione `Nothing`, non è né `true` né `false`. Si osservi l'esempio riportato di seguito.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

In questo esempio `b1 And b2` restituisca `Nothing`. Di conseguenza, il `Else` clausola viene eseguita in ogni `If` istruzione e l'output è come segue:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso` e `OrElse`, che usano la valutazione, short circuit deve restituire i relativi operandi secondo quando restituisce il primo `Nothing`.

## <a name="propagation"></a>Propagazione

Se uno o entrambi gli operandi di un aritmetica, di confronto, MAIUSC o operazione di tipo è nullable, anche il risultato dell'operazione è nullable. Se entrambi gli operandi hanno valori diversi da quelli `Nothing`, l'operazione viene eseguita sui valori sottostanti degli operandi, come se non fossero un tipo nullable. Nell'esempio seguente, le variabili `compare1` e `sum1` sono tipizzate in modo implicito. Se si posiziona il puntatore del mouse su di essi, si noterà che il compilatore deduce i tipi nullable per entrambi.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Se il valore di uno o entrambi gli operandi `Nothing`, il risultato sarà `Nothing`.

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Utilizzo dei tipi Nullable con dati

Un database è uno dei posti più importanti da usare tipi nullable. Non tutti gli oggetti di database attualmente supportano i tipi nullable, mentre gli adattatori di tabella generati dalla finestra di progettazione. Visualizzare [TableAdapter supporto per i tipi nullable](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).

## <a name="see-also"></a>Vedere anche

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Uso dei tipi nullable](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [Tipi di dati](index.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](troubleshooting-data-types.md)
- [Compilare i set di dati usando oggetti TableAdapter](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [Operatore If](../../../language-reference/operators/if-operator.md)
- [Inferenza del tipo di variabile locale](../variables/local-type-inference.md)
- [Operatore Is](../../../language-reference/operators/is-operator.md)
- [Operatore IsNot](../../../language-reference/operators/isnot-operator.md)