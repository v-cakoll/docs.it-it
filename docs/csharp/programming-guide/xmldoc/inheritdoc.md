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
ms.openlocfilehash: 6f42462f21d045428577cd2123e2180d866f1e1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156948"
---
# <a name="inheritdoc-c-programming-guide"></a>\<> inheritdoc (Guida per programmatori C

## <a name="syntax"></a>Sintassi  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a>EreditatoreDoc

Ereditare i commenti XML dalle classi base, dalle interfacce e da metodi simili. In questo modo si eliminano le operazioni di copia e incolla indesiderate di commenti XML duplicati e mantiene automaticamente sincronizzati i commenti XML.
  
## <a name="remarks"></a>Osservazioni  
Aggiungere i commenti XML nelle classi di base o nelle interfacce e consentire a InheritDoc di copiare i commenti nelle classi di implementazione.

Aggiungere i commenti XML ai metodi sincroni e consentire a InheritDoc di copiare i commenti nelle versioni asincrone degli stessi metodi.  

Se si desidera copiare i commenti da un `cref` membro specifico, è possibile utilizzare l'attributo per specificare il membro.
  
## <a name="examples"></a>Esempi
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
