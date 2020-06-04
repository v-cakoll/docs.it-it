---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 24358a1b004f1cefbfeb3fb8451380ed883841df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411473"
---
# <a name="value-visual-basic"></a>\<value> (Visual Basic)
Specifica la descrizione di una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Parametri  
 `property-description`  
 Descrizione della proprietà.  
  
## <a name="remarks"></a>Commenti  
 Usare il `<value>` tag per descrivere una proprietà. Si noti che quando si aggiunge una proprietà usando la creazione guidata codice nell'ambiente di sviluppo di Visual Studio, verrà aggiunto un [\<summary>](summary.md) tag per la nuova proprietà. È quindi necessario aggiungere manualmente un `<value>` tag per descrivere il valore rappresentato dalla proprietà.  
  
 Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il `<value>` tag per descrivere il valore che la `Counter` proprietà possiede.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](index.md)
