---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 90f358aad8e3219b2e3cb3e9b996a24b3138828b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970831"
---
# <a name="remarks-visual-basic"></a>\<remarks> (Visual Basic)
Specifica una sezione Osservazioni per il membro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parametri  
 `description`  
 Descrizione del membro.  
  
## <a name="remarks"></a>Note  
 Usare la `<remarks>` tag per aggiungere informazioni su un tipo, integrando le informazioni specificate con [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 Queste informazioni vengono visualizzate nel Visualizzatore oggetti. Per informazioni sul Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa il `<remarks>` tag per illustrare i valori di `UpdateRecord` metodo.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
