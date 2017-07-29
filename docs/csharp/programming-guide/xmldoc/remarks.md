---
title: '&lt;remarks&gt; (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- remarks
- <remarks>
dev_langs:
- CSharp
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cd11865fb0d4c8d21294107542fe39ad7e2b690a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ltremarksgt-c-programming-guide"></a>&lt;remarks&gt; (Guida per programmatori C#)
## <a name="syntax"></a>Sintassi  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parametri  
 `Description`  
 Descrizione del membro.  
  
## <a name="remarks"></a>Note  
 Il tag \<remarks> viene usato per aggiungere informazioni su un tipo, integrando le informazioni con [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md). Queste informazioni vengono visualizzate nella finestra Visualizzatore oggetti.  
  
 Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

