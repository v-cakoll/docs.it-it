---
title: '&lt;Restituisce&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6130a6fabe450900fe19ef4d361654508f907ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltreturnsgt-visual-basic"></a>&lt;Restituisce&gt; (Visual Basic)
Specifica il valore restituito della proprietà o della funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a>Parametri  
 `description`  
 Descrizione del valore restituito.  
  
## <a name="remarks"></a>Note  
 Utilizzare il `<returns>` tag nel commento per descrivere il valore restituito di una dichiarazione di metodo.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `<returns>` tag per illustrare i valori di `DoesRecordExist` risultato della funzione.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
