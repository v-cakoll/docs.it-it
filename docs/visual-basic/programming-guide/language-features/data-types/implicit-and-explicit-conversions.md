---
title: Conversioni implicite ed esplicite (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: 4bcf2d76a2983294f244b72f286842a92fb5e64e
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512862"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a>Conversioni implicite ed esplicite (Visual Basic)

Una *conversione implicita* non richiede alcuna sintassi speciale nel codice sorgente. Nell'esempio seguente Visual Basic converte in modo implicito il valore di `k` in un valore a virgola mobile a precisione singola prima di assegnarlo `q`a.

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

Una *conversione esplicita* usa una parola chiave di conversione del tipo. Visual Basic fornisce diverse parole chiave, che assegnano un'espressione tra parentesi al tipo di dati desiderato. Queste parole chiave agiscono come funzioni, ma il compilatore genera il codice inline, quindi l'esecuzione è leggermente più veloce rispetto a una chiamata di funzione.

Nell'estensione seguente dell'esempio precedente, la `CInt` parola chiave converte il valore di `q` di nuovo in un intero prima di assegnarlo a `k`.

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a>Parole chiave di conversione

Nella tabella seguente vengono illustrate le parole chiave di conversione disponibili.

|Parola chiave di conversione del tipo|Converte un'espressione in un tipo di dati|Tipi di dati consentiti di espressione da convertire|
|---|---|---|
|`CBool`|[Tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `String`,`Object`|
|`CByte`|[Tipo di dati Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Qualsiasi tipo numerico (inclusi `SByte` i tipi enumerati e) `Boolean` `String`,,,`Object`|
|`CChar`|[Tipo di dati Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|
|`CDate`|[Tipo di dati Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|
|`CDbl`|[Tipo di dati Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `Boolean` `String`,,`Object`|
|`CDec`|[Tipo di dati Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `Boolean` `String`,,`Object`|
|`CInt`|[Tipo di dati Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `Boolean` `String`,,`Object`|
|`CLng`|[Tipo di dati Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `Boolean` `String`,,`Object`|
|`CObj`|[Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Qualsiasi tipo|
|`CSByte`|[Tipo di dati SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` i tipi enumerati e) `Boolean` `String`,,,`Object`|
|`CShort`|[Tipo di dati Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `Boolean` `String`,,`Object`|
|`CSng`|[Tipo di dati Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `Boolean` `String`,,`Object`|
|`CStr`|[Tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `Boolean` `Char`,, `Char` matrice, `Date`,`Object`|
|`CType`|Tipo specificato dopo la virgola`,`()|Quando si esegue la conversione in un *tipo di dati Elementary* (inclusa una matrice di un tipo elementare), gli stessi tipi consentiti per la parola chiave di conversione corrispondente<br /><br /> Quando si esegue la conversione in un *tipo di dati composito*, le interfacce implementate e le classi da cui eredita<br /><br /> Quando si esegue la conversione in una classe o struttura in cui è stato `CType`sottoposto a overload, tale classe o struttura|
|`CUInt`|[Tipo di dati UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `Boolean` `String`,,`Object`|
|`CULng`|[Tipo di dati ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `Boolean` `String`,,`Object`|
|`CUShort`|[Tipo di dati UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Qualsiasi tipo numerico (inclusi `Byte` `SByte`i tipi enumerati, e), `Boolean` `String`,,`Object`|

## <a name="the-ctype-function"></a>Funzione CType

La [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) opera su due argomenti. Il primo è l'espressione da convertire e la seconda è il tipo di dati di destinazione o la classe di oggetti. Si noti che il primo argomento deve essere un'espressione, non un tipo.

`CType`è una *funzione inline*, ovvero il codice compilato esegue la conversione, spesso senza generare una chiamata di funzione. Ciò migliora le prestazioni.

Per un confronto di `CType` con le altre parole chiave di conversione dei tipi, vedere [Operatore DirectCast](../../../../visual-basic/language-reference/operators/directcast-operator.md) e [operatore TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md).

### <a name="elementary-types"></a>Tipi elementari

L'esempio seguente illustra l'uso di `CType`.

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a>Tipi compositi

È possibile usare `CType` per convertire i valori in tipi di dati compositi e in tipi elementari. È anche possibile usarlo per forzare una classe di oggetti nel tipo di una delle relative interfacce, come nell'esempio seguente.

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a>Tipi di matrice

`CType`può anche convertire i tipi di dati della matrice, come nell'esempio seguente.

```vb
Dim v() As classV
Dim obArray() As Object
' Assume some object array has been assigned to obArray.
' Check for run-time type compatibility.
If TypeOf obArray Is classV()
    ' obArray can be converted to classV.
    v = CType(obArray, classV())
End If
```

Per ulteriori informazioni e un esempio, vedere [conversioni di matrici](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).

### <a name="types-defining-ctype"></a>Tipi che definiscono CType

È possibile definire `CType` in una classe o una struttura definita. In questo modo è possibile convertire i valori da e verso il tipo della classe o della struttura. Per ulteriori informazioni e un esempio, vedere [procedura: Definire un operatore](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)di conversione.

> [!NOTE]
> I valori utilizzati con una parola chiave di conversione devono essere validi per il tipo di dati di destinazione oppure si verifica un errore. Se, ad esempio, si tenta di convertire `Long` un oggetto `Integer`in un oggetto `Long` , il valore di deve essere compreso nell'intervallo valido `Integer` per il tipo di dati.

> [!CAUTION]
> La `CType` specifica di per la conversione da un tipo di classe a un altro non riesce in fase di esecuzione se il tipo di origine non deriva dal tipo di destinazione. Tale errore genera un' <xref:System.InvalidCastException> eccezione.

Tuttavia, se uno dei tipi è una struttura o una classe definita e se è stato definito `CType` su tale struttura o classe, una conversione può avere esito positivo se soddisfa i requisiti `CType`di. Vedere [Procedura: Definire un operatore](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)di conversione.

L'esecuzione di una conversione esplicita è nota anche come *cast* di un'espressione a un tipo di dati o a una classe di oggetti specificati.

## <a name="see-also"></a>Vedere anche

- [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversioni fra stringhe e altri tipi](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Procedura: Converte un oggetto in un altro tipo in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
