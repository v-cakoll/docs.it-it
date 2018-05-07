---
title: 'Procedura: convertire stringhe in matrici di byte in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: da4a47b955b91f4bb39ecd7832da30d76e75d553
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>Procedura: convertire stringhe in matrici di byte in Visual Basic
In questo argomento viene illustrato come convertire una stringa in una matrice di byte.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il <xref:System.Text.Encoding.GetBytes%2A> metodo la <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> classe per convertire una stringa in una matrice di byte di codifica.  
  
 [!code-vb[VbVbalrStrings#74](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-strings-into-an-array-of-bytes_1.vb)]  
  
 È possibile scegliere tra diverse opzioni di codifica per convertire una stringa in una matrice di byte:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ottiene una codifica per i caratteri ASCII (7 bit) set.  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 che usa l'ordine dei byte big-endian.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ottiene una codifica per la tabella codici ANSI corrente del sistema.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 che usa l'ordine dei byte little-endian.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-32 che usa l'ordine dei byte little-endian.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-8.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Text.Encoding?displayProperty=nameWithType>  
 <xref:System.Text.Encoding.GetBytes%2A>  
 [Procedura: convertire una matrice di byte in una stringa in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
