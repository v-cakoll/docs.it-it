---
title: <inheritdoc> - Guida per programmatori C#
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d660cb1739733c4e98ae0b7939476fe74e6cf200
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76795161"
---
# <a name="inheritdoc-c-programming-guide"></a>> inheritdoc \<(C# guida per programmatori)

## <a name="syntax"></a>Sintassi  
  
```xml  
<inheritdoc/> 
```  

## <a name="inheritdoc"></a>InheritDoc

Ereditano commenti XML da classi base, interfacce e metodi simili. In questo modo si elimina la copia indesiderata e si incollano i commenti XML duplicati e i commenti XML vengono sincronizzati automaticamente. 
  
## <a name="remarks"></a>Note  
Aggiungere i commenti XML in classi o interfacce di base e consentire a InheritDoc di copiare i commenti alle classi di implementazione.

Aggiungere i commenti XML ai metodi sincroni e consentire a InheritDoc di copiare i commenti nelle versioni asincrone degli stessi metodi.  

Se si desidera copiare i commenti da un membro specifico, è possibile utilizzare l'attributo `cref` per specificare il membro.
  
## <a name="examples"></a>Esempi
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
