---
title: 'Procedura: Convalidare nomi e percorsi di file'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: 3b4695dfbcaf05c73bd53af5be7a49d081eb8e47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410580"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Procedura: convalidare nomi e percorsi di file in Visual Basic
Questo esempio restituisce un `Boolean` valore che indica se una stringa rappresenta un nome file o un percorso. La convalida controlla se il nome contiene caratteri non consentiti dal file system.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 In questo esempio non viene verificato se il nome ha inserito in modo errato i due punti oppure le directory senza nome oppure se la lunghezza del nome supera la lunghezza massima definita dal sistema. Inoltre, non controlla se l'applicazione è autorizzata ad accedere alla risorsa del file System con il nome specificato.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Convalida delle stringhe in Visual Basic](validating-strings.md)
