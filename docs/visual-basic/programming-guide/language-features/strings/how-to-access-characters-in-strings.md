---
title: 'Procedura: Accesso caratteri delle stringhe in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 840a769b0bb322ef7b878a312437c5ec200ab074
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834491"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Procedura: Accesso caratteri delle stringhe in Visual Basic
In questo esempio viene illustrato come utilizzare il <xref:System.String.Chars%2A> proprietà a cui accedere il carattere in corrispondenza della posizione specificata in una stringa.  
  
## <a name="example"></a>Esempio  
 Talvolta è utile disporre di dati relativi ai caratteri di una stringa e le posizioni di tali caratteri all'interno della stringa. È possibile pensare a una stringa come una matrice di caratteri (`Char` istanze); è possibile recuperare un carattere specifico facendo riferimento all'indice del carattere desiderato tramite il <xref:System.String.Chars%2A> proprietà.  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 Il `index` parametro il <xref:System.String.Chars%2A> proprietà è in base zero.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Il <xref:System.String.Chars%2A> proprietà restituisce il carattere in corrispondenza della posizione specificata. Tuttavia, alcuni caratteri Unicode possono essere rappresentati da più di un carattere. Per altre informazioni su come usare i caratteri Unicode, vedere [come: Convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 Il <xref:System.String.Chars%2A> proprietà genera un' <xref:System.IndexOutOfRangeException> eccezione se il `index` parametro è maggiore o uguale alla lunghezza della stringa, o se è minore di zero  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.String.Chars%2A>
- [Procedura: Convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [Conversione tra stringhe e altri tipi di dati in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)
