---
title: Caratteri tipo
ms.date: 01/31/2018
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
ms.openlocfilehash: a48260694c1dfcbbb8f804f220fe89b1663c7319
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393078"
---
# <a name="type-characters-visual-basic"></a>Caratteri di tipo (Visual Basic)

Oltre a specificare un tipo di dati in un'istruzione di dichiarazione, è possibile forzare il tipo di dati di alcuni elementi di programmazione con un *carattere tipo*. Il carattere tipo deve seguire immediatamente l'elemento, senza alcun carattere corrispondente.

Il tipo di carattere non fa parte del nome dell'elemento. È possibile fare riferimento a un elemento definito con un carattere di tipo senza il carattere tipo.

## <a name="identifier-type-characters"></a>Caratteri di tipo identificatore

Visual Basic fornisce un set di *caratteri di tipo identificatore* che è possibile utilizzare in una dichiarazione per specificare il tipo di dati di una variabile o di una costante. Nella tabella seguente sono illustrati i caratteri di tipo identificatore disponibili con esempi di utilizzo.
  
|Carattere di tipo identificatore|Tipo di dati|Esempio|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 Nessun carattere di tipo identificatore esistente per `Boolean` i `Byte` tipi di dati,, `Char` , `Date` , `Object` , `SByte` , `Short` , `UInteger` , `ULong` o o `UShort` per qualsiasi tipo di dati composito, ad esempio matrici o strutture.

In alcuni casi, è possibile aggiungere il `$` carattere a una funzione Visual Basic, ad esempio `Left$` anziché `Left` , per ottenere un valore restituito di tipo `String` .

In tutti i casi, il carattere di tipo identificatore deve seguire immediatamente il nome dell'identificatore.

## <a name="literal-type-characters"></a>Caratteri di tipo letterale

Un valore *letterale* è una rappresentazione testuale di un particolare valore di un tipo di dati.  

### <a name="default-literal-types"></a>Tipi di valore letterale predefinito

Il formato di un valore letterale come appare nel codice determina in genere il tipo di dati. Nella tabella seguente vengono illustrati questi tipi predefiniti.  
  
|Forma testuale di valore letterale|Tipo di dati predefinito|Esempio|  
|-----------------------------|-----------------------|-------------|  
|Numeric, nessuna parte frazionaria|`Integer`|`2147483647`|  
|Numerico, nessuna parte frazionaria, troppo grande per`Integer`|`Long`|`2147483648`|  
|Numerica, parte frazionaria|`Double`|`1.2`|  
|Racchiuso tra virgolette doppie|`String`|`"A"`|  
|Racchiuso tra segni di cancelletto|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>Tipi di valori letterali forzati

Visual Basic fornisce un set di *caratteri di tipo letterale*, che è possibile usare per imporre a un valore letterale di assumere un tipo di dati diverso da quello indicato dal form. A tale scopo, aggiungere il carattere alla fine del valore letterale. Nella tabella seguente vengono illustrati i caratteri di tipo letterale disponibili con esempi di utilizzo.
  
|Carattere di tipo letterale|Tipo di dati|Esempio|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

Nessun carattere di tipo letterale esistente per i `Boolean` `Byte` tipi di dati,, `Date` , `Object` ,, o `SByte` `String` per qualsiasi tipo di dati composito, ad esempio matrici o strutture.

I valori letterali possono anche usare i caratteri di tipo identificatore ( `%` , `&` , `@` , `!` , `#` , `$` ), così come possono variabili, costanti ed espressioni. Tuttavia, i caratteri di tipo letterale ( `S` , `I` , `L` , `D` , `F` , `R` , `C` ) possono essere utilizzati solo con valori letterali.

In tutti i casi, il carattere di tipo letterale deve seguire immediatamente il valore letterale.

## <a name="hexadecimal-binary-and-octal-literals"></a>Valori letterali esadecimali, binari e ottali

Il compilatore interpreta in genere un valore letterale integer che si trova nel sistema numerico Decimal (base 10). È anche possibile definire un valore letterale integer come numero esadecimale (base 16) con il `&H` prefisso, come numero binario (base 2) con il `&B` prefisso e come numero ottale (base 8) con il `&O` prefisso. Le cifre che seguono il prefisso devono essere appropriate per il sistema di numeri. Questa operazione è illustrata nella tabella seguente.  
  
|Base numero|Prefisso|Valori numerici validi|Esempio|
|-----------------|------------|------------------------|-------------|
|Esadecimale (base 16)|`&H`|0-9 e A-F|`&HFFFF`|
|Binary (base 2)|`&B`|0-1|`&B01111100`|
|Ottale (base 8)|`&O`|0-7|`&O77`|

A partire da Visual Basic 2017, è possibile usare il carattere di sottolineatura ( `_` ) come separatore di gruppo per migliorare la leggibilità di un valore letterale integrale. Nell'esempio seguente viene usato il `_` carattere per raggruppare un valore letterale binario in gruppi a 8 bit:

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

È possibile seguire un valore letterale con prefisso con un carattere di tipo letterale. Nell'esempio riportato di seguito viene illustrata questa situazione.

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

Nell'esempio precedente, `counter` ha il valore decimale di-32768 e `flags` il valore decimale è + 32768.

A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura ( `_` ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>Vedere anche

- [Tipi di dati](index.md)
- [Tipi di dati elementari](elementary-data-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Conversioni di tipi in Visual Basic](type-conversions.md)
- [Risoluzione dei problemi relativi ai tipi di dati](troubleshooting-data-types.md)
- [Dichiarazione di variabile](../variables/variable-declaration.md)
- [Tipi di dati](../../../language-reference/data-types/index.md)
