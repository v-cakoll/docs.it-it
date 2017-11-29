---
title: 'Procedura: creare una stringa da una matrice di valori Char (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06e5c6923c26f3cb84b38475d6680523853d727d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="7356c-102">Procedura: creare una stringa da una matrice di valori Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7356c-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="7356c-103">Questo esempio crea la stringa "abcd" da singoli caratteri.</span><span class="sxs-lookup"><span data-stu-id="7356c-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7356c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7356c-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7356c-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7356c-105">Compiling the Code</span></span>  
 <span data-ttu-id="7356c-106">Questo metodo non ha presenta requisiti speciali.</span><span class="sxs-lookup"><span data-stu-id="7356c-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="7356c-107">La sintassi `"a"c`, in cui un singolo `c` segue un singolo carattere tra virgolette, viene utilizzato per creare un carattere letterale.</span><span class="sxs-lookup"><span data-stu-id="7356c-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7356c-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="7356c-108">Robust Programming</span></span>  
 <span data-ttu-id="7356c-109">Caratteri null (equivalente a `Chr(0)`) nella stringa di produrre risultati imprevisti quando si utilizza la stringa.</span><span class="sxs-lookup"><span data-stu-id="7356c-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="7356c-110">Il carattere null sarà incluso nella stringa, ma non caratteri che seguono il carattere null verranno visualizzati in alcune situazioni.</span><span class="sxs-lookup"><span data-stu-id="7356c-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7356c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7356c-111">See Also</span></span>  
 <xref:System.String>  
 [<span data-ttu-id="7356c-112">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="7356c-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="7356c-113">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7356c-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
