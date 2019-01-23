---
title: 'Procedura: Accesso caratteri delle stringhe in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 9833b562fc0b4115448ebefb8631f0d73eb15f6f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618922"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Procedura: Accesso caratteri delle stringhe in Visual Basic
In questo esempio viene illustrato come utilizzare il <xref:System.String.Chars%2A> proprietà a cui accedere il carattere in corrispondenza della posizione specificata in una stringa.  
  
## <a name="example"></a>Esempio  
 Talvolta è utile disporre di dati relativi ai caratteri di una stringa e le posizioni di tali caratteri all'interno della stringa. È possibile pensare a una stringa come una matrice di caratteri (`Char` istanze); è possibile recuperare un carattere specifico facendo riferimento all'indice del carattere desiderato tramite il <xref:System.String.Chars%2A> proprietà.  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 Il `index` parametro il <xref:System.String.Chars%2A> proprietà è in base zero.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Il <xref:System.String.Chars%2A> proprietà restituisce il carattere in corrispondenza della posizione specificata. Tuttavia, alcuni caratteri Unicode possono essere rappresentati da più di un carattere. Per altre informazioni su come usare i caratteri Unicode, vedere [come: Convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 Il <xref:System.String.Chars%2A> proprietà genera un' <xref:System.IndexOutOfRangeException> eccezione se il `index` parametro è maggiore o uguale alla lunghezza della stringa, o se è minore di zero  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.String.Chars%2A>
- [Procedura: Convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [Conversione tra stringhe e altri tipi di dati in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)
