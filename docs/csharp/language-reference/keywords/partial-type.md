---
title: parziale (Tipo) (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 362a02815cb249d57c0bd19706714df1d71644f4
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929663"
---
# <a name="partial-type-c-reference"></a>parziale (Tipo) (Riferimenti per C#)
Le definizioni di tipi parziali consentono la suddivisione in più file della definizione di una classe, una struttura o un'interfaccia.  
  
 In File1.cs:  
  
 [!code-csharp[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 In File2.cs la dichiarazione:  
  
 [!code-csharp[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## <a name="remarks"></a>Note  
 La suddivisione di un tipo di classe, struttura o interfaccia in più file può essere utile per progetti di grandi dimensioni o quando si usa codice generato automaticamente come quello fornito da [Progettazione Windows Form](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md). Un tipo parziale può contenere un [metodo parziale](../../../csharp/language-reference/keywords/partial-method.md). Per altre informazioni, vedere [Classi e metodi parziali](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)  
- [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md)
