---
title: Codice unsafe e puntatori (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: b57a6f607dbdbc84c60889a5ce2b1e3c33d7f435
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a>Codice unsafe e puntatori (Guida per programmatori C#)
Per mantenere l'indipendenza dai tipi e la sicurezza, C# non supporta il puntatore aritmetico per impostazione predefinita. Tuttavia, se si usa la parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), è possibile definire un contesto non sicuro in cui si possono usare i puntatori. Per altre informazioni sui puntatori, vedere l'argomento [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).  
  
> [!NOTE]
>  Nel supporto Common Language Runtime (CLR) il codice di tipo unsafe è detto codice non verificabile. Il codice unsafe in C# non è necessariamente pericoloso, è solo codice di cui il supporto CLR non può verificare la sicurezza. CLR pertanto eseguirà il codice unsafe solo se si trova in un assembly completamente attendibile. Se si usa codice unsafe, è responsabilità dell'utente verificare che il codice non introduca rischi per la sicurezza o errori dei puntatori.  
  
## <a name="unsafe-code-overview"></a>Panoramica del codice unsafe  
 Il codice unsafe presenta le proprietà seguenti:  
  
-   Metodi, tipi e blocchi di codice possono essere definiti come unsafe.  
  
-   In alcuni casi il codice unsafe può migliorare le prestazioni di un'applicazione poiché vengono rimosse le verifiche dei limiti di matrice.  
  
-   Il codice unsafe è necessario quando si chiamano funzioni native che richiedono i puntatori.  
  
-   L'uso del codice unsafe implica rischi per la sicurezza e la stabilità.  
  
-   Affinché C# compili il codice unsafe, l'applicazione deve essere compilata con [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  
  
## <a name="related-sections"></a>Sezioni correlate  
 Per altre informazioni, vedere:  
  
-   [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [Buffer a dimensione fissa](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [Procedura: Usare i puntatori per copiare una matrice di byte](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
