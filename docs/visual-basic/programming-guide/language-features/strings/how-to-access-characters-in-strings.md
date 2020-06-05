---
title: 'Procedura: accedere ai caratteri delle stringhe'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: fa5920cfd25f61f6e6c7d5438ef7c0e38a48fa1e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401953"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Procedura: accedere ai caratteri delle stringhe in Visual Basic
Questo esempio illustra come usare la <xref:System.String.Chars%2A> proprietà per accedere al carattere in corrispondenza della posizione specificata in una stringa.  
  
## <a name="example"></a>Esempio  
 A volte è utile avere dati sui caratteri nella stringa e le posizioni dei caratteri all'interno della stringa. È possibile considerare una stringa come una matrice di caratteri ( `Char` istanze); è possibile recuperare un particolare carattere facendo riferimento all'indice di tale carattere tramite la <xref:System.String.Chars%2A> Proprietà.  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 Il `index` parametro della <xref:System.String.Chars%2A> proprietà è in base zero.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 La <xref:System.String.Chars%2A> proprietà restituisce il carattere in corrispondenza della posizione specificata. Tuttavia, alcuni caratteri Unicode possono essere rappresentati da più di un carattere. Per altre informazioni su come usare i caratteri Unicode, vedere [procedura: convertire una stringa in una matrice di caratteri](how-to-convert-a-string-to-an-array-of-characters.md).  
  
 La <xref:System.String.Chars%2A> proprietà genera un' <xref:System.IndexOutOfRangeException> eccezione se il `index` parametro è maggiore o uguale alla lunghezza della stringa o se è minore di zero.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.String.Chars%2A>
- [Procedura: convertire una stringa in una matrice di caratteri](how-to-convert-a-string-to-an-array-of-characters.md)
- [Conversione tra stringhe e altri tipi di dati in Visual Basic](converting-between-strings-and-other-data-types.md)
- [Stringhe](index.md)
