---
title: <see> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 31806ad06cc97fa27f1944f2500f0f9cbb29f561
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262101"
---
# <a name="see-c-programming-guide"></a>\<see> (Guida per programmatori C#)
## <a name="syntax"></a>Sintassi  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parametri  
 cref = " `member`"  
 Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output. Racchiudere *member* tra virgolette doppie (" ").  
  
## <a name="remarks"></a>Note  
 Con il tag \<see> è possibile specificare un collegamento nel testo. Usare [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) per indicare che il testo deve essere inserito in una sezione Vedere anche. Usare l'[attributo cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) per creare collegamenti ipertestuali interni alle pagine della documentazione per gli elementi di codice.  
  
 Compilare con [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.  
  
 Nell'esempio seguente viene illustrato un tag \<see> all'interno di una sezione di riepilogo.  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
