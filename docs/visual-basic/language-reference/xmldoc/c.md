---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: c8ba03d9cc01c4751d15c01530c6cbf7d499dc3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400163"
---
# <a name="c-visual-basic"></a>\<c> (Visual Basic)
Indica che il testo all'interno di una descrizione è codice.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---|---|  
|`text`|Il testo che si desidera indicare come codice.|  
  
## <a name="remarks"></a>Commenti  
 Il `<c>` tag fornisce un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice. Usare [\<code>](code.md) per indicare più righe come codice.  
  
 Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il `<c>` tag nella sezione Summary per indicare che `Counter` si tratta di codice.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](index.md)
