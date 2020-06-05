---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: c57ddb870192bd94301f99eb71ad29526e8efc28
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400021"
---
# <a name="remarks-visual-basic"></a>\<remarks> (Visual Basic)
Specifica una sezione di osservazioni per il membro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>Parametri  
 `description`  
 Descrizione del membro.  
  
## <a name="remarks"></a>Commenti  
 Usare il `<remarks>` tag per aggiungere informazioni su un tipo, integrando le informazioni specificate con [\<summary>](summary.md) .  
  
 Queste informazioni vengono visualizzate nel Visualizzatore oggetti. Per informazioni sulla Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il `<remarks>` tag per spiegare cosa `UpdateRecord` fa il metodo.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](index.md)
