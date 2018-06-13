---
title: '&lt;value&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 22de15560d6db6e8a70cea744dd9d85359336306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356431"
---
# <a name="ltvaluegt-c-programming-guide"></a>&lt;value&gt; (Guida per programmatori C#)
## <a name="syntax"></a>Sintassi  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>Parametri  
 `property-description`  
 Descrizione della proprietà.  
  
## <a name="remarks"></a>Note  
 Il tag \<value> consente di descrivere il valore che rappresenta una proprietà. Si noti che quando si aggiunge una proprietà tramite la procedura guidata per il codice nell'ambiente di sviluppo di Visual Studio .NET, verrà aggiunto un tag [ \<summary>](../../../csharp/programming-guide/xmldoc/summary.md) per la nuova proprietà. È quindi necessario aggiungere manualmente un tag \<value> per descrivere il valore rappresentato dalla proprietà.  
  
 Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
