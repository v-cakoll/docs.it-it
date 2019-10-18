---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: b220c2a9aa544413c3692485f6c1eb2b64e54389
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524690"
---
# <a name="returns-visual-basic"></a>\<returns > (Visual Basic)
Specifica il valore restituito della proprietà o della funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Parametri  
 `description`  
 Descrizione del valore restituito.  
  
## <a name="remarks"></a>Note  
 Usare il tag `<returns>` nel commento per una dichiarazione di metodo per descrivere il valore restituito.  
  
 Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il tag `<returns>` per spiegare il risultato restituito dalla funzione `DoesRecordExist`.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
