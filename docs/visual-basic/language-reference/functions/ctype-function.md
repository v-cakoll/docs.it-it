---
title: Funzione CType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 8f60edb2b5e2dba15526169ef10bc05c1f50a7f1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970012"
---
# <a name="ctype-function-visual-basic"></a>Funzione CType (Visual Basic)
Restituisce il risultato della conversione esplicita di un'espressione in un tipo di dati specificato, oggetto, struttura, classe o interfaccia.  
  
## <a name="syntax"></a>Sintassi  
  
```  
CType(expression, typename)  
```  
  
## <a name="parts"></a>Parti  
 `expression`  
 Qualsiasi espressione valida. Se il valore di `expression` non è compreso nell'intervallo consentito da `typename`, Visual Basic genera un'eccezione.  
  
 `typename`  
 Qualsiasi espressione valida in un' `As` clausola in un `Dim` istruzione, vale a dire, il nome di qualsiasi tipo di dati, oggetto, struttura, classe o interfaccia.  
  
## <a name="remarks"></a>Note  
  
> [!TIP]
>  È anche possibile usare le funzioni seguenti per eseguire una conversione del tipo:  
>   
>  -   Digitare, ad esempio funzioni di conversione `CByte`, `CDbl`, e `CInt` che eseguono una conversione in un tipo di dati specifico. Per altre informazioni, vedere [funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
> -   [Operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) oppure [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md). Questi operatori richiedono che un tipo erediti da o implementi l'altro tipo. Possono fornire prestazioni migliori rispetto a `CType` durante la conversione da e verso il `Object` tipo di dati.  
  
 `CType` viene compilata inline, il che significa che il codice di conversione fa parte del codice che valuta l'espressione. In alcuni casi, il codice viene eseguito più velocemente perché viene chiamata alcuna procedura per eseguire la conversione.  
  
 Se non è stata definita alcuna conversione da `expression` al `typename` (ad esempio, da `Integer` a `Date`), Visual Basic viene visualizzato un messaggio di errore in fase di compilazione.  
  
 Se una conversione non riesce in fase di esecuzione, viene generata l'eccezione appropriata. Se una conversione di narrowing non riesce, un <xref:System.OverflowException> è il risultato più comune. Se la conversione non è definita, un <xref:System.InvalidCastException> in generata. Ad esempio, questa situazione può verificarsi se `expression` JE typu `Object` e il relativo tipo in fase di esecuzione non viene convertito in `typename`.  
  
 Se il tipo di dati `expression` oppure `typename` è una classe o struttura sono definiti, è possibile definire `CType` in quella classe o struttura come operatore di conversione. In questo modo `CType` agire come un *operatore di overload*. In questo caso, è possibile controllare il comportamento delle conversioni da e nella classe o struttura, incluse le eccezioni che possono essere generate.  
  
## <a name="overloading"></a>Overload  
 Il `CType` operatore può anche essere sottoposti a overload in una classe o struttura definita all'esterno del codice. Se il codice esegue una conversione da o verso una classe o una struttura, assicurarsi di comprendere il comportamento del relativo `CType` operatore. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="converting-dynamic-objects"></a>Conversione di oggetti dinamici  
 Conversioni di tipi di oggetti dinamici vengono eseguite da conversioni dinamiche definite dall'utente che usano il <xref:System.Dynamic.DynamicObject.TryConvert%2A> o <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> metodi. Se si lavora con gli oggetti dinamici, utilizzare il <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> metodo per convertire l'oggetto dinamico.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `CType` funzione per convertire un'espressione di `Single` tipo di dati.  
  
 [!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]  
  
 Per altri esempi, vedere [conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Funzioni di conversione](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Conversione di tipi in .NET Framework](../../../standard/base-types/type-conversion.md)
