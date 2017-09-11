---
title: "Tipo di membro &quot;&lt;membername&gt;&quot; non è conforme a CLS | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40025
- vbc40025
dev_langs:
- VB
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ab4d0936603ae133bd7def4341f29d5fcdf7188b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a><span data-ttu-id="a5d4d-102">Tipo di membro '&lt;membername&gt;' non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="a5d4d-102">Type of member &#39;&lt;membername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="a5d4d-103">Il tipo di dati specificato per questo membro non è in parte il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span><span class="sxs-lookup"><span data-stu-id="a5d4d-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span> <span data-ttu-id="a5d4d-104">Non si tratta di un errore all'interno del componente, poiché il [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] e [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supporta questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] and [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] support this data type.</span></span> <span data-ttu-id="a5d4d-105">Tuttavia, un altro componente scritto in codice strettamente conforme a CLS potrebbe non supportare questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="a5d4d-106">Tale componente potrebbe non essere in grado di interagire correttamente con il componente.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="a5d4d-107">I tipi di dati di [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] seguenti non sono compatibili con CLS:</span><span class="sxs-lookup"><span data-stu-id="a5d4d-107">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="a5d4d-108">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="a5d4d-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="a5d4d-109">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="a5d4d-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="a5d4d-110">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="a5d4d-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="a5d4d-111">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="a5d4d-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="a5d4d-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-112">By default, this message is a warning.</span></span> <span data-ttu-id="a5d4d-113">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a5d4d-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a5d4d-114">**ID errore:** BC40025</span><span class="sxs-lookup"><span data-stu-id="a5d4d-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a5d4d-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a5d4d-115">To correct this error</span></span>  
  
-   <span data-ttu-id="a5d4d-116">Se il componente interagisce solo con altri [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] componenti o non si interfaccia con altri componenti, non occorre apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="a5d4d-117">Se si prevede l'interazione con un componente non scritto per il [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], potrebbe essere in grado di determinare, tramite reflection o dalla documentazione, se supporta questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="a5d4d-118">In questo caso, non occorre apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="a5d4d-119">Se si prevede l'interazione con un componente che non supporta questo tipo di dati, è necessario sostituirlo con il tipo più conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="a5d4d-120">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="a5d4d-121">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="a5d4d-122">Se si prevede l'interazione con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno un'ampiezza di dati diversa da [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5d4d-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="a5d4d-123">Ad esempio, `uint` è spesso a 16 bit in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="a5d4d-124">Se si passa un argomento a 16 bit a tale componente, dichiararla come `UShort` invece di `UInteger` in gestito [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] codice.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d4d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5d4d-125">See Also</span></span>  
 <span data-ttu-id="a5d4d-126">[Reflection](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775) </span><span class="sxs-lookup"><span data-stu-id="a5d4d-126">[Reflection](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775) </span></span>  
<span data-ttu-id="a5d4d-127"> [\<PAVE su > la scrittura di codice conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="a5d4d-127"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
