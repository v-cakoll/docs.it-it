---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 89a2daad1c47ea8e2a045b2e22a9569e54086e8a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970740"
---
# <a name="value-visual-basic"></a>\<value> (Visual Basic)
Specifica la descrizione di una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>Parametri  
 `property-description`  
 Descrizione della proprietà.  
  
## <a name="remarks"></a>Note  
 Usare il `<value>` tag per descrivere una proprietà. Si noti che quando si aggiunge una proprietà usando la procedura guidata per codice nell'ambiente di sviluppo Visual Studio, verrà aggiunto un [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md) tag per la nuova proprietà. È quindi necessario aggiungere manualmente un `<value>` tag per descrivere il valore che rappresenta la proprietà.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<value>` tag per descrivere il valore di `Counter` contiene proprietà.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
