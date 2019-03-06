---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: e629a738a706b09dec97dd6593ef493470ec9472
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473877"
---
# <a name="summary-visual-basic"></a>\<summary> (Visual Basic)
Specifica il riepilogo del membro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>Parametri  
 `description`  
 Un riepilogo dell'oggetto.  
  
## <a name="remarks"></a>Note  
 Usare il `<summary>` tag per descrivere un tipo o un membro del tipo. Utilizzare [ \<osservazioni >](../../../visual-basic/language-reference/xmldoc/remarks.md) per aggiungere informazioni supplementari alla descrizione di un tipo.  
  
 Il testo per il `<summary>` tag è l'unica fonte di informazioni sul tipo in IntelliSense e viene anche visualizzato nel Visualizzatore oggetti. Per informazioni sul Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<summary>` tag per descrivere le `ResetCounter` metodo e `Counter` proprietà.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
