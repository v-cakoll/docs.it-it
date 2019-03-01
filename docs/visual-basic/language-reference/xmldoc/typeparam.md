---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: d7fb980545a532e39310ea3e9d663a2b5a81a006
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968452"
---
# <a name="typeparam-visual-basic"></a>\<typeparam > (Visual Basic)
Definisce un parametro di tipo nome e una descrizione.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a>Parametri  
 `name`  
 Nome del parametro di tipo. Racchiudere il nome tra virgolette doppie (" ").  
  
 `description`  
 Descrizione del parametro di tipo.  
  
## <a name="remarks"></a>Note  
 Usare il `<typeparam>` tag del commento per un tipo generico o dichiarazione di un membro generico descrivere uno dei parametri di tipo.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<typeparam>` tag per descrivere il `id` parametro.  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>Vedere anche
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
