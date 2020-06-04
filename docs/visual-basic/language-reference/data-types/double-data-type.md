---
title: Tipo di dati Double
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 899554f427ac77ead465752c35e51ca88d045763
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415634"
---
# <a name="double-data-type-visual-basic"></a>Tipo di dati Double (Visual Basic)

Include numeri a virgola mobile a precisione doppia IEEE a 64 bit (8 byte) che variano in base al valore da-1.79769313486231570 E + 308 a-4.94065645841246544 E-324 per i valori negativi e da 4.94065645841246544 E-324 a 1.79769313486231570 E + 308 per i valori positivi. I numeri a precisione doppia archiviano un'approssimazione di un numero reale.

## <a name="remarks"></a>Commenti

Il `Double` tipo di dati fornisce le Magnitude più grandi e minime possibili per un numero.

Il valore predefinito di `Double` è 0.

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Precisione.** Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione precisa in memoria. Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l' `Mod` operatore. Per ulteriori informazioni, vedere [risoluzione dei problemi](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.

- **Zeri finali.** I tipi di dati a virgola mobile non hanno alcuna rappresentazione interna di caratteri zero finali. Ad esempio, non si distinguono tra 4,2000 e 4,2. Di conseguenza, i caratteri zero finali non vengono visualizzati quando si visualizzano o stampano valori a virgola mobile.

- **Digitare i caratteri.** Aggiungendo il carattere di tipo letterale `R` a un valore letterale, se ne determina la conversione nel tipo di dati `Double`. Se, ad esempio, un valore integer è seguito da `R` , il valore viene modificato in un oggetto `Double` .

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  Aggiungendo il carattere identificatore di tipo `#` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Double`. Nell'esempio seguente la variabile `num` è tipizzata come `Double` :

  ```vb
  Dim num# = 3
  ```

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Double?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Double?displayProperty=nameWithType>
- [Tipi di dati](index.md)
- [Tipo di dati Decimal](decimal-data-type.md)
- [Tipo di dati Single](single-data-type.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Caratteri tipo](../../programming-guide/language-features/data-types/type-characters.md)
