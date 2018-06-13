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
ms.openlocfilehash: 7b1c7ae2a0126bf7cd487df4e9a7364c98e1c695
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603019"
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
 Qualsiasi espressione valida in un `As` clausola in un `Dim` istruzione, vale a dire il nome di qualsiasi tipo di dati, oggetto, struttura, classe o interfaccia.  
  
## <a name="remarks"></a>Note  
  
> [!TIP]
>  È inoltre possibile utilizzare le funzioni seguenti per eseguire una conversione del tipo:  
>   
>  -   Digitare ad esempio le funzioni di conversione `CByte`, `CDbl`, e `CInt` che eseguono una conversione in un tipo di dati specifico. Per ulteriori informazioni, vedere [funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
> -   [Operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) oppure [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md). Questi operatori richiedono che un tipo di ereditare da o implementare l'altro tipo. Possono fornire prestazioni migliori rispetto a `CType` durante la conversione da e verso il `Object` tipo di dati.  
  
 `CType` viene compilata inline, il che significa che il codice di conversione fa parte del codice che valuta l'espressione. In alcuni casi, il codice viene eseguito più velocemente poiché nessuna procedure vengono chiamata per eseguire la conversione.  
  
 Se è definita alcuna conversione da `expression` a `typename` (ad esempio, da `Integer` a `Date`), Visual Basic viene visualizzato un messaggio di errore in fase di compilazione.  
  
 Se una conversione non riesce in fase di esecuzione, viene generata l'eccezione appropriata. Se una conversione non riesce, un <xref:System.OverflowException> è il risultato più comune. Se la conversione non è definita, un <xref:System.InvalidCastException> in generata. Ad esempio, questa situazione può verificarsi se `expression` è di tipo `Object` e il relativo tipo in fase di esecuzione non viene convertito in `typename`.  
  
 Se il tipo di dati `expression` o `typename` è una classe o struttura è stato definito, è possibile definire `CType` in quella classe o struttura come operatore di conversione. In questo modo `CType` agire come un *operatore di overload*. In questo caso, è possibile controllare il comportamento delle conversioni da e dalla classe o struttura, incluse le eccezioni che possono essere generate.  
  
## <a name="overloading"></a>Overload  
 Il `CType` operatore possa essere sottoposti a overload anche in una classe o struttura definita all'esterno del codice. Se il codice viene convertito in o da una classe o una struttura, assicurarsi di comprendere il comportamento del relativo `CType` operatore. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="converting-dynamic-objects"></a>Conversione di oggetti dinamici  
 Conversioni di tipo degli oggetti dinamici vengono eseguite da conversioni dinamiche definite dall'utente che utilizzano il <xref:System.Dynamic.DynamicObject.TryConvert%2A> o <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> metodi. Se si lavora con gli oggetti dinamici, utilizzare il <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> metodo per convertire l'oggetto dinamico.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `CType` funzione per convertire un'espressione per il `Single` tipo di dati.  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 Per ulteriori esempi, vedere [conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.OverflowException>  
 <xref:System.InvalidCastException>  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Funzioni di conversione](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Conversione di tipi in .NET Framework](../../../standard/base-types/type-conversion.md)
