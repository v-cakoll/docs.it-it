---
title: AttributeUsage (C#)
ms.date: 04/25/2018
ms.openlocfilehash: a3a82e33d7259ec56ec3e907bc3d4d9f8a01167d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61668718"
---
# <a name="attributeusage-c"></a>AttributeUsage (C#)

Determina come usare una classe di attributi personalizzati. <xref:System.AttributeUsageAttribute> è un attributo che si applica alle definizioni di attributi personalizzati. L'attributo `AttributeUsage` consente di controllare:

- Elementi del programma a cui l'attributo può essere applicato. Se non se ne limita l'utilizzo, un attributo può essere applicato a uno qualsiasi degli elementi del programma seguenti:
  - assembly
  - modulo
  - campo
  - evento
  - method
  - param
  - proprietà
  - return
  - type
- Se un attributo può essere applicato più volte a un singolo elemento del programma.
- Se gli attributi vengono ereditati dalle classi derivate.

Le impostazioni predefinite sono simili all'esempio seguente quando vengono applicate in modo esplicito:

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

In questo esempio la classe `NewAttribute` può essere applicata a qualsiasi elemento del programma supportato, ma solo una volta a ogni entità. L'attributo viene ereditato dalle classi derivate se applicato a una classe base.

Gli argomenti <xref:System.AttributeUsageAttribute.AllowMultiple> e <xref:System.AttributeUsageAttribute.Inherited> sono facoltativi, quindi il codice seguente ha lo stesso effetto:

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

Il primo argomento <xref:System.AttributeUsageAttribute> deve consistere di uno o più elementi dell'enumerazione <xref:System.AttributeTargets>. Più tipi di destinazione possono essere collegati con l'operatore OR, nel modo illustrato nell'esempio seguente:

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

A partire da C# 7.3, gli attributi possono essere applicati alla proprietà o al campo sottostante per una proprietà implementata automaticamente. L'attributo si applica alla proprietà, a meno che non si specifichi l'identificatore `field` per l'attributo. Entrambe le situazioni sono illustrate nell'esempio seguente:

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

Se l'argomento <xref:System.AttributeUsageAttribute.AllowMultiple> è `true`, l'attributo restituito può essere applicato più volte a una singola entità, come illustrato nell'esempio seguente:

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

In questo caso, `MultiUseAttribute` può essere applicato più volte perché `AllowMultiple` è impostato su `true`. Entrambi i formati illustrati per applicare più attributi sono validi.

Se <xref:System.AttributeUsageAttribute.Inherited> è `false`, l'attributo non viene ereditato dalle classi derivate da una classe con attributi. Ad esempio:

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

In questo caso `NonInheritedAttribute` non viene applicato a `DClass` attraverso l'ereditarietà.

## <a name="remarks"></a>Osservazioni

L'attributo `AttributeUsage` è un attributo monouso ovvero non può essere applicato più volte alla stessa classe. `AttributeUsage` è un alias per <xref:System.AttributeUsageAttribute>.

Per altre informazioni, vedere [Accesso agli attributi tramite reflection (C#)](accessing-attributes-by-using-reflection.md).

## <a name="example"></a>Esempio

L'esempio seguente illustra l'effetto degli argomenti <xref:System.AttributeUsageAttribute.Inherited> e <xref:System.AttributeUsageAttribute.AllowMultiple> nell'attributo <xref:System.AttributeUsageAttribute> e come gli attributi personalizzati applicati a una classe possono essere enumerati.

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a>Output di esempio

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Guida per programmatori C#](../..//index.md)
- [Attributi](../../../..//standard/attributes/index.md)
- [Reflection (C#)](../reflection.md)
- [Attributi](index.md)
- [Creazione di attributi personalizzati (C#)](creating-custom-attributes.md)
- [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md) (Accesso agli attributi con reflection (C#))
