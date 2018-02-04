---
title: Caratteri tipo (Visual Basic)
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
author: rpetrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: bdb675b9605d03829c95897382daa6d03cf1b041
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="type-characters-visual-basic"></a>Digitare i caratteri (Visual Basic)

Oltre a specificare un tipo di dati in un'istruzione di dichiarazione, è possibile forzare il tipo di dati di alcuni elementi di programmazione con un *carattere tipo*. Il tipo di carattere deve seguire immediatamente l'elemento, senza i caratteri di qualsiasi tipo.

Il tipo di carattere non è parte del nome dell'elemento. Un elemento definito con un carattere di tipo può fare riferimento senza il tipo di carattere.

## <a name="identifier-type-characters"></a>Caratteri di tipo identificatore

Visual Basic fornisce un set di *caratteri identificatori di tipo* che è possibile utilizzare in una dichiarazione per specificare il tipo di dati di una variabile o costante. Nella tabella seguente mostra i caratteri di tipo identificatore disponibile con esempi di utilizzo.
  
|Carattere di tipo identificatore|Tipo di dati|Esempio|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 Non esiste alcun carattere di tipo identificatore per il `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort` tipi di dati, o uno tipi di dati composti, ad esempio matrici o strutture.

In alcuni casi, è possibile aggiungere il `$` carattere a una funzione di Visual Basic, ad esempio `Left$` anziché `Left`, per ottenere un valore restituito di tipo `String`.

In tutti i casi, il carattere di tipo identificatore deve seguire immediatamente il nome dell'identificatore.

## <a name="literal-type-characters"></a>Caratteri di tipo effettivo

Oggetto *letterale* è una rappresentazione testuale di un particolare valore di un tipo di dati.  

### <a name="default-literal-types"></a>Tipi di valore letterale predefinito

Il modulo di un valore letterale come appare nel codice in genere determina il tipo di dati. Nella tabella seguente vengono illustrati questi tipi di valore predefinito.  
  
|Formato testuale del valore letterale|Tipo di dati predefinito|Esempio|  
|-----------------------------|-----------------------|-------------|  
|Numerico, senza parte frazionaria|`Integer`|`2147483647`|  
|Numerico, senza parte frazionaria, troppo grande per`Integer`|`Long`|`2147483648`|  
|Numerico, parte frazionaria|`Double`|`1.2`|  
|Racchiuso tra virgolette doppie|`String`|`"A"`|  
|Racchiuso tra simboli di cancelletto|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>Tipi letterali forzati

Visual Basic fornisce un set di *caratteri di tipo letterale*, indica che è possibile utilizzare per forzare un valore letterale di un tipo di dati diverso da quello assumere la forma. Questo caso aggiungendo il carattere alla fine del valore letterale. Nella tabella seguente mostra i caratteri di tipo letterale disponibili con esempi di utilizzo.
  
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

Non esiste alcun carattere di tipo di valore letterale per il `Boolean`, `Byte`, `Date`, `Object`, `SByte`, o `String` tipi di dati, o per qualsiasi tipo di dati composta, ad esempio matrici o strutture.

Valori letterali possono inoltre utilizzare i caratteri identificatori di tipo (`%`, `&`, `@`, `!`, `#`, `$`), analogamente a variabili, costanti ed espressioni. Tuttavia, caratteri di tipo letterale (`S`, `I`, `L`, `D`, `F`, `R`, `C`) può essere utilizzato solo con valori letterali.

In tutti i casi, il carattere di tipo di valore letterale deve seguire immediatamente il valore letterale.

## <a name="hexadecimal-binary-and-octal-literals"></a>Valori letterali esadecimali, binari e ottali

In genere, il compilatore interpreta un valore letterale integer per il sistema di numeri decimali (base 10). È inoltre possibile definire un valore letterale integer come un numero esadecimale (base 16) con il `&H` prefisso, come numero binario (base 2) con il `&B` prefisso e come un ottale (base 8) numero con la `&O` prefisso. Le cifre che seguono il prefisso devono essere appropriate per il sistema di numeri. Questa condizione è illustrata nella tabella seguente.  
  
|Numero di base|Prefisso|Valori di cifra valida|Esempio|
|-----------------|------------|------------------------|-------------|
|Esadecimale (base 16)|`&H`|0-9 e A-F|`&HFFFF`|
|Binario (base 2)|`0B`|0-1|`&B01111100`|
|Ottale (base 8)|`&O`|0-7|`&O77`|

A partire da Visual Basic 2017, è possibile utilizzare il carattere di sottolineatura (`_`) come separatore di gruppi per migliorare la leggibilità di un valore letterale integrale. L'esempio seguente usa il `_` carattere per raggruppare un valore letterale binario in gruppi di 8 bit:

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

È possibile seguire un valore letterale con prefisso con un carattere di tipo di valore letterale. Nell'esempio seguente viene illustrata questa operazione.

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

Nell'esempio precedente, `counter` ha il valore decimale compreso tra -32768, e `flags` ha il valore decimale 32768.

A partire da Visual Basic 15,5, è inoltre possibile utilizzare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre binarie, ottale o esadecimale. Ad esempio:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>Vedere anche

 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
