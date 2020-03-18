---
title: Tag consigliati per i commenti relativi alla documentazione - Guida alla programmazione in C
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: c746615d0d7a7a3058fbe2f8506a7a7c5c4a8779
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789717"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a>Tag consigliati per i commenti relativi alla documentazione (Guida per programmatori C

Il compilatore C# elabora i commenti alla documentazione nel codice e li formatta come XML in un file il cui nome è stato specificato nell'opzione della riga di comando **/doc**. Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato oppure utilizzare uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).

I tag vengono elaborati in costrutti di codice come tipi e membri dei tipi.

> [!NOTE]
> Non è possibile applicare a uno spazio dei nomi i commenti relativi alla documentazione.  
  
 Il compilatore elabora tutti i tag validi per XML. I tag seguenti forniscono le funzionalità comunemente usate nella documentazione dell'utente.  
  
## <a name="tags"></a>Tag  
  
|||||  
|---|---|---|---|
|[\<c>](./code-inline.md)|[\<para>](./para.md)|[\<vedi>](./see.md)*|[\<valore>](./value.md)  
|[\<>del codice](./code.md)|[\<>param](./param.md)*|[\<vedianche>](./seealso.md)*|  
|[\<esempio>](./example.md)|[\<>paramref](./paramref.md)|[\<>riepilogativo](./summary.md)|  
|[\<eccezione>](./exception.md)*|[\<>di autorizzazione](./permission.md)*|[\<>typeparam](./typeparam.md)*|  
|[\<includere>](./include.md)*|[\<osservazioni>](./remarks.md)|[\<>typeparamref](./typeparamref.md)|  
|[\<elenco>](./list.md)|[\<ereditadoc>](./inheritdoc.md)|[\<restituisce>](./returns.md)|
  
(indica\* che il compilatore verifica la sintassi.)

Se si vuole che nel testo di un commento alla documentazione vengano visualizzate parentesi angolari, usare la codifica HTML di `<` e `>`, ovvero rispettivamente `&lt;` e `&gt;`. Questa codifica è illustrata nell'esempio seguente.

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a>Vedere anche

- [Guida alla programmazione in C](../index.md)
- [-doc (opzioni del compilatore C](../../language-reference/compiler-options/doc-compiler-option.md)
- [Commenti relativi alla documentazione XML](./index.md)
