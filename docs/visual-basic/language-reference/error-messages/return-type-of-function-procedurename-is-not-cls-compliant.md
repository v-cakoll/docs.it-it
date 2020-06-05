---
title: Il tipo restituito della funzione '<procedurename>' non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 9cc7e25ef1be21ff2f6a71dcb61bc29ec92da30f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400357"
---
# <a name="return-type-of-function-procedurename-is-not-cls-compliant"></a><span data-ttu-id="f6eb0-102">Il tipo restituito della funzione '\<procedurename>' non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="f6eb0-102">Return type of function '\<procedurename>' is not CLS-compliant</span></span>
<span data-ttu-id="f6eb0-103">Una `Function` routine è contrassegnata come `<CLSCompliant(True)>` , ma restituisce un tipo contrassegnato come `<CLSCompliant(False)>` , non contrassegnato o non qualificato perché è un tipo non conforme.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="f6eb0-104">Affinché una procedura risulti compatibile con l'[indipendenza del linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve usare solo tipi conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="f6eb0-105">Questo scenario si applica ai tipi dei parametri, al tipo restituito e ai tipi di tutte le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="f6eb0-106">I tipi di dati Visual Basic seguenti non sono conformi a CLS:</span><span class="sxs-lookup"><span data-stu-id="f6eb0-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="f6eb0-107">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="f6eb0-107">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="f6eb0-108">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="f6eb0-108">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="f6eb0-109">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="f6eb0-109">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="f6eb0-110">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="f6eb0-110">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="f6eb0-111">Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="f6eb0-112">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="f6eb0-113">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="f6eb0-114">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-114">By default, this message is a warning.</span></span> <span data-ttu-id="f6eb0-115">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f6eb0-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f6eb0-116">**ID errore:** BC40027</span><span class="sxs-lookup"><span data-stu-id="f6eb0-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f6eb0-117">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f6eb0-117">To correct this error</span></span>  
  
- <span data-ttu-id="f6eb0-118">Se la `Function` routine deve restituire questo particolare tipo, rimuovere <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="f6eb0-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="f6eb0-119">La procedura non può essere compatibile con CLS.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="f6eb0-120">Se la `Function` routine deve essere conforme a CLS, impostare il tipo restituito sul tipo conforme a CLS più vicino.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="f6eb0-121">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="f6eb0-122">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="f6eb0-123">Se si interagisce con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno larghezze di dati diverse rispetto all'.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="f6eb0-124">Ad esempio, `int` è spesso a 16 bit in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="f6eb0-125">Se si sta restituendo un intero a 16 bit a tale componente, dichiararlo come `Short` anziché `Integer` nel codice Visual Basic gestito.</span><span class="sxs-lookup"><span data-stu-id="f6eb0-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
