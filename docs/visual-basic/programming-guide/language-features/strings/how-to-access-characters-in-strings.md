---
title: 'Procedura: accedere ai caratteri delle stringhe'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 44a021ed3ce1d10613cf6ab7c959c62feec6046c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352468"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Procedura: accedere ai caratteri delle stringhe in Visual Basic
Questo esempio illustra come usare la proprietà <xref:System.String.Chars%2A> per accedere al carattere in corrispondenza della posizione specificata in una stringa.  
  
## <a name="example"></a>Esempio  
 A volte è utile avere dati sui caratteri nella stringa e le posizioni dei caratteri all'interno della stringa. È possibile considerare una stringa come una matrice di caratteri (`Char` istanze); è possibile recuperare un particolare carattere facendo riferimento all'indice di tale carattere tramite la proprietà <xref:System.String.Chars%2A>.  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 Il parametro `index` della proprietà <xref:System.String.Chars%2A> è in base zero.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 La proprietà <xref:System.String.Chars%2A> restituisce il carattere in corrispondenza della posizione specificata. Tuttavia, alcuni caratteri Unicode possono essere rappresentati da più di un carattere. Per altre informazioni su come usare i caratteri Unicode, vedere [procedura: convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 La proprietà <xref:System.String.Chars%2A> genera un'eccezione <xref:System.IndexOutOfRangeException> se il parametro `index` è maggiore o uguale alla lunghezza della stringa o se è minore di zero  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.String.Chars%2A>
- [Procedura: Convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [Conversione tra stringhe e altri tipi di dati in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)
