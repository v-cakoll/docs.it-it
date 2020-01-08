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
ms.openlocfilehash: 0d259e11a969f4eb7e64626a4adf498db06ece06
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347831"
---
# <a name="nullable-value-types-visual-basic"></a>Tipi di valori nullable (Visual Basic)

Talvolta si utilizza un tipo di valore che non dispone di un valore definito in determinate circostanze. Ad esempio, un campo in un database potrebbe dover distinguere tra un valore assegnato significativo e senza un valore assegnato. I tipi di valore possono essere estesi in modo da usare i valori normali o un valore null. Tale estensione viene chiamata *tipo Nullable*.

Ogni tipo nullable viene costruito dalla struttura <xref:System.Nullable%601> generica. Si consideri un database che tiene traccia delle attività correlate al lavoro. Nell'esempio seguente viene costruito un tipo di `Boolean` nullable e viene dichiarata una variabile di quel tipo. È possibile scrivere la dichiarazione in tre modi:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

La variabile `ridesBusToWork` può conservare un valore `True`, un valore di `False`o nessun valore. Il valore predefinito iniziale non è alcun valore, che in questo caso potrebbe indicare che le informazioni non sono state ancora ottenute per questa persona. Al contrario, `False` potrebbe significare che le informazioni sono state ottenute e che la persona non ha cavalcato il bus per lavorare.

È possibile dichiarare variabili e proprietà con tipi nullable ed è possibile dichiarare una matrice con elementi di un tipo Nullable. È possibile dichiarare procedure con tipi nullable come parametri ed è possibile restituire un tipo Nullable da una procedura di `Function`.

Non è possibile costruire un tipo nullable in un tipo riferimento, ad esempio una matrice, una `String`o una classe. Il tipo sottostante deve essere un tipo valore. Per altre informazioni, vedere [Value Types and Reference Types](value-types-and-reference-types.md).

## <a name="using-a-nullable-type-variable"></a>Uso di una variabile di tipo Nullable

I membri più importanti di un tipo nullable sono le proprietà <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A>. Per una variabile di un tipo nullable, <xref:System.Nullable%601.HasValue%2A> indica se la variabile contiene un valore definito. Se <xref:System.Nullable%601.HasValue%2A> è `True`, è possibile leggere il valore da <xref:System.Nullable%601.Value%2A>. Si noti che <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A> sono proprietà `ReadOnly`.

### <a name="default-values"></a>Valori predefiniti

Quando si dichiara una variabile con un tipo nullable, il relativo <xref:System.Nullable%601.HasValue%2A> proprietà ha il valore predefinito `False`. Questo significa che per impostazione predefinita la variabile non ha un valore definito, anziché il valore predefinito del tipo di valore sottostante. Nell'esempio seguente, la variabile `numberOfChildren` inizialmente non ha un valore definito, anche se il valore predefinito del tipo di `Integer` è 0.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Un valore null è utile per indicare un valore non definito o sconosciuto. Se `numberOfChildren` stata dichiarata come `Integer`, non esiste alcun valore che potrebbe indicare che le informazioni non sono attualmente disponibili.

### <a name="storing-values"></a>Archiviazione di valori

Un valore in una variabile o in una proprietà di un tipo nullable viene archiviato in modo tipico. Nell'esempio seguente viene assegnato un valore alla variabile `numberOfChildren` dichiarata nell'esempio precedente.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Se una variabile o una proprietà di un tipo Nullable contiene un valore definito, è possibile fare in modo che venga ripristinato lo stato iniziale della mancata assegnazione di un valore. A tale scopo, impostare la variabile o la proprietà su `Nothing`, come illustrato nell'esempio riportato di seguito.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Sebbene sia possibile assegnare `Nothing` a una variabile di un tipo nullable, non è possibile eseguirne il test per `Nothing` utilizzando il segno di uguale. Il confronto che utilizza il segno di uguale `someVar = Nothing`restituisce sempre `Nothing`. È possibile testare la proprietà <xref:System.Nullable%601.HasValue%2A> della variabile per `False`o eseguire il test usando l'operatore `Is` o `IsNot`.

### <a name="retrieving-values"></a>Recupero di valori

Per recuperare il valore di una variabile di un tipo nullable, è necessario innanzitutto testare la relativa proprietà <xref:System.Nullable%601.HasValue%2A> per verificare che disponga di un valore. Se si tenta di leggere il valore quando <xref:System.Nullable%601.HasValue%2A> viene `False`, Visual Basic genera un'eccezione <xref:System.InvalidOperationException>. Nell'esempio seguente viene illustrato il modo consigliato per leggere la variabile `numberOfChildren` degli esempi precedenti.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Confronto tra tipi Nullable

Quando si utilizzano valori null `Boolean` variabili in espressioni booleane, il risultato può essere `True`, `False`o `Nothing`. Di seguito è riportata la tabella di verità per `And` e `Or`. Poiché `b1` e `b2` ora hanno tre valori possibili, è possibile valutare nove combinazioni.

|b1|b2|B1 e B2|B1 o B2|
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

Quando il valore di una variabile o di un'espressione booleana è `Nothing`, non è né `true` né `false`. Si osservi l'esempio riportato di seguito.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

In questo esempio `b1 And b2` restituisce `Nothing`. Di conseguenza, la clausola `Else` viene eseguita in ogni istruzione `If` e l'output è il seguente:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso` e `OrElse`, che usano la valutazione del cortocircuito, devono valutare i secondi operandi quando il primo restituisce `Nothing`.

## <a name="propagation"></a>Propagazione

Se uno o entrambi gli operandi di un'operazione aritmetica, di confronto, di spostamento o di tipo ammettono valori null, anche il risultato dell'operazione è nullable. Se entrambi gli operandi hanno valori che non sono `Nothing`, l'operazione viene eseguita sui valori sottostanti degli operandi, come se nessuno dei due fosse un tipo Nullable. Nell'esempio seguente le variabili `compare1` e `sum1` sono tipizzate in modo implicito. Se si posiziona il puntatore del mouse su di essi, si noterà che il compilatore deduce i tipi Nullable per entrambi.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Se uno o entrambi gli operandi hanno un valore di `Nothing`, il risultato verrà `Nothing`.

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Utilizzo di tipi nullable con dati

Un database è uno dei punti più importanti per usare i tipi nullable. Non tutti gli oggetti di database supportano attualmente i tipi nullable, ma gli adattatori di tabella generati dalla finestra di progettazione. Vedere [supporto TableAdapter per i tipi nullable](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).

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
- [Tipi di valore NullableC#()](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
