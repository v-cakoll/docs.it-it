---
title: Generics e attributi - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 47bf4e8f07a8b6778db8fa675d745d362dc10d7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75703026"
---
# <a name="generics-and-attributes-c-programming-guide"></a>Generics e attributi (Guida per programmatori C#)
Gli attributi possono essere applicati a tipi generici allo stesso modo che ai tipi non generici. Per altre informazioni sull'applicazione di attributi, vedere [Attributi](../concepts/attributes/index.md).  
  
 Gli attributi personalizzati sono consentiti solo per fare riferimento a tipi generici aperti, che sono tipi generici per cui non è specificato alcun argomento tipo, e tipi generici costruiti chiusi, che specificano argomenti per tutti i parametri di tipo.  
  
 Gli esempi seguenti usano questo attributo personalizzato:  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 Un attributo può fare riferimento a un tipo generico aperto:  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 Specificare più parametri di tipo usando il numero appropriato di virgole. In questo esempio `GenericClass2` include due parametri di tipo:  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 Un attributo può fare riferimento a un tipo generico costruito chiuso:  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 Un attributo che fa riferimento a un parametro di tipo generico provoca un errore in fase di compilazione:  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 Un tipo generico non può ereditare da <xref:System.Attribute>:  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 Per ottenere informazioni su un tipo generico o un parametro di tipo in fase di esecuzione, è possibile usare i metodi di <xref:System.Reflection>. Per altre informazioni, vedere [Generics e reflection](./generics-and-reflection.md)  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Generics](./index.md)
- [Attributi](../../../standard/attributes/index.md)
