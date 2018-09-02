---
title: Tipo del parametro &#39; &lt;parametername&gt; &#39; non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: 13a4e35cd27ed5aa135cec77c4415f223cba70f2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43403036"
---
# <a name="type-of-parameter-39ltparameternamegt39-is-not-cls-compliant"></a><span data-ttu-id="a2bb8-102">Tipo del parametro &#39; &lt;parametername&gt; &#39; non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="a2bb8-102">Type of parameter &#39;&lt;parametername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="a2bb8-103">Una procedura è contrassegnata come `<CLSCompliant(True)>` ma viene dichiarato un parametro con un tipo contrassegnato come `<CLSCompliant(False)>`, non è contrassegnata o non può essere utilizzato perché è un tipo non conforme.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="a2bb8-104">Affinché una procedura risulti compatibile con l'[indipendenza del linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve usare solo tipi conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="a2bb8-105">Questo scenario si applica ai tipi dei parametri, al tipo restituito e ai tipi di tutte le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="a2bb8-106">I seguenti tipi di dati di Visual Basic non sono conformi a CLS:</span><span class="sxs-lookup"><span data-stu-id="a2bb8-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="a2bb8-107">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="a2bb8-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="a2bb8-108">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="a2bb8-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="a2bb8-109">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="a2bb8-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="a2bb8-110">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="a2bb8-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="a2bb8-111">Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="a2bb8-112">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="a2bb8-113">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="a2bb8-114">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-114">By default, this message is a warning.</span></span> <span data-ttu-id="a2bb8-115">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a2bb8-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a2bb8-116">**ID errore:** BC40028</span><span class="sxs-lookup"><span data-stu-id="a2bb8-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a2bb8-117">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a2bb8-117">To correct this error</span></span>  
  
-   <span data-ttu-id="a2bb8-118">Se la routine deve accettare un parametro di questo tipo specifico, rimuovere il <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="a2bb8-119">La procedura non può essere compatibile con CLS.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="a2bb8-120">Se la procedura deve essere conforme a CLS, modificare il tipo di questo parametro di tipo conforme a CLS più vicina.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="a2bb8-121">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="a2bb8-122">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="a2bb8-123">Se si prevede l'interazione con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno un'ampiezza di dati diversa da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2bb8-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="a2bb8-124">Ad esempio, `int` è spesso a 16 bit in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="a2bb8-125">Se si accetta un intero a 16 bit da tale componente, dichiararlo come `Short` invece di `Integer` nel codice gestito di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a2bb8-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>