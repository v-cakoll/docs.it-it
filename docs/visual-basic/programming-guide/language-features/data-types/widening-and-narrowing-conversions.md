---
title: Conversioni di ampliamento e restrizione (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- widening conversions [Visual Basic]
- narrowing conversions [Visual Basic]
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions [Visual Basic], exceptions during conversion
- type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], data type
- conversions [Visual Basic], narrowing
- type conversion [Visual Basic], narrowing
- data type conversion [Visual Basic], widening
- data type conversion [Visual Basic], narrowing
- changing data types [Visual Basic]
- type conversion [Visual Basic], widening
- data type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
ms.openlocfilehash: ad49e5443016dc4fed57be4a991df9f6d6095b55
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43391394"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Conversioni di ampliamento e restrizione (Visual Basic)
Una considerazione importante con una conversione del tipo è se il risultato della conversione è compreso nell'intervallo del tipo di dati di destinazione.  
  
 Oggetto *conversione di ampliamento* imposta un valore su un tipo di dati che possa consentire di tutti i valori possibili dei dati originali.  Le conversioni di ampliamento mantenere il valore di origine, ma possono modificarne la rappresentazione. Ciò si verifica se si converte da un tipo integrale a `Decimal`, e viceversa `Char` a `String`.  
  
 Una *conversione verso un tipo di dati più piccolo* imposta un valore su un tipo di dati che potrebbe non contenere alcuni dei possibili valori. Ad esempio, un valore frazionario viene arrotondato quando viene convertito in un tipo integrale e un tipo numerico convertito in `Boolean` viene ridotto a uno `True` o `False`.  
  
## <a name="widening-conversions"></a>conversioni verso un tipo di dati più grande  
 La tabella seguente illustra lo standard di ampliamento.  
  
|Tipo di dati|Si amplia in tipi di dati <sup>1</sup>|  
|---|---|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|Qualsiasi tipo enumerato ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))|Il relativo tipo integrale sottostante e qualsiasi tipo a cui può ampliarsi nel tipo sottostante.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|Matrice `Char`|`Char` matrice, `String`|  
|Qualsiasi tipo|[Oggetto](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Qualsiasi tipo derivato|Qualsiasi tipo da cui viene derivato di base <sup>3</sup>.|  
|Qualsiasi tipo|Qualsiasi interfaccia implementata.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Qualsiasi tipo di dati o un tipo di oggetto.|  
  
 <sup>1</sup> per definizione, ogni tipo di dati viene ampliato a se stesso.  
  
 <sup>2</sup> conversioni dai `Integer`, `UInteger`, `Long`, `ULong`, oppure `Decimal` al `Single` o `Double` possono comportare una perdita di precisione, ma mai in ordine di grandezza. In questo senso non comportano la perdita di dati.  
  
 <sup>3</sup> potrebbe sembrare sorprendente che una conversione da un tipo derivato a uno dei tipi di base è una conversione di ampliamento. La giustificazione è che il tipo derivato contiene tutti i membri del tipo di base, pertanto viene qualificato come un'istanza del tipo di base. Nella direzione opposta, il tipo di base non contiene alcun membro nuovo definito dal tipo derivato.  
  
 Le conversioni di ampliamento sempre eseguite correttamente in fase di esecuzione e non comportano perdita di dati. È sempre possibile eseguirle in modo implicito, indica se il [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) imposta il tipo di opzione di controllo `On` o su `Off`.  
  
## <a name="narrowing-conversions"></a>conversioni verso un tipo di dati più piccolo  
 Le conversioni di narrowing standard includono quanto segue:  
  
-   Le istruzioni inverse delle conversioni di ampliamento nella precedente tabella (ad eccezione del fatto che ogni tipo viene ampliato a se stessa)  
  
-   Le conversioni in entrambe le direzioni tra [booleana](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) e qualsiasi tipo numerico  
  
-   Le conversioni da qualsiasi tipo numerico a qualsiasi tipo enumerato (`Enum`)  
  
-   Le conversioni in entrambe le direzioni tra [stringa](../../../../visual-basic/language-reference/data-types/string-data-type.md) e qualsiasi tipo numerico `Boolean`, o [Data](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   Le conversioni da un tipo di dati o un oggetto tipo per un tipo derivato da esso  
  
 Conversioni di Narrowing non sempre riuscire in fase di esecuzione e può avere esito negativo o comportano una perdita di dati. Si verifica un errore se il tipo di dati di destinazione non può ricevere il valore convertito. Ad esempio, una conversione numerica può comportare un overflow. Il compilatore non consente di eseguire conversioni di narrowing in modo implicito, a meno che il [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) imposta il tipo di opzione di controllo `Off`.  
  
> [!NOTE]
>  L'errore di conversione narrowing viene eliminata per le conversioni dagli elementi in un `For Each…Next` insieme alla variabile di controllo del ciclo. Per altre informazioni ed esempi, vedere la sezione "Conversioni di Narrowing" [For Each... Istruzione Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Quando usare le conversioni di restrizione  
 Si usa una conversione di narrowing quando si conosce che il valore di origine può essere convertito nel tipo di dati di destinazione senza errore o perdita di dati. Ad esempio, se si dispone di un `String` che si conosce contenente "True" o "False", è possibile usare il `CBool` parola chiave per convertirlo in `Boolean`.  
  
## <a name="exceptions-during-conversion"></a>Eccezioni durante la conversione  
 Poiché le conversioni di ampliamento sempre esito positivo, non generano eccezioni. Conversioni di Narrowing, quando non riescono, generano di solito le eccezioni seguenti:  
  
-   <xref:System.InvalidCastException> ovvero se non è stata definita alcuna conversione tra i due tipi  
  
-   <xref:System.OverflowException> : (solo tipi integrali) se il valore convertito è troppo grande per il tipo di destinazione  
  
 Se una classe o struttura definisce un [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) da usare come un operatore di conversione da o verso tale classe o struttura, che `CType` possibile generare qualsiasi eccezione considera appropriata. Inoltre, che `CType` potrebbe chiamare funzioni di Visual Basic o [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] metodi, che a sua volta è stato possibile generare un'ampia gamma di eccezioni.  
  
## <a name="changes-during-reference-type-conversions"></a>Modifiche apportate durante le conversioni di tipo riferimento  
 Una conversione da un *fanno riferimento a tipo* copia solo il puntatore al valore. Il valore stesso non viene copiato né modificato in alcun modo. L'unica cosa che è possibile modificare è il tipo di dati della variabile che contiene il puntatore. Nell'esempio seguente, il tipo di dati viene convertito dalla classe derivata a classe base, ma l'oggetto che entrambe le variabili a questo puntano rimane invariato.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Conversioni fra stringhe e altri tipi](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Procedura: convertire un oggetto in un altro tipo in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Conversioni di matrice](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)  
 [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
