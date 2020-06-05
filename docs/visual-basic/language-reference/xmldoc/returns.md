---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: edbc374332bdcd67b385ac3d061045664e942460
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84399995"
---
# <a name="returns-visual-basic"></a>\<returns> (Visual Basic)
Specifica il valore restituito della proprietà o della funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Parametri  
 `description`  
 Descrizione del valore restituito.  
  
## <a name="remarks"></a>Commenti  
 Usare il `<returns>` tag nel commento per una dichiarazione di metodo per descrivere il valore restituito.  
  
 Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il `<returns>` tag per spiegare il risultato `DoesRecordExist` restituito dalla funzione.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](index.md)
