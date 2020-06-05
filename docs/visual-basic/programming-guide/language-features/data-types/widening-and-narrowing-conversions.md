---
title: Widening and Narrowing Conversions
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
ms.openlocfilehash: 177ff6c6fe15c57563d2f62ed8927f9ee975be48
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393000"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Conversioni di ampliamento e restrizione (Visual Basic)
Una considerazione importante per la conversione di un tipo è la possibilità che il risultato della conversione sia compreso nell'intervallo del tipo di dati di destinazione.  
  
 Una *conversione* verso un tipo di dati più ampio modifica un valore in un tipo di dati che può consentire qualsiasi valore possibile dei dati originali.  Le conversioni verso un tipo di dati più ampio conservano il valore di origine ma possono modificarne la rappresentazione. Questo errore si verifica se si esegue la conversione da un tipo integrale a `Decimal` o da `Char` a `String` .  
  
 Una *conversione verso un tipo di dati più piccolo* imposta un valore su un tipo di dati che potrebbe non contenere alcuni dei possibili valori. Ad esempio, un valore frazionario viene arrotondato quando viene convertito in un tipo integrale e un tipo numerico convertito in `Boolean` viene ridotto a `True` o `False` .  
  
## <a name="widening-conversions"></a>conversioni verso un tipo di dati più grande  
 Nella tabella seguente vengono illustrate le conversioni standard verso un tipo di ampliamento.  
  
|Tipo di dati|Viene ampliato ai tipi di dati <sup>1</sup>|  
|---|---|  
|[SByte](../../../language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Breve](../../../language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Intero](../../../language-reference/data-types/integer-data-type.md)|`Integer`, `Long` , `Decimal` , `Single` , `Double` <sup>2</sup>|  
|[UInteger](../../../language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long` , `ULong` , `Decimal` , `Single` , `Double` <sup>2</sup>|  
|[Long](../../../language-reference/data-types/long-data-type.md)|`Long`, `Decimal` , `Single` , `Double` <sup>2</sup>|  
|[ULong](../../../language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal` , `Single` , `Double` <sup>2</sup>|  
|[Decimale](../../../language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single` , `Double` <sup>2</sup>|  
|[Single](../../../language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../language-reference/data-types/double-data-type.md)|`Double`|  
|Qualsiasi tipo enumerato ([enum](../../../language-reference/statements/enum-statement.md))|Il tipo integrale sottostante e qualsiasi tipo in cui viene ampliato il tipo sottostante.|  
|[Char](../../../language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|Matrice `Char`|`Char`matrice`String`|  
|Qualsiasi tipo|[Object](../../../language-reference/data-types/object-data-type.md)|  
|Qualsiasi tipo derivato|Qualsiasi tipo di base da cui è derivato <sup>3</sup>.|  
|Qualsiasi tipo|Qualsiasi interfaccia implementata.|  
|[Nothing](../../../language-reference/nothing.md)|Qualsiasi tipo di dati o tipo di oggetto.|  
  
 <sup>1</sup> per definizione, ogni tipo di dati viene ampliato a se stesso.  
  
 <sup>2</sup> le conversioni da `Integer` , `UInteger` , `Long` , `ULong` o `Decimal` a o potrebbero comportare `Single` `Double` la perdita di precisione, ma mai in perdita di grandezza. In questo senso, non subiscono perdite di informazioni.  
  
 <sup>3</sup> potrebbe sembrare sorprendente che una conversione da un tipo derivato a uno dei relativi tipi di base sia più ampia. La giustificazione è che il tipo derivato contiene tutti i membri del tipo di base, quindi è qualificato come un'istanza del tipo di base. Nella direzione opposta, il tipo di base non contiene i nuovi membri definiti dal tipo derivato.  
  
 Le conversioni verso un tipo di dati più ampio hanno sempre esito positivo in fase di esecuzione e non subiscono mai È sempre possibile eseguirli in modo implicito, se l' [istruzione Option Strict](../../../language-reference/statements/option-strict-statement.md) imposta l'opzione di controllo del tipo su `On` o su `Off` .  
  
## <a name="narrowing-conversions"></a>conversioni verso un tipo di dati più piccolo  
 Di seguito sono riportate le conversioni standard più strette:  
  
- Direzioni inverse delle conversioni verso un tipo di inverso più ampio nella tabella precedente, ad eccezione del fatto che ogni tipo viene ampliato a se stesso.  
  
- Conversioni in entrambe le direzioni tra il tipo [booleano](../../../language-reference/data-types/boolean-data-type.md) e qualsiasi tipo numerico  
  
- Conversioni da qualsiasi tipo numerico a qualsiasi tipo enumerato ( `Enum` )  
  
- Conversioni in entrambe le direzioni tra [stringa](../../../language-reference/data-types/string-data-type.md) e qualsiasi tipo numerico, `Boolean` o [Data](../../../language-reference/data-types/date-data-type.md)  
  
- Conversioni da un tipo di dati o da un tipo di oggetto a un tipo derivato da esso  
  
 Le conversioni verso un tipo di dati più piccolo non vengono sempre eseguite in fase di esecuzione e possono avere esito negativo o causare una perdita di dati. Si verifica un errore se il tipo di dati di destinazione non è in grado di ricevere il valore da convertire. Una conversione numerica, ad esempio, può causare un overflow. Il compilatore non consente di eseguire in modo implicito le conversioni verso un tipo di caratteri più piccolo, a meno che l' [istruzione Option Strict](../../../language-reference/statements/option-strict-statement.md) non imposti l'opzione di controllo del tipo su `Off` .  
  
> [!NOTE]
> L'errore di conversione verso un tipo di ristringimento viene eliminato per le conversioni dagli elementi di una `For Each…Next` raccolta alla variabile di controllo del ciclo. Per ulteriori informazioni ed esempi, vedere la sezione relativa alle conversioni verso un tipo di dati più piccolo in [per ciascuna... Istruzione successiva](../../../language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Quando usare le conversioni verso un tipo di caratteri più piccolo  
 Si utilizza una conversione verso un tipo di dati più piccolo quando si sa che il valore di origine può essere convertito nel tipo di dati di destinazione senza errori o perdita di dati. Se, ad esempio, si dispone di un oggetto `String` che si conosce contiene "true" o "false", è possibile utilizzare la `CBool` parola chiave per convertirlo in `Boolean` .  
  
## <a name="exceptions-during-conversion"></a>Eccezioni durante la conversione  
 Poiché le conversioni verso un tipo di conversione più ampio hanno sempre esito positivo, non generano eccezioni. Le conversioni verso un tipo di testo più piccolo, in caso di errore, generano in genere le eccezioni seguenti:  
  
- <xref:System.InvalidCastException>: se non è stata definita alcuna conversione tra i due tipi  
  
- <xref:System.OverflowException>: (solo tipi integrali) se il valore convertito è troppo grande per il tipo di destinazione  
  
 Se una classe o una struttura definisce una [funzione CType](../../../language-reference/functions/ctype-function.md) che funge da operatore di conversione verso o da tale classe o struttura, che `CType` può generare qualsiasi eccezione ritenuta appropriata. Inoltre, è `CType` possibile che venga chiamato Visual Basic funzioni o metodi .NET Framework, che a loro volta possono generare una serie di eccezioni.  
  
## <a name="changes-during-reference-type-conversions"></a>Modifiche durante le conversioni di tipi di riferimento  
 Una conversione da un *tipo riferimento* copia solo il puntatore al valore. Il valore stesso non viene copiato né modificato in alcun modo. L'unica cosa che può cambiare è il tipo di dati della variabile che contiene il puntatore. Nell'esempio seguente il tipo di dati viene convertito dalla classe derivata alla relativa classe di base, ma l'oggetto a cui puntano entrambe le variabili è invariato.  
  
```vb  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](index.md)
- [Conversioni di tipi in Visual Basic](type-conversions.md)
- [Conversioni implicite ed esplicite](implicit-and-explicit-conversions.md)
- [Conversioni fra stringhe e altri tipi](conversions-between-strings-and-other-types.md)
- [Procedura: convertire un oggetto in un altro tipo in Visual Basic](how-to-convert-an-object-to-another-type.md)
- [Conversioni di matrice](array-conversions.md)
- [Tipi di dati](../../../language-reference/data-types/index.md)
- [CString](../../../language-reference/functions/type-conversion-functions.md)
