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
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>Attributo &#39; &lt;attributename&gt; &#39; non può essere applicato più volte
L'attributo può essere applicato una sola volta. Il `AttributeUsage` attributo determina se un attributo può essere applicato più volte.  
  
 **ID errore:** BC30663  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Assicurarsi che l'attributo viene applicato una sola volta.  
  
2.  Se si usano attributi personalizzati, è possibile modificare i `AttributeUsage` attributo per consentire l'utilizzo di più attributi, come con l'esempio seguente.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.AttributeUsageAttribute>
- [Creazione di attributi personalizzati](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
