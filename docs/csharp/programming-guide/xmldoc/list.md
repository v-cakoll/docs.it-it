---
title: '&lt;list&gt; (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- list
- <list>
dev_langs:
- CSharp
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
caps.latest.revision: 11
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
ms.openlocfilehash: b9d3dfa60530734a142295c8a8f2c32c4ecd9a47
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ltlistgt-c-programming-guide"></a>&lt;list&gt; (Guida per programmatori C#)
## <a name="syntax"></a>Sintassi  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### <a name="parameters"></a>Parametri  
 `term`  
 Termine da definire, che verrà definito in `description`.  
  
 `description`  
 Elemento di un elenco puntato o numerato oppure la definizione di un `term`.  
  
## <a name="remarks"></a>Note  
 Il blocco \<listheader> viene usato per definire la riga di intestazione di una tabella o di un elenco di definizioni. Per definire una tabella, è sufficiente specificare una voce per il termine nell'intestazione.  
  
 Ogni elemento dell'elenco viene specificato tramite un blocco \<item>. Quando si crea un elenco di definizioni, è necessario specificare sia `term` che `description`. Per le tabelle e gli elenchi puntati o numerati, tuttavia, è sufficiente fornire una voce per `description`.  
  
 Gli elenchi e le tabelle possono contenere un numero qualsiasi di blocchi \<item>.  
  
 Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

