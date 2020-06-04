---
title: Il tipo di parametro '<parametername>' non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: edbcadf271c4ccafc11e5b64eb103a0290976179
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413014"
---
# <a name="type-of-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="57738-102">Il tipo di parametro '\<parametername>' non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="57738-102">Type of parameter '\<parametername>' is not CLS-compliant</span></span>
<span data-ttu-id="57738-103">Una routine è contrassegnata come `<CLSCompliant(True)>` ma dichiara un parametro con un tipo contrassegnato come `<CLSCompliant(False)>` , non contrassegnato o non qualificato perché è un tipo non conforme.</span><span class="sxs-lookup"><span data-stu-id="57738-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="57738-104">Affinché una procedura risulti compatibile con l'[indipendenza del linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve usare solo tipi conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="57738-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="57738-105">Questo scenario si applica ai tipi dei parametri, al tipo restituito e ai tipi di tutte le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="57738-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="57738-106">I tipi di dati Visual Basic seguenti non sono conformi a CLS:</span><span class="sxs-lookup"><span data-stu-id="57738-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="57738-107">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="57738-107">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="57738-108">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="57738-108">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="57738-109">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="57738-109">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="57738-110">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="57738-110">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="57738-111">Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="57738-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="57738-112">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="57738-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="57738-113">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="57738-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="57738-114">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="57738-114">By default, this message is a warning.</span></span> <span data-ttu-id="57738-115">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="57738-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="57738-116">**ID errore:** BC40028</span><span class="sxs-lookup"><span data-stu-id="57738-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="57738-117">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="57738-117">To correct this error</span></span>  
  
- <span data-ttu-id="57738-118">Se la routine deve prendere un parametro di questo tipo specifico, rimuovere <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="57738-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="57738-119">La procedura non può essere compatibile con CLS.</span><span class="sxs-lookup"><span data-stu-id="57738-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="57738-120">Se la routine deve essere conforme a CLS, modificare il tipo di questo parametro sul tipo conforme a CLS più vicino.</span><span class="sxs-lookup"><span data-stu-id="57738-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="57738-121">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="57738-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="57738-122">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="57738-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="57738-123">Se si interagisce con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno larghezze di dati diverse rispetto all'.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57738-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="57738-124">Ad esempio, `int` è spesso a 16 bit in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="57738-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="57738-125">Se si accetta un valore integer a 16 bit da tale componente, dichiararlo come `Short` anziché `Integer` nel codice Visual Basic gestito.</span><span class="sxs-lookup"><span data-stu-id="57738-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
