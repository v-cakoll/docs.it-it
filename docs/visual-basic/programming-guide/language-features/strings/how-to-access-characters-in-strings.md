---
title: 'Procedura: accedere ai caratteri delle stringhe in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54d604fc08dd97e0e31f9bcec148431374e8ef8f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Procedura: accedere ai caratteri delle stringhe in Visual Basic
In questo esempio viene illustrato come utilizzare il <xref:System.String.Chars%2A> proprietà per accedere al carattere nella posizione specificata in una stringa.  
  
## <a name="example"></a>Esempio  
 Talvolta è utile disporre di dati relativi ai caratteri di una stringa e le posizioni dei caratteri all'interno della stringa. È possibile considerare una stringa come matrice di caratteri (`Char` istanze); è possibile recuperare un particolare carattere facendo riferimento all'indice di tale carattere mediante il <xref:System.String.Chars%2A> proprietà.  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 Il `index` parametro il <xref:System.String.Chars%2A> proprietà è in base zero.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Il <xref:System.String.Chars%2A> proprietà restituisce il carattere in corrispondenza della posizione specificata. Tuttavia, alcuni caratteri Unicode possono essere rappresentati da più di un carattere. Per ulteriori informazioni su come utilizzare i caratteri Unicode, vedere [procedura: convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 Il <xref:System.String.Chars%2A> proprietà genera un <xref:System.IndexOutOfRangeException> eccezione se il `index` parametro è maggiore o uguale alla lunghezza della stringa, o se è minore di zero  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.String.Chars%2A>  
 [Procedura: Convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [Conversione tra stringhe e altri tipi di dati in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)
