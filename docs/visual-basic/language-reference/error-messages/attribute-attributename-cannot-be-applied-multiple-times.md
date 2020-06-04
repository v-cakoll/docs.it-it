---
title: Impossibile applicare più volte l'attributo '<attributename>'
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 14145f165adf5ccd20298a70ca5596488b488b0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409959"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>Impossibile applicare più volte l'attributo '\<attributename>'

L'attributo può essere applicato una sola volta. L' `AttributeUsage` attributo determina se un attributo può essere applicato più di una volta.  
  
 **ID errore:** BC30663  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che l'attributo venga applicato una sola volta.  
  
2. Se si usano attributi personalizzati sviluppati, provare a modificare l' `AttributeUsage` attributo per consentire l'utilizzo di più attributi, come nell'esempio seguente.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AttributeUsageAttribute>
- [Creazione di attributi personalizzati](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../programming-guide/concepts/attributes/attributeusage.md)
