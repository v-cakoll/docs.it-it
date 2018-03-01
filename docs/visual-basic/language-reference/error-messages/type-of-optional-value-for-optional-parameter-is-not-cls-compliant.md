---
title: "Tipo di valore facoltativo per il parametro facoltativo &lt;parametername&gt; non è conforme a CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50ea7ce108796d099272c4a909f2fc6c81e9c77c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="type-of-optional-value-for-optional-parameter-ltparameternamegt-is-not-cls-compliant"></a><span data-ttu-id="a3fa9-102">Tipo di valore facoltativo per il parametro facoltativo &lt;parametername&gt; non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="a3fa9-102">Type of optional value for optional parameter &lt;parametername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="a3fa9-103">Una procedura è contrassegnata come `<CLSCompliant(True)>`, ma viene dichiarato un parametro [facoltativo](../../../visual-basic/language-reference/modifiers/optional.md) con valore predefinito di un tipo non conforme.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-103">A procedure is marked as `<CLSCompliant(True)>` but declares an [Optional](../../../visual-basic/language-reference/modifiers/optional.md) parameter with default value of a noncompliant type.</span></span>  
  
 <span data-ttu-id="a3fa9-104">Affinché una procedura risulti compatibile con l'[indipendenza del linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve usare solo tipi conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="a3fa9-105">Questo scenario si applica ai tipi dei parametri, al tipo restituito e ai tipi di tutte le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span> <span data-ttu-id="a3fa9-106">Si applica anche ai valori predefiniti dei parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-106">It also applies to the default values of optional parameters.</span></span>  
  
 <span data-ttu-id="a3fa9-107">I tipi di dati di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] seguenti non sono compatibili con CLS:</span><span class="sxs-lookup"><span data-stu-id="a3fa9-107">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="a3fa9-108">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="a3fa9-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="a3fa9-109">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="a3fa9-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="a3fa9-110">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="a3fa9-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="a3fa9-111">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="a3fa9-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="a3fa9-112">Quando l'attributo <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-112">When you apply the <xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="a3fa9-113">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-113">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="a3fa9-114">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-114">If you do not apply <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="a3fa9-115">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-115">By default, this message is a warning.</span></span> <span data-ttu-id="a3fa9-116">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a3fa9-116">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a3fa9-117">**ID errore:** BC40042</span><span class="sxs-lookup"><span data-stu-id="a3fa9-117">**Error ID:** BC40042</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a3fa9-118">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a3fa9-118">To correct this error</span></span>  
  
-   <span data-ttu-id="a3fa9-119">Se il parametro facoltativo deve avere un valore predefinito di questo particolare tipo, rimuovere <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-119">If the optional parameter must have a default value of this particular type, remove <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="a3fa9-120">La procedura non può essere compatibile con CLS.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-120">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="a3fa9-121">Se la procedura deve essere compatibile con CLS, modificare il tipo di questo valore predefinito impostandolo sul tipo con una compatibilità con CLS più vicina.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-121">If the procedure must be CLS-compliant, change the type of this default value to the closest CLS-compliant type.</span></span> <span data-ttu-id="a3fa9-122">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-122">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="a3fa9-123">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-123">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="a3fa9-124">Se si prevede l'interazione con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno un'ampiezza di dati diversa da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3fa9-124">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="a3fa9-125">Ad esempio, `int` è spesso a 16 bit in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-125">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="a3fa9-126">Se si accetta un valore integer a 16 bit da tale componente, dichiararlo come `Short` anziché `Integer` nel codice [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gestito.</span><span class="sxs-lookup"><span data-stu-id="a3fa9-126">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>