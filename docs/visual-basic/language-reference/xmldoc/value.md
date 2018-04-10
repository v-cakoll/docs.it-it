---
title: '&lt;valore&gt; (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a72c6330596e59d26fbae9d13f6b9c8b1987e519
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltvaluegt-visual-basic"></a>&lt;valore&gt; (Visual Basic)
Specifica la descrizione di una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>Parametri  
 `property-description`  
 Descrizione della proprietà.  
  
## <a name="remarks"></a>Note  
 Utilizzare il `<value>` tag per descrivere una proprietà. Si noti che quando si aggiunge una proprietà utilizzando la procedura guidata codice nell'ambiente di sviluppo di Visual Studio, verrà aggiunto un [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md) tag per la nuova proprietà. È quindi necessario aggiungere manualmente un `<value>` tag per descrivere il valore che rappresenta la proprietà.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `<value>` tag per descrivere il valore di `Counter` contiene proprietà.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
