---
title: Generics e attributi (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 0fe2d61001584aa7c175500bfa754b2ae2244660
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45675535"
---
# <a name="generics-and-attributes-c-programming-guide"></a>Generics e attributi (Guida per programmatori C#)
Gli attributi possono essere applicati a tipi generici allo stesso modo che ai tipi non generici. Per altre informazioni sull'applicazione di attributi, vedere [Attributi](../../../csharp/programming-guide/concepts/attributes/index.md).  
  
 Gli attributi personalizzati sono consentiti solo per fare riferimento a tipi generici aperti, che sono tipi generici per cui non è specificato alcun argomento tipo, e tipi generici costruiti chiusi, che specificano argomenti per tutti i parametri di tipo.  
  
 Gli esempi seguenti usano questo attributo personalizzato:  
  
 [!code-csharp[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 Un attributo può fare riferimento a un tipo generico aperto:  
  
 [!code-csharp[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 Specificare più parametri di tipo usando il numero appropriato di virgole. In questo esempio `GenericClass2` include due parametri di tipo:  
  
 [!code-csharp[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 Un attributo può fare riferimento a un tipo generico costruito chiuso:  
  
 [!code-csharp[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 Un attributo che fa riferimento a un parametro di tipo generico provoca un errore in fase di compilazione:  
  
 [!code-csharp[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 Un tipo generico non può ereditare da <xref:System.Attribute>:  
  
 [!code-csharp[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 Per ottenere informazioni su un tipo generico o un parametro di tipo in fase di esecuzione, è possibile usare i metodi di <xref:System.Reflection>. Per altre informazioni, vedere [Generics e reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Generics](../../../csharp/programming-guide/generics/index.md)  
- [Attributi](../../../../docs/standard/attributes/index.md)
