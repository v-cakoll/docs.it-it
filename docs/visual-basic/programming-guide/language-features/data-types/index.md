---
title: Tipi di dati
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
ms.openlocfilehash: 928d7fb6a40873641ae3e91e057c272b946a0091
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393715"
---
# <a name="data-types-in-visual-basic"></a>Tipi di dati in Visual Basic
Il *tipo di dati* di un elemento di programmazione indica la tipologia di dati che può contenere e la modalità di archiviazione di tali dati. I tipi di dati si applicano a tutti i valori che possono essere archiviati nella memoria del computer o partecipano alla valutazione di un'espressione. Ogni variabile, valore letterale, costante, enumerazione, proprietà, parametro di routine, argomento di routine e valore restituito di routine ha un tipo di dati.  
  
## <a name="declared-data-types"></a>Tipi di dati dichiarati  
 Un elemento di programmazione viene definito con un'istruzione di dichiarazione e il relativo tipo di dati viene specificato con la clausola `As`. La tabella seguente mostra le istruzioni usate per dichiarare i vari elementi.  
  
|Elemento di programmazione|Dichiarazione del tipo di dati|  
|-------------------------|---------------------------|  
|Variabile|In un'[istruzione Dim](../../../language-reference/statements/dim-statement.md)<br /><br /> `Dim`   `amount As Double`<br /><br /> `Static`   `yourName As String`<br /><br /> `Public`   `billsPaid As Decimal = 0`|  
|Literal (Valore letterale)|Con un carattere di tipo letterale. Vedere "Caratteri di tipo letterale" in [Caratteri tipo](type-characters.md)<br /><br /> `Dim searchChar As Char = "."`  `C`|  
|Costante|In un'[istruzione Const](../../../language-reference/statements/const-statement.md)<br /><br /> `Const`   `modulus As Single = 4.17825F`|  
|Enumerazione|In un'[istruzione Enum](../../../language-reference/statements/enum-statement.md)<br /><br /> `Public`   `Enum`   `colors`|  
|Proprietà|In un'[istruzione Property](../../../language-reference/statements/property-statement.md)<br /><br /> `Property`   `region() As String`|  
|Parametro di routine|In un'[istruzione Sub](../../../language-reference/statements/sub-statement.md), un'[istruzione Function](../../../language-reference/statements/function-statement.md) o un'[istruzione Operator](../../../language-reference/statements/operator-statement.md)<br /><br /> `Sub addSale(ByVal`   `amount`   `As Double)`|  
|Argomento di routine|Nel codice chiamante; ogni argomento è un elemento di programmazione già dichiarato o un'espressione che contiene elementi dichiarati<br /><br /> `subString = Left(`  `inputString`  `,`   `5`  `)`|  
|Valore restituito di routine|In un'[istruzione Function](../../../language-reference/statements/function-statement.md) o un'[istruzione Operator](../../../language-reference/statements/operator-statement.md)<br /><br /> `Function convert(ByVal b As Byte)`   `As String`|  
  
 Per un elenco dei tipi di dati di Visual Basic, vedere [Tipi di dati](../../../language-reference/data-types/index.md).  
  
## <a name="see-also"></a>Vedere anche

- [Caratteri tipo](type-characters.md)
- [Tipi di dati elementari](elementary-data-types.md)
- [Tipi di dati compositi](composite-data-types.md)
- [Generic Types in Visual Basic](generic-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Conversioni di tipi in Visual Basic](type-conversions.md)
- [Strutture](structures.md)
- [Tuple](tuples.md)
- [Risoluzione dei problemi relativi ai tipi di dati](troubleshooting-data-types.md)
- [Tipi di dati](../../../language-reference/data-types/index.md)
- [Uso efficiente dei tipi di dati](efficient-use-of-data-types.md)
