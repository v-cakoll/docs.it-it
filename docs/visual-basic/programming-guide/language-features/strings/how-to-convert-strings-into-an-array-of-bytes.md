---
title: 'Procedura: Conversione di stringhe in una matrice di byte in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: 83efc9e6b4d4433d5416f2f8b2612c76581586e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648482"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>Procedura: Conversione di stringhe in una matrice di byte in Visual Basic
In questo argomento viene illustrato come convertire una stringa in una matrice di byte.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Text.Encoding.GetBytes%2A> metodo del <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> classe per convertire una stringa in una matrice di byte di codifica.  
  
 [!code-vb[VbVbalrStrings#74](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-strings-into-an-array-of-bytes_1.vb)]  
  
 È possibile scegliere tra diverse opzioni di codifica per convertire una stringa in una matrice di byte:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ottiene una codifica per il set di caratteri ASCII (7 bit).  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 nell'ordine dei byte big-endian.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ottiene una codifica per la tabella codici ANSI corrente del sistema.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 nell'ordine dei byte little-endian.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-32 mediante l'ordine dei byte little-endian.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-8.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [Procedura: Convertire una matrice di byte in una stringa in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
