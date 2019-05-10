---
title: Il tipo sottostante <typename> di Enum non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: b58759502b9297f9cd5ac89296ab147c40fc89f1
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913353"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a><span data-ttu-id="32653-102">Il tipo sottostante \<typename > dell'enumerazione non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="32653-102">Underlying type \<typename> of Enum is not CLS-compliant</span></span>
<span data-ttu-id="32653-103">Il tipo di dati specificato per questa enumerazione non è in parte i [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="32653-103">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="32653-104">Non si tratta di un errore all'interno del componente, perché il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] e Visual Basic supporta questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="32653-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and Visual Basic support this data type.</span></span> <span data-ttu-id="32653-105">Tuttavia, un altro componente scritto in codice strettamente conforme a CLS potrebbe non supportare questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="32653-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="32653-106">Un componente di questo tipo potrebbe non essere in grado di interagire correttamente con il componente.</span><span class="sxs-lookup"><span data-stu-id="32653-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="32653-107">I seguenti tipi di dati di Visual Basic non sono conformi a CLS:</span><span class="sxs-lookup"><span data-stu-id="32653-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="32653-108">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="32653-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="32653-109">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="32653-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="32653-110">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="32653-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="32653-111">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="32653-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="32653-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="32653-112">By default, this message is a warning.</span></span> <span data-ttu-id="32653-113">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="32653-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="32653-114">**ID errore:** BC40032</span><span class="sxs-lookup"><span data-stu-id="32653-114">**Error ID:** BC40032</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="32653-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="32653-115">To correct this error</span></span>  
  
- <span data-ttu-id="32653-116">Se il componente interagisce solo con altri [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] componenti o non si interfaccia con altri componenti, non è necessario apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="32653-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="32653-117">Se si prevede l'interazione con un componente non scritto per il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], potrebbe essere in grado di determinare, tramite reflection o nella documentazione, che supporta questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="32653-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="32653-118">In caso affermativo, non occorre apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="32653-118">If it does, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="32653-119">Se si prevede l'interazione con un componente che non supporta questo tipo di dati, è necessario sostituirlo con il tipo compatibile con CLS più vicino.</span><span class="sxs-lookup"><span data-stu-id="32653-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="32653-120">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="32653-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="32653-121">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="32653-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="32653-122">Se si prevede l'interazione con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno un'ampiezza di dati diversa da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32653-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="32653-123">Ad esempio, `uint` è spesso a 16 bit in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="32653-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="32653-124">Se si passa un argomento a 16 bit a un componente, dichiararlo come `UShort` invece di `UInteger` nel codice gestito di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="32653-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32653-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32653-125">See also</span></span>

- [<span data-ttu-id="32653-126">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32653-126">Reflection (Visual Basic)</span></span>](../../programming-guide/concepts/reflection.md)
- [<span data-ttu-id="32653-127">Reflection</span><span class="sxs-lookup"><span data-stu-id="32653-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
