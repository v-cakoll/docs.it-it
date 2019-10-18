---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 25a0b307756401bed4d4c77d3668c2af53ba8b42
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524638"
---
# <a name="summary-visual-basic"></a>\<summary > (Visual Basic)
Specifica il riepilogo del membro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>Parametri  
 `description`  
 Un riepilogo dell'oggetto.  
  
## <a name="remarks"></a>Note  
 Usare il tag `<summary>` per descrivere un tipo o un membro del tipo. Utilizzare [ \<osservazioni >](../../../visual-basic/language-reference/xmldoc/remarks.md) per aggiungere informazioni supplementari alla descrizione di un tipo.  
  
 Il testo per il tag `<summary>` è l'unica fonte di informazioni sul tipo in IntelliSense e viene visualizzato anche nel Visualizzatore oggetti. Per informazioni sulla Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il tag `<summary>` per descrivere il metodo `ResetCounter` e `Counter` proprietà.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
