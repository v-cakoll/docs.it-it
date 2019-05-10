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
ms.openlocfilehash: 786065fde9814d31ac36b56e1455d5b1685122ad
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665349"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>Procedura: Conversione di stringhe in una matrice di byte in Visual Basic
In questo argomento viene illustrato come convertire una stringa in una matrice di byte.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Text.Encoding.GetBytes%2A> metodo del <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> classe per convertire una stringa in una matrice di byte di codifica.  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 È possibile scegliere tra diverse opzioni di codifica per convertire una stringa in una matrice di byte:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ottiene una codifica per il set di caratteri ASCII (7 bit).  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 nell'ordine dei byte big-endian.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ottiene una codifica per la tabella codici ANSI corrente del sistema.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 nell'ordine dei byte little-endian.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-32 mediante l'ordine dei byte little-endian.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-7.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-8.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [Procedura: Convertire una matrice di byte in una stringa in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
