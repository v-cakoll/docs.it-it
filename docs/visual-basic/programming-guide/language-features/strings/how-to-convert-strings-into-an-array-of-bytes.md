---
title: 'Procedura: Convertire stringhe in matrici di byte'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: 3ee1d5e1e31054f23f4510c7a112d8e3473bcdd7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410606"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>Procedura: convertire stringhe in matrici di byte in Visual Basic
In questo argomento viene illustrato come convertire una stringa in una matrice di byte.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il <xref:System.Text.Encoding.GetBytes%2A> metodo della <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> classe Encoding per convertire una stringa in una matrice di byte.  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 È possibile scegliere tra diverse opzioni di codifica per convertire una stringa in una matrice di byte:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ottiene una codifica per il set di caratteri ASCII (7 bit).  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 che usa l'ordine dei byte big-endian.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ottiene una codifica per la tabella codici ANSI corrente del sistema.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 che usa l'ordine dei byte little-endian.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-32 usando l'ordine dei byte little-endian.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-7.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-8.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [Procedura: convertire una matrice di byte in una stringa in Visual Basic](how-to-convert-an-array-of-bytes-into-a-string.md)
