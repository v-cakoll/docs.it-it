---
title: Numero di record non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: abd0a1467c0991a40b93e74a1d7a7889367fb8ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61977024"
---
# <a name="bad-record-number"></a><span data-ttu-id="cfc36-102">Numero di record non valido</span><span class="sxs-lookup"><span data-stu-id="cfc36-102">Bad record number</span></span>
<span data-ttu-id="cfc36-103">Il numero di record nell'istruzione `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` è minore o uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="cfc36-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cfc36-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="cfc36-104">To correct this error</span></span>  
  
1. <span data-ttu-id="cfc36-105">Controllare i calcoli usati per generare il numero di record.</span><span class="sxs-lookup"><span data-stu-id="cfc36-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="cfc36-106">Controllare l'ortografia delle variabili che contengono il numero di record o usati per calcolare i numeri di record.</span><span class="sxs-lookup"><span data-stu-id="cfc36-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="cfc36-107">Un nome di variabile contenente errori di ortografia è dichiarato in modo implicito e inizializzato su zero, a meno che non sia stato usato `Option Explicit On` nel modulo.</span><span class="sxs-lookup"><span data-stu-id="cfc36-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc36-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfc36-108">See also</span></span>

- [<span data-ttu-id="cfc36-109">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="cfc36-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
