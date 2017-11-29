---
title: 'Procedura: convertire una stringa in una matrice di caratteri in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59d0da52c8f78b93c76325e6242156c106deeaf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Procedura: convertire una stringa in una matrice di caratteri in Visual Basic
Talvolta è utile disporre di dati relativi ai caratteri di una stringa e le posizioni dei caratteri all'interno della stringa, ad esempio quando si analizza una stringa. Questo esempio viene illustrato come è possibile ottenere una matrice di caratteri in una stringa chiamando la stringa <xref:System.String.ToCharArray%2A> metodo.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come suddividere una stringa in un `Char` matrice e come suddividere una stringa in un `String` matrice dei relativi caratteri di testo Unicode. Il motivo di questa distinzione è che i caratteri di testo Unicode possono essere composti da due o più `Char` caratteri (ad esempio una coppia di surrogati o una combinazione sequenza di caratteri). Per ulteriori informazioni, vedere <xref:System.Globalization.TextElementEnumerator> e "Lo Standard Unicode" indirizzo http://www.unicode.org.  
  
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
