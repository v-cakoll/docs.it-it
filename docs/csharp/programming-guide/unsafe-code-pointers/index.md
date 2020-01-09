---
title: Codice non gestito e puntatori - Guida per programmatori C#
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
ms.openlocfilehash: 013af4e55c8fc396bbc92058d7fb454484f3263e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711831"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a>Codice non gestito e puntatori (Guida per programmatori C#)

Per mantenere l'indipendenza dai tipi e la sicurezza, C# non supporta il puntatore aritmetico per impostazione predefinita. Tuttavia, se si usa la parola chiave [unsafe](../../language-reference/keywords/unsafe.md), è possibile definire un contesto non sicuro in cui si possono usare i puntatori. Per altre informazioni sui puntatori, vedere [Tipi puntatore](pointer-types.md).  
  
> [!NOTE]
> Nel supporto Common Language Runtime (CLR) il codice di tipo unsafe è detto codice non verificabile. Il codice unsafe in C# non è necessariamente pericoloso, è solo codice di cui il supporto CLR non può verificare la sicurezza. CLR pertanto eseguirà il codice unsafe solo se si trova in un assembly completamente attendibile. Se si usa codice unsafe, è responsabilità dell'utente verificare che il codice non introduca rischi per la sicurezza o errori dei puntatori.  
  
## <a name="unsafe-code-overview"></a>Panoramica del codice non gestito

Il codice unsafe presenta le proprietà seguenti:

- Metodi, tipi e blocchi di codice possono essere definiti come unsafe.

- In alcuni casi il codice unsafe può migliorare le prestazioni di un'applicazione poiché vengono rimosse le verifiche dei limiti di matrice.

- Il codice unsafe è necessario quando si chiamano funzioni native che richiedono i puntatori.

- L'uso del codice unsafe implica rischi per la sicurezza e la stabilità.

- Il codice che contiene blocchi non gestiti deve essere compilato con l'opzione [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) del compilatore.
  
## <a name="related-sections"></a>Sezioni correlate

Per altre informazioni, vedere:

- [Tipi di puntatori](pointer-types.md)

- [Buffer a dimensione fissa](fixed-size-buffers.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere l'argomento [Codice di tipo unsafe](~/_csharplang/spec/unsafe-code.md) nella [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
