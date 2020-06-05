---
title: Il tipo di membro "<membername>" non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 030cb31b8f1ba0e8eaa82eeb8e37153411a53404
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400305"
---
# <a name="type-of-member-membername-is-not-cls-compliant"></a><span data-ttu-id="a2d69-102">Il tipo di membro "\<membername>" non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="a2d69-102">Type of member '\<membername>' is not CLS-compliant</span></span>
<span data-ttu-id="a2d69-103">Il tipo di dati specificato per questo membro non fa parte dell' [indipendenza del linguaggio e dei componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="a2d69-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="a2d69-104">Non si tratta di un errore all'interno del componente, perché il .NET Framework e Visual Basic supportano questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a2d69-104">This is not an error within your component, because the .NET Framework and Visual Basic support this data type.</span></span> <span data-ttu-id="a2d69-105">Tuttavia, un altro componente scritto in codice strettamente conforme a CLS potrebbe non supportare questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a2d69-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="a2d69-106">Un componente di questo tipo potrebbe non essere in grado di interagire correttamente con il componente.</span><span class="sxs-lookup"><span data-stu-id="a2d69-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="a2d69-107">I tipi di dati Visual Basic seguenti non sono conformi a CLS:</span><span class="sxs-lookup"><span data-stu-id="a2d69-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="a2d69-108">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="a2d69-108">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="a2d69-109">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="a2d69-109">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="a2d69-110">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="a2d69-110">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="a2d69-111">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="a2d69-111">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="a2d69-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="a2d69-112">By default, this message is a warning.</span></span> <span data-ttu-id="a2d69-113">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a2d69-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a2d69-114">**ID errore:** BC40025</span><span class="sxs-lookup"><span data-stu-id="a2d69-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a2d69-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a2d69-115">To correct this error</span></span>  
  
- <span data-ttu-id="a2d69-116">Se il componente si interfaccia solo con altri componenti .NET Framework o non si interfaccia con altri componenti, non è necessario apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="a2d69-116">If your component interfaces only with other .NET Framework components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="a2d69-117">Se si esegue l'interazione con un componente non scritto per il .NET Framework, potrebbe essere possibile determinare, tramite reflection o dalla documentazione, se supporta questo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a2d69-117">If you are interfacing with a component not written for the .NET Framework, you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="a2d69-118">In tal caso, non è necessario apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="a2d69-118">If it does, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="a2d69-119">Se si esegue l'interazione con un componente che non supporta questo tipo di dati, è necessario sostituirlo con il tipo più vicino conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="a2d69-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="a2d69-120">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="a2d69-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="a2d69-121">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="a2d69-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="a2d69-122">Se si interagisce con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno larghezze di dati diverse rispetto all'.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a2d69-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="a2d69-123">Ad esempio, `uint` è spesso a 16 bit in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="a2d69-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="a2d69-124">Se si passa un argomento a 16 bit a tale componente, dichiararlo come `UShort` anziché `UInteger` nel codice gestito del Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a2d69-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d69-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2d69-125">See also</span></span>

- [<span data-ttu-id="a2d69-126">Reflection</span><span class="sxs-lookup"><span data-stu-id="a2d69-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
