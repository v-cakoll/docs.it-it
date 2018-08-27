---
title: parziale (Metodo) (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 69e16dd8b0fe0055124aca90fea65a36d9e413f3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933685"
---
# <a name="partial-method-c-reference"></a>parziale (Metodo) (Riferimenti per C#)
Un metodo parziale ha la firma definita in una parte di un tipo parziale e l'implementazione definita in un'altra parte del tipo. I metodi parziali consentono a Progettazione classi di fornire gli hook del metodo, analoghi ai gestori eventi, che gli sviluppatori possono decidere se implementare o meno. Se lo sviluppatore non fornisce un'implementazione, il compilatore rimuove la firma in fase di compilazione. Ai metodi parziali si applicano le condizioni seguenti:  
  
-   Le firme nelle due parti del tipo parziale devono corrispondere.  
  
-   Il metodo deve restituire void.  
  
-   Non è consentito alcun modificatore di accesso. I metodi parziali sono implicitamente privati.  
  
 Nell'esempio seguente viene illustrato un metodo parziale definito in due parti di una classe parziale:  
  
 [!code-csharp[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 Per altre informazioni, vedere [Classi e metodi parziali](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [partial (tipo)](../../../csharp/language-reference/keywords/partial-type.md)
