---
title: 'Procedura: convertire stringhe esadecimali in numeri'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: f0a97a0c212a64bfa4db4606ee526b666f07877a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347169"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Procedura: convertire stringhe esadecimali in numeri (Visual Basic)

Questo esempio converte una stringa esadecimale in un Integer usando il metodo <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>.

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Per convertire una stringa esadecimale in un numero

- Usare il metodo <xref:System.Convert.ToInt32(System.String,System.Int32)> per convertire il numero espresso in base-16 in un valore integer.

  Il primo argomento del metodo <xref:System.Convert.ToInt32(System.String,System.Int32)> è la stringa da convertire. Il secondo argomento descrive la base in cui è espresso il numero; il formato esadecimale è base 16.

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- Si noti che la stringa esadecimale presenta le restrizioni seguenti:

  - Non può includere il prefisso `&h`.
  - Non può includere il separatore di cifre `_`.

  Se è presente il prefisso o un separatore di cifre, la chiamata al metodo <xref:System.Convert.ToInt32(System.String,System.Int32)> genera un'<xref:System.FormatException>.

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
