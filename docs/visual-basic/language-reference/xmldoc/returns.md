---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 62f70ae7f40fa3cde9492563b7bd14dfa5940a5f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352236"
---
# <a name="returns-visual-basic"></a>\<returns> (Visual Basic)
Specifies the return value of the property or function.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Parametri  
 `description`  
 Descrizione del valore restituito.  
  
## <a name="remarks"></a>Note  
 Use the `<returns>` tag in the comment for a method declaration to describe the return value.  
  
 Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
