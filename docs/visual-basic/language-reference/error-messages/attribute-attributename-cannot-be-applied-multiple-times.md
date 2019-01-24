---
title: Attributo &#39; &lt;attributename&gt; &#39; non può essere applicato più volte
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 6609ce299799bc3c4b78d48478e99e4d4101dd72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565163"
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a><span data-ttu-id="a9244-102">Attributo &#39; &lt;attributename&gt; &#39; non può essere applicato più volte</span><span class="sxs-lookup"><span data-stu-id="a9244-102">Attribute &#39;&lt;attributename&gt;&#39; cannot be applied multiple times</span></span>
<span data-ttu-id="a9244-103">L'attributo può essere applicato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="a9244-103">The attribute can only be applied once.</span></span> <span data-ttu-id="a9244-104">Il `AttributeUsage` attributo determina se un attributo può essere applicato più volte.</span><span class="sxs-lookup"><span data-stu-id="a9244-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="a9244-105">**ID errore:** BC30663</span><span class="sxs-lookup"><span data-stu-id="a9244-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a9244-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a9244-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="a9244-107">Assicurarsi che l'attributo viene applicato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="a9244-107">Make sure the attribute is only applied once.</span></span>  
  
2.  <span data-ttu-id="a9244-108">Se si usano attributi personalizzati, è possibile modificare i `AttributeUsage` attributo per consentire l'utilizzo di più attributi, come con l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a9244-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9244-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9244-109">See also</span></span>
- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="a9244-110">Creazione di attributi personalizzati</span><span class="sxs-lookup"><span data-stu-id="a9244-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="a9244-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="a9244-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
