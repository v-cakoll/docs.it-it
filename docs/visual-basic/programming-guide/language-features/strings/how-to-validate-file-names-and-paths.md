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
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="4c19a-102">Procedura: convalidare nomi e percorsi di file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c19a-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="4c19a-103">Questo esempio restituisce un `Boolean` valore che indica se una stringa rappresenta un nome file o un percorso.</span><span class="sxs-lookup"><span data-stu-id="4c19a-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="4c19a-104">La convalida controlla se il nome contiene caratteri non consentiti dal file system.</span><span class="sxs-lookup"><span data-stu-id="4c19a-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c19a-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c19a-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="4c19a-106">In questo esempio non viene verificato se il nome ha inserito in modo errato i due punti oppure le directory senza nome oppure se la lunghezza del nome supera la lunghezza massima definita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="4c19a-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="4c19a-107">Inoltre, non controlla se l'applicazione è autorizzata ad accedere alla risorsa del file System con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="4c19a-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c19a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c19a-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="4c19a-109">Convalida delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c19a-109">Validating Strings in Visual Basic</span></span>](validating-strings.md)
