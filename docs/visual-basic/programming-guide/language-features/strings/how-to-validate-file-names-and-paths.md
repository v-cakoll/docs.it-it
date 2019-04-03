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
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835804"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="ca703-102">Procedura: Convalidare i nomi di File e percorsi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ca703-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="ca703-103">Questo esempio viene restituito un `Boolean` valore che indica se una stringa rappresenta un nome file o percorso.</span><span class="sxs-lookup"><span data-stu-id="ca703-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="ca703-104">I controlli di convalida se il nome contiene caratteri non consentiti dal file system.</span><span class="sxs-lookup"><span data-stu-id="ca703-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca703-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca703-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="ca703-106">In questo esempio non verifica se il nome è posizionato in modo non corretto due punti o le directory con alcun nome, o se la lunghezza del nome supera la lunghezza massima definita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="ca703-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="ca703-107">Inoltre non controlla se l'applicazione è autorizzata ad accedere alla risorsa del file system con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="ca703-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca703-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca703-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="ca703-109">Convalida delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ca703-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
