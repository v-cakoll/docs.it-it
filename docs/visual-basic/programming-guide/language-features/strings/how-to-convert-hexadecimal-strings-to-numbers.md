---
title: 'Procedura: Convertire stringhe esadecimali in numeri (Visual Basic)'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: ddb7b39f7a47234c003ca16e1d7ea013e113c108
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773688"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Procedura: Convertire stringhe esadecimali in numeri (Visual Basic)

In questo esempio converte una stringa esadecimale in un numero intero usando la <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> (metodo).

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Per convertire una stringa esadecimale in un numero

- Usare il <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo per convertire il numero espresso in base 16 per un numero intero.

  Il primo argomento del <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo è la stringa da convertire. Il secondo argomento viene descritto il numero viene espresso in; base esadecimale è base 16.

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- Si noti che la stringa esadecimale presenta le restrizioni seguenti:

  - Non può includere il `&h` prefisso.
  - Non può includere il `_` separatore di cifre.

  Se il prefisso o un separatore di cifra è presente, la chiamata per il <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo genera un <xref:System.FormatException>.

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
