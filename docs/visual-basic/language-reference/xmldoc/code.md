---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: aa65fed863718f1f00b510f82051a13e764e1b23
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400144"
---
# <a name="code-visual-basic"></a>\<code> (Visual Basic)
Indica che il testo è costituito da più righe di codice.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>Parametri  
 `content`  
 Testo da contrassegnare come codice.  
  
## <a name="remarks"></a>Commenti  
 Usare il `<code>` tag per indicare più righe come codice. Usare [\<c>](c.md) per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.  
  
 Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il \<code> tag per includere il codice di esempio per l'uso del `ID` campo.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](index.md)
