---
title: "Tipo &lt;typename&gt; non è conforme a CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords: BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d45da3b061dff0f82c1155daf5724033261bbdaa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="8c806-102">Tipo &lt;typename&gt; non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="8c806-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="8c806-103">Una funzione, una proprietà o una variabile viene dichiarata con un tipo di dati che non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="8c806-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="8c806-104">Per un'applicazione sia compatibile con il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](https://msdn.microsoft.com/library/12a7a7h3) (CLS), è necessario utilizzare solo tipi conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="8c806-104">For an application to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="8c806-105">I tipi di dati di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] seguenti non sono compatibili con CLS:</span><span class="sxs-lookup"><span data-stu-id="8c806-105">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="8c806-106">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="8c806-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="8c806-107">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="8c806-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="8c806-108">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="8c806-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="8c806-109">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="8c806-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="8c806-110">**ID errore:** BC40041</span><span class="sxs-lookup"><span data-stu-id="8c806-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8c806-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8c806-111">To correct this error</span></span>  
  
-   <span data-ttu-id="8c806-112">Se l'applicazione deve essere conforme a CLS, modificare il tipo di dati di questo elemento per il tipo conforme a CLS più vicino.</span><span class="sxs-lookup"><span data-stu-id="8c806-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="8c806-113">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="8c806-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="8c806-114">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="8c806-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="8c806-115">Se l'applicazione non deve essere conforme a CLS, non è necessario apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="8c806-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="8c806-116">È necessario essere consapevoli di conformità, tuttavia.</span><span class="sxs-lookup"><span data-stu-id="8c806-116">You should be aware of its noncompliance, however.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c806-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c806-117">See Also</span></span>  
 [<span data-ttu-id="8c806-118">\<PAVE su > scrittura di codice conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="8c806-118">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
