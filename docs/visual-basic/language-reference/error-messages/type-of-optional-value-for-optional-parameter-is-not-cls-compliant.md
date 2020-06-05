---
title: Il tipo di valore facoltativo per il parametro facoltativo <parametername> non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: 8e53d036ead114d828d9035cef76cee72bf6b1db
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400292"
---
# <a name="type-of-optional-value-for-optional-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="fbfc9-102">Il tipo di valore facoltativo per il parametro facoltativo \<parametername> non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="fbfc9-102">Type of optional value for optional parameter \<parametername> is not CLS-compliant</span></span>
<span data-ttu-id="fbfc9-103">Una procedura è contrassegnata come `<CLSCompliant(True)>`, ma viene dichiarato un parametro [facoltativo](../modifiers/optional.md) con valore predefinito di un tipo non conforme.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-103">A procedure is marked as `<CLSCompliant(True)>` but declares an [Optional](../modifiers/optional.md) parameter with default value of a noncompliant type.</span></span>  
  
 <span data-ttu-id="fbfc9-104">Affinché una procedura risulti compatibile con l'[indipendenza del linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve usare solo tipi conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="fbfc9-105">Questo scenario si applica ai tipi dei parametri, al tipo restituito e ai tipi di tutte le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span> <span data-ttu-id="fbfc9-106">Si applica anche ai valori predefiniti dei parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-106">It also applies to the default values of optional parameters.</span></span>  
  
 <span data-ttu-id="fbfc9-107">I tipi di dati Visual Basic seguenti non sono conformi a CLS:</span><span class="sxs-lookup"><span data-stu-id="fbfc9-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="fbfc9-108">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="fbfc9-108">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="fbfc9-109">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="fbfc9-109">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="fbfc9-110">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="fbfc9-110">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="fbfc9-111">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="fbfc9-111">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="fbfc9-112">Quando l'attributo <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-112">When you apply the <xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="fbfc9-113">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-113">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="fbfc9-114">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-114">If you do not apply <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="fbfc9-115">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-115">By default, this message is a warning.</span></span> <span data-ttu-id="fbfc9-116">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fbfc9-116">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="fbfc9-117">**ID errore:** BC40042</span><span class="sxs-lookup"><span data-stu-id="fbfc9-117">**Error ID:** BC40042</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fbfc9-118">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fbfc9-118">To correct this error</span></span>  
  
- <span data-ttu-id="fbfc9-119">Se il parametro facoltativo deve avere un valore predefinito di questo tipo specifico, rimuovere <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-119">If the optional parameter must have a default value of this particular type, remove <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="fbfc9-120">La procedura non può essere compatibile con CLS.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-120">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="fbfc9-121">Se la procedura deve essere compatibile con CLS, modificare il tipo di questo valore predefinito impostandolo sul tipo con una compatibilità con CLS più vicina.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-121">If the procedure must be CLS-compliant, change the type of this default value to the closest CLS-compliant type.</span></span> <span data-ttu-id="fbfc9-122">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-122">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="fbfc9-123">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-123">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="fbfc9-124">Se si interagisce con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno larghezze di dati diverse rispetto all'.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-124">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="fbfc9-125">Ad esempio, `int` è spesso a 16 bit in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-125">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="fbfc9-126">Se si accetta un valore integer a 16 bit da tale componente, dichiararlo come `Short` anziché `Integer` nel codice Visual Basic gestito.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-126">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
