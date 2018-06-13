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
ms.openlocfilehash: e574c20ec259953fea4b11d8f65e546373a4fe8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655419"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Conversioni di ampliamento e restrizione (Visual Basic)
Una considerazione importante con una conversione del tipo è se il risultato della conversione è compreso nell'intervallo del tipo di dati di destinazione.  
  
 Oggetto *conversione di ampliamento* modifica un valore in un tipo di dati che consente di eseguire tutti i valori possibili dei dati originali.  Conversioni di ampliamento mantenere il valore di origine, ma possono modificarne la rappresentazione. Questo errore si verifica se si converte da un tipo integrale a `Decimal`, o da `Char` a `String`.  
  
 Una *conversione verso un tipo di dati più piccolo* imposta un valore su un tipo di dati che potrebbe non contenere alcuni dei possibili valori. Ad esempio, un valore frazionario viene arrotondato quando viene convertito in un tipo integrale e un tipo numerico convertito in `Boolean` viene ridotto a `True` o `False`.  
  
## <a name="widening-conversions"></a>conversioni verso un tipo di dati più grande  
 La tabella seguente illustra le conversioni di ampliamento standard.  
  
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
|Qualsiasi tipo enumerato ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))|Il tipo integrale sottostante e qualsiasi tipo a cui viene ampliato al tipo sottostante.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|Matrice `Char`|`Char` matrice, `String`|  
|Qualsiasi tipo|[Oggetto](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Qualsiasi tipo derivato|Qualsiasi tipo da cui deriva di base <sup>3</sup>.|  
|Qualsiasi tipo|Qualsiasi interfaccia implementata.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Qualsiasi tipo di dati o un tipo di oggetto.|  
  
 <sup>1</sup> per definizione, ogni tipo di dati viene ampliato a se stessa.  
  
 <sup>2</sup> le conversioni dai `Integer`, `UInteger`, `Long`, `ULong`, o `Decimal` a `Single` o `Double` possono comportare una perdita di precisione, ma mai in ordine di grandezza. In questo senso non comportano la perdita di informazioni.  
  
 <sup>3</sup> potrebbe sembrare sorprendente che una conversione da un tipo derivato a uno dei tipi di base è una conversione di ampliamento. La giustificazione è che il tipo derivato contiene tutti i membri del tipo di base, pertanto viene qualificato come un'istanza del tipo di base. Nella direzione opposta, il tipo di base non contiene tutti i nuovi membri definiti dal tipo derivato.  
  
 Le conversioni di ampliamento sempre esito positivo in fase di esecuzione e non comportano perdita di dati. È sempre possibile eseguirle in modo implicito, se il [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) imposta il tipo di controllo passa a `On` o `Off`.  
  
## <a name="narrowing-conversions"></a>conversioni verso un tipo di dati più piccolo  
 Di seguito sono elencate le conversioni di narrowing standard:  
  
-   Le direzioni inverse delle conversioni di ampliamento nel passaggio precedente tabella (ad eccezione del fatto che ogni tipo viene ampliato al suo interno)  
  
-   Le conversioni in entrambe le direzioni tra [booleano](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) e qualsiasi tipo numerico  
  
-   Conversioni da qualsiasi tipo numerico a qualsiasi tipo enumerato (`Enum`)  
  
-   Le conversioni in entrambe le direzioni tra [stringa](../../../../visual-basic/language-reference/data-types/string-data-type.md) e qualsiasi tipo numerico `Boolean`, o [Data](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   Le conversioni da un tipo di dati o un oggetto di tipo a un tipo derivato da esso  
  
 Conversioni di restrizione non sempre esito positivo in fase di esecuzione e può non riuscire o comportare la perdita di dati. Si verifica un errore se il tipo di dati di destinazione non può ricevere il valore da convertire. Ad esempio, una conversione numerica può causare un overflow. Il compilatore non consente di eseguire conversioni di restrizione in modo implicito, a meno che il [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) imposta il tipo di controllo passa a `Off`.  
  
> [!NOTE]
>  L'errore di conversione di restrizione viene eliminato per le conversioni dagli elementi in un `For Each…Next` insieme alla variabile di controllo del ciclo. Per ulteriori informazioni ed esempi, vedere la sezione "Conversioni di restrizione" [For Each... Istruzione successiva](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Quando utilizzare le conversioni di restrizione  
 Utilizzare una conversione di narrowing quando si conosce che il valore di origine può essere convertito nel tipo di dati di destinazione senza perdita di dati o di errore. Ad esempio, se dispone di un `String` di conoscere contenga "True" o "False", è possibile utilizzare il `CBool` (parola chiave) per convertirlo in `Boolean`.  
  
## <a name="exceptions-during-conversion"></a>Eccezioni durante la conversione  
 Poiché le conversioni di ampliamento sempre esito positivo, non generano eccezioni. In genere, le conversioni di restrizione quando hanno esito negativo, generano le eccezioni seguenti:  
  
-   <xref:System.InvalidCastException> ovvero se è definita alcuna conversione tra i due tipi  
  
-   <xref:System.OverflowException> : (solo tipi integrali) se il valore convertito è troppo grande per il tipo di destinazione  
  
 Se una classe o struttura definisce un [CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md) come un operatore di conversione da o verso tale classe o struttura, che `CType` può generare qualsiasi eccezione che considera appropriate. Inoltre, che `CType` potrebbe chiamare funzioni di Visual Basic o [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] metodi, che a sua volta è stato possibile generare una varietà di eccezioni.  
  
## <a name="changes-during-reference-type-conversions"></a>Modifiche apportate durante le conversioni di tipo riferimento  
 Una conversione da un *tipo di riferimento* copia solo il puntatore al valore. Il valore stesso non viene copiato né modificato in alcun modo. L'unico elemento che è possibile modificare è il tipo di dati della variabile contenente il puntatore del mouse. Nell'esempio seguente, il tipo di dati viene convertito dalla classe derivata alla relativa classe base, ma non viene modificato l'oggetto che entrambe le variabili a questo puntano.  
  
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
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
