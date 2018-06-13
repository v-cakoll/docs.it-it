---
title: Attributo &#39; &lt;attributename&gt; &#39; non può essere applicato più volte
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: df97a4e391406661db98eb1c958c0e12e45b6c49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584859"
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>Attributo &#39; &lt;attributename&gt; &#39; non può essere applicato più volte
L'attributo può essere applicato solo una volta. Il `AttributeUsage` attributo determina se un attributo può essere applicato più volte.  
  
 **ID errore:** BC30663  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che l'attributo viene applicato solo una volta.  
  
2.  Se si utilizza attributi personalizzati, è possibile modificare i relativi `AttributeUsage` attributo per consentire più utilizzo dell'attributo, come con l'esempio seguente.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.AttributeUsageAttribute>  
 [Creazione di attributi personalizzati](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
