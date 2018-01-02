---
title: "Tipo di membro &#39; &lt;membername&gt;&#39; non è conforme a CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords: BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bc82714d25efbe9d379fff36f92261cf25a78862
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a><span data-ttu-id="142ad-102">Tipo di membro &#39; &lt;membername&gt;&#39; non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="142ad-102">Type of member &#39;&lt;membername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="142ad-103">Il tipo di dati specificato per questo membro non è in parte il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="142ad-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="142ad-104">Non si tratta di un errore all'interno del componente, poiché il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] e [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supporta questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="142ad-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] support this data type.</span></span> <span data-ttu-id="142ad-105">Tuttavia, un altro componente scritto in codice strettamente conforme a CLS potrebbe non supportare questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="142ad-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="142ad-106">Un componente di questo tipo potrebbe non essere in grado di interagire correttamente con il componente.</span><span class="sxs-lookup"><span data-stu-id="142ad-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="142ad-107">I tipi di dati di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] seguenti non sono compatibili con CLS:</span><span class="sxs-lookup"><span data-stu-id="142ad-107">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="142ad-108">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="142ad-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="142ad-109">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="142ad-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="142ad-110">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="142ad-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="142ad-111">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="142ad-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="142ad-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="142ad-112">By default, this message is a warning.</span></span> <span data-ttu-id="142ad-113">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="142ad-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="142ad-114">**ID errore:** BC40025</span><span class="sxs-lookup"><span data-stu-id="142ad-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="142ad-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="142ad-115">To correct this error</span></span>  
  
-   <span data-ttu-id="142ad-116">Se il componente interagisce solo con altri [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] componenti o non si interfaccia con altri componenti, non è necessario apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="142ad-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="142ad-117">Se si prevede l'interazione con un componente non scritto per il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], potrebbe essere in grado di determinare, tramite reflection o dalla documentazione, che supporta questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="142ad-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="142ad-118">In caso affermativo, non è necessario apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="142ad-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="142ad-119">Se si prevede l'interazione con un componente che non supporta questo tipo di dati, è necessario sostituirlo con il tipo conforme a CLS più vicino.</span><span class="sxs-lookup"><span data-stu-id="142ad-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="142ad-120">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="142ad-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="142ad-121">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="142ad-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="142ad-122">Se si prevede l'interazione con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno un'ampiezza di dati diversa da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="142ad-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="142ad-123">Ad esempio, `uint` è spesso a 16 bit in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="142ad-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="142ad-124">Se si passa un argomento a 16 bit a tale componente, dichiararla come `UShort` anziché `UInteger` in gestito [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] codice.</span><span class="sxs-lookup"><span data-stu-id="142ad-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142ad-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="142ad-125">See Also</span></span>  
 [<span data-ttu-id="142ad-126">Reflection</span><span class="sxs-lookup"><span data-stu-id="142ad-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
 
