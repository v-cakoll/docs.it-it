---
title: 'Procedura: convertire una stringa in una matrice di caratteri'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: d2f7128f97e576d37216d3aa9736921f13f77004
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352452"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Procedura: convertire una stringa in una matrice di caratteri in Visual Basic
A volte è utile avere dati sui caratteri nella stringa e le posizioni dei caratteri all'interno della stringa, ad esempio durante l'analisi di una stringa. Questo esempio illustra come ottenere una matrice di caratteri in una stringa chiamando il metodo <xref:System.String.ToCharArray%2A> della stringa.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come suddividere una stringa in una matrice di `Char` e come suddividere una stringa in una matrice di `String` dei caratteri di testo Unicode. Il motivo di questa distinzione è che i caratteri di testo Unicode possono essere composti da due o più caratteri di `Char` (ad esempio una coppia di surrogati o una sequenza di caratteri di combinazione). Per ulteriori informazioni, vedere <xref:System.Globalization.TextElementEnumerator> e [lo standard Unicode](https://www.unicode.org/standard/standard.html).  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a>Esempio  
 È più difficile suddividere una stringa nei caratteri di testo Unicode, ma questa operazione è necessaria se sono necessarie informazioni sulla rappresentazione visiva di una stringa. In questo esempio viene usato il metodo <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> per ottenere informazioni sui caratteri di testo Unicode che costituiscono una stringa.  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [Procedura: Accedere ai caratteri delle stringhe](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [Conversione tra stringhe e altri tipi di dati in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)
