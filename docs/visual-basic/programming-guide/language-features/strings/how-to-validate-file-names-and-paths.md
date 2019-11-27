---
title: 'Procedura: convalidare i nomi e i percorsi dei file'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: cc4d275d469860aa19c45ca0fe0401b709b42d82
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344357"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Procedura: convalidare nomi e percorsi di file in Visual Basic
In questo esempio viene restituito un valore `Boolean` che indica se una stringa rappresenta un percorso o un nome di file. La convalida controlla se il nome contiene caratteri non consentiti dal file system.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 In questo esempio non viene verificato se il nome ha inserito in modo errato i due punti oppure le directory senza nome oppure se la lunghezza del nome supera la lunghezza massima definita dal sistema. Inoltre, non controlla se l'applicazione è autorizzata ad accedere alla risorsa del file System con il nome specificato.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Convalida delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
