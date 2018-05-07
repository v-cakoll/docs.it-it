---
title: Tipi di valori nullable (Visual Basic)
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
ms.openlocfilehash: bb44ad85347b494b63dde964b2b407d8f038f2b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="nullable-value-types-visual-basic"></a>Tipi di valori nullable (Visual Basic)
A volte si lavora con un tipo di valore che non dispone di un valore definito in determinate circostanze. Ad esempio, un campo in un database potrebbe essere necessario distinguere tra l'assegnazione di un valore che è significativo e non con un valore assegnato. Tipi di valore possono essere esteso per i relativi valori normale o un valore null. Tale estensione viene chiamato un *tipo nullable*.  
  
 Ogni tipo che ammette valori null viene costruita dal modello generico <xref:System.Nullable%601> struttura. Si consideri un database che tiene traccia delle attività relative al lavoro. L'esempio seguente crea un oggetto nullable `Boolean` digitare e dichiara una variabile di quel tipo. È possibile scrivere la dichiarazione in tre modi:  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]  
  
 La variabile `ridesBusToWork` può contenere un valore di `True`, un valore di `False`, o nessun valore. Il valore predefinito iniziale è alcun valore, che in questo caso potrebbe indicare che le informazioni non ha ancora ottenute per questo utente. Al contrario, `False` potrebbe significare che sono state ottenute le informazioni e la persona non sostituire il bus di lavoro.  
  
 È possibile dichiarare variabili e proprietà con tipi nullable ed è possibile dichiarare una matrice con elementi di un tipo nullable. È possibile dichiarare procedure con tipi nullable, come parametri ed è possibile restituire un tipo nullable da un `Function` stored procedure.  
  
 È possibile creare un tipo che ammette valori null in un tipo riferimento, ad esempio una matrice, un `String`, o una classe. Il tipo sottostante deve essere un tipo di valore. Per ulteriori informazioni, vedere [tipi di valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## <a name="using-a-nullable-type-variable"></a>Utilizzo di una variabile di tipo Nullable  
 I membri di un tipo nullable più importanti sono relativi <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A> proprietà. Per una variabile di tipo nullable, <xref:System.Nullable%601.HasValue%2A> indica se la variabile contiene un valore definito. Se <xref:System.Nullable%601.HasValue%2A> è `True`, è possibile leggere il valore <xref:System.Nullable%601.Value%2A>. Si noti che entrambi <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A> sono `ReadOnly` proprietà.  
  
### <a name="default-values"></a>Valori predefiniti  
 Quando si dichiara una variabile con un tipo nullable, il relativo <xref:System.Nullable%601.HasValue%2A> proprietà ha un valore predefinito di `False`. Ciò significa che per impostazione predefinita la variabile non ha valore definito, anziché il valore predefinito del relativo tipo di valore sottostante. Nell'esempio seguente, la variabile `numberOfChildren` non dispone inizialmente di alcun valore, definito anche se il valore predefinito di `Integer` tipo è 0.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]  
  
 Un valore null è utile per indicare un valore non definito o sconosciuto. Se `numberOfChildren` è stato dichiarato come `Integer`, non vi sarà alcun valore che potrebbe indicare che le informazioni non sono attualmente disponibili.  
  
### <a name="storing-values"></a>L'archiviazione di valori  
 Archiviare un valore in una variabile o proprietà di un tipo che ammette valori null nel modo usuale. Nell'esempio seguente assegna un valore alla variabile `numberOfChildren` dichiarato nell'esempio precedente.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]  
  
 Se una variabile o proprietà di un tipo nullable contiene un valore definito, è possibile causarne ripristinare lo stato iniziale di non avere un valore assegnato. Eseguire questa operazione impostando la variabile o proprietà `Nothing`, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]  
  
> [!NOTE]
>  Sebbene sia possibile assegnare `Nothing` a una variabile di un tipo nullable, è possibile eseguirne il test per `Nothing` utilizzando il segno di uguale. Confronto che utilizza il segno di uguale, `someVar = Nothing`, restituisce sempre `Nothing`. È possibile testare la variabile <xref:System.Nullable%601.HasValue%2A> proprietà `False`, o di test utilizzando il `Is` o `IsNot` operatore.  
  
### <a name="retrieving-values"></a>Recupero di valori  
 Per recuperare il valore di una variabile di tipo nullable, è necessario testare la <xref:System.Nullable%601.HasValue%2A> proprietà per confermare che ha un valore. Se si tenta di leggere il valore quando <xref:System.Nullable%601.HasValue%2A> viene `False`, Visual Basic genera un <xref:System.InvalidOperationException> (eccezione). Nell'esempio seguente viene illustrato il modo consigliato per la lettura della variabile `numberOfChildren` gli esempi precedenti.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]  
  
## <a name="comparing-nullable-types"></a>Il confronto dei tipi Nullable  
 Quando nullable `Boolean` vengono utilizzate variabili nelle espressioni booleane, il risultato può essere `True`, `False`, o `Nothing`. Di seguito è la tabella della verità per `And` e `Or`. Poiché `b1` e `b2` ora hanno tre possibili valori, sono disponibili nove combinazioni da valutare.  
  
|B1|B2|B1 e b2|B1 o b2|  
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
  
 Quando il valore di una variabile o espressione booleana è `Nothing`, nessuno dei due è `true` né `false`. Si osservi l'esempio riportato di seguito.  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]  
  
 In questo esempio, `b1 And b2` restituisce `Nothing`. Di conseguenza, il `Else` clausola viene eseguita in ogni `If` istruzione e l'output è indicato di seguito:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso` e `OrElse`, valutazione, di corto circuito che utilizzano deve valutare i propri operandi secondo quando restituisce il primo `Nothing`.  
  
## <a name="propagation"></a>Propagazione  
 Se uno o entrambi gli operandi di un'operazione tipo aritmetico, confronto, MAIUSC oppure ammette valori null, il risultato dell'operazione è nullable. Se entrambi gli operandi hanno valori che non sono `Nothing`, l'operazione viene eseguita sui valori sottostanti degli operandi, come se non fossero un tipo nullable. Nell'esempio seguente, le variabili `compare1` e `sum1` sono tipizzate in modo implicito. Se si posiziona il puntatore del mouse su di essi, si noterà che il compilatore deduce tipi nullable per entrambe.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]  
  
 Se uno o entrambi gli operandi hanno un valore di `Nothing`, il risultato sarà `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]  
  
## <a name="using-nullable-types-with-data"></a>Utilizzo dei tipi Nullable con dati  
 Un database è una delle posizioni più importanti per utilizzare i tipi nullable. Non tutti gli oggetti di database attualmente supportano i tipi nullable, mentre gli adattatori di tabella generati dalla finestra di progettazione. Vedere "Supporto dell'oggetto TableAdapter per i tipi Nullable" in [panoramica degli oggetti TableAdapter](/visualstudio/data-tools/tableadapter-overview).
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.InvalidOperationException>  
 <xref:System.Nullable%601.HasValue%2A>  
 [Uso dei tipi nullable](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Panoramica degli oggetti TableAdapter](/visualstudio/data-tools/tableadapter-overview)  
 [Operatore If](../../../../visual-basic/language-reference/operators/if-operator.md)  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [Operatore IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)
