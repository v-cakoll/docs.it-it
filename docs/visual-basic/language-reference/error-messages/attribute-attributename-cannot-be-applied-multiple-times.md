---
title: Impossibile applicare più volte l'attributo '<attributename>'
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: da4a766e2617308cb33b9673a88db9e7a954152a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304298"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="33f25-102">Attributo '\<NomeAttributo >' non può essere applicato più volte</span><span class="sxs-lookup"><span data-stu-id="33f25-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>
<span data-ttu-id="33f25-103">L'attributo può essere applicato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="33f25-103">The attribute can only be applied once.</span></span> <span data-ttu-id="33f25-104">Il `AttributeUsage` attributo determina se un attributo può essere applicato più volte.</span><span class="sxs-lookup"><span data-stu-id="33f25-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="33f25-105">**ID errore:** BC30663</span><span class="sxs-lookup"><span data-stu-id="33f25-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="33f25-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="33f25-106">To correct this error</span></span>  
  
1. <span data-ttu-id="33f25-107">Assicurarsi che l'attributo viene applicato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="33f25-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="33f25-108">Se si usano attributi personalizzati, è possibile modificare i `AttributeUsage` attributo per consentire l'utilizzo di più attributi, come con l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="33f25-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33f25-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33f25-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="33f25-110">Creazione di attributi personalizzati</span><span class="sxs-lookup"><span data-stu-id="33f25-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="33f25-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="33f25-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
