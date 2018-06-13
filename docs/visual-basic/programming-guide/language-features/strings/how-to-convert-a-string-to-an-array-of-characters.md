---
title: 'Procedura: convertire una stringa in una matrice di caratteri in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: c109143601e304b1ec15a60c71d65fe6bd15aae8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648619"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Procedura: convertire una stringa in una matrice di caratteri in Visual Basic
Talvolta è utile disporre di dati relativi ai caratteri di una stringa e le posizioni dei caratteri all'interno della stringa, ad esempio quando si analizza una stringa. Questo esempio viene illustrato come è possibile ottenere una matrice di caratteri in una stringa chiamando la stringa <xref:System.String.ToCharArray%2A> metodo.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come suddividere una stringa in un `Char` matrice e come suddividere una stringa in un `String` matrice dei relativi caratteri di testo Unicode. Il motivo di questa distinzione è che i caratteri di testo Unicode possono essere composti da due o più `Char` caratteri (ad esempio una coppia di surrogati o una combinazione sequenza di caratteri). Per altre informazioni, vedere <xref:System.Globalization.TextElementEnumerator> e "Lo Standard Unicode" nella http://www.unicode.org.  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a>Esempio  
 È più difficile suddividere una stringa in relativi caratteri di testo Unicode, ma questa operazione è necessaria se sono necessarie informazioni sulla rappresentazione visiva di una stringa. Questo esempio viene utilizzato il <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> metodo per ottenere informazioni sui caratteri che costituiscono una stringa di testo Unicode.  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [Procedura: Accedere ai caratteri delle stringhe](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [Conversione tra stringhe e altri tipi di dati in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)
