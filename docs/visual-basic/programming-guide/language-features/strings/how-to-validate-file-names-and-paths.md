---
title: 'Procedura: convalidare nomi e percorsi di file in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: ab3df335bc5bba21d386bb69b12d840990e629fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647804"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Procedura: convalidare nomi e percorsi di file in Visual Basic
Questo esempio viene restituito un `Boolean` valore che indica se una stringa rappresenta un nome file o un percorso. I controlli di convalida se il nome contiene caratteri non consentiti dal file system.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 In questo esempio non verifica se il nome è inserito in modo non corretto, due punti o directory senza nome, o se la lunghezza del nome supera la lunghezza massima definita dal sistema. Inoltre non controlla se l'applicazione dispone dell'autorizzazione per accedere alla risorsa del file system con il nome specificato.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.Path.GetInvalidPathChars%2A>  
 [Convalida delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
