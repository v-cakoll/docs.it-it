---
title: Numero di record non valido
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be04987353498775ec7dcef50b6acc1e6b4ec149
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="bad-record-number"></a><span data-ttu-id="c6e94-102">Numero di record non valido</span><span class="sxs-lookup"><span data-stu-id="c6e94-102">Bad record number</span></span>
<span data-ttu-id="c6e94-103">Il numero di record nell'istruzione `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` è minore o uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="c6e94-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6e94-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c6e94-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="c6e94-105">Controllare i calcoli usati per generare il numero di record.</span><span class="sxs-lookup"><span data-stu-id="c6e94-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="c6e94-106">Controllare l'ortografia delle variabili che contengono il numero di record o usati per calcolare i numeri di record.</span><span class="sxs-lookup"><span data-stu-id="c6e94-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="c6e94-107">Un nome di variabile contenente errori di ortografia è dichiarato in modo implicito e inizializzato su zero, a meno che non sia stato usato `Option Explicit On` nel modulo.</span><span class="sxs-lookup"><span data-stu-id="c6e94-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e94-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6e94-108">See Also</span></span>  
 [<span data-ttu-id="c6e94-109">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="c6e94-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
