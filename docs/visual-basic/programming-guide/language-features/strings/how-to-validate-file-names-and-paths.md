---
title: 'Procedura: Convalidare i nomi di File e percorsi in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c8e01a0f5a3f99fdbc424d6cd7d224367c7bad08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032175"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Procedura: Convalidare i nomi di File e percorsi in Visual Basic
Questo esempio viene restituito un `Boolean` valore che indica se una stringa rappresenta un nome file o percorso. I controlli di convalida se il nome contiene caratteri non consentiti dal file system.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 In questo esempio non verifica se il nome è posizionato in modo non corretto due punti o le directory con alcun nome, o se la lunghezza del nome supera la lunghezza massima definita dal sistema. Inoltre non controlla se l'applicazione è autorizzata ad accedere alla risorsa del file system con il nome specificato.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Convalida delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
