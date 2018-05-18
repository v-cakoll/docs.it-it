---
title: '&lt;param&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 3d89637e5b1238c582390750e8eef30960fa90b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ltparamgt-c-programming-guide"></a>&lt;param&gt; (Guida per programmatori C#)
## <a name="syntax"></a>Sintassi  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>Parametri  
 `name`  
 Nome di un parametro di metodo. Racchiudere il nome tra virgolette doppie (" ").  
  
 `description`  
 Descrizione del parametro.  
  
## <a name="remarks"></a>Note  
 Il tag \<param> viene usato nel commento di una dichiarazione di metodo per descrivere uno dei parametri del metodo. Per documentare più parametri, usare più tag \<param>.  
  
 Il testo del tag \<param> verrà visualizzato in IntelliSense, nella finestra Visualizzatore oggetti e nel report Web sui commenti del codice.  
  
 Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
