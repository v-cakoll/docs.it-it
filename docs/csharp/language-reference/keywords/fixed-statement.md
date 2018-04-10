---
title: Istruzione fixed (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 13633e71c863b075eede41c9a18419d65350bdb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-statement-c-reference"></a>Istruzione fixed (Riferimenti per C#)
L'istruzione `fixed` impedisce che il Garbage Collector esegua la rilocazione di una variabile mobile. L'istruzione `fixed` è consentita solo in un contesto di tipo [unsafe](../../../csharp/language-reference/keywords/unsafe.md). È possibile usare `Fixed` anche per creare [buffer a dimensione fissa](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).  
  
 L'istruzione `fixed` imposta un puntatore a una variabile gestita e la blocca durante l'esecuzione dell'istruzione. Senza `fixed`, i puntatori alle variabili gestite mobili risulterebbero poco utili poiché il Garbage Collection potrebbe eseguire una rilocazione delle variabili in modo imprevisto. Il compilatore C# consente di assegnare un puntatore a una variabile gestita in un'istruzione `fixed`.  
  
 [!code-csharp[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 È possibile inizializzare un puntatore usando una matrice, una stringa, un buffer a dimensione fissa o l'indirizzo di una variabile. Nell'esempio seguente viene illustrato l'uso di indirizzi, matrici e stringhe di una variabile. Per altre informazioni sui buffer a dimensione fissa, vedere [Buffer a dimensione fissa](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).  
  
 [!code-csharp[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 È possibile inizializzare più puntatori, purché siano tutti dello stesso tipo.  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 Per inizializzare puntatori di tipi diversi, annidare semplicemente le istruzioni `fixed` come illustrato nell'esempio seguente.  
  
 [!code-csharp[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 Dopo aver eseguito il codice nell'istruzione, le variabili bloccate vengono sbloccate e sottoposte al Garbage Collection. Di conseguenza, evitare di puntare alle variabili esterne all'istruzione `fixed`.  
  
> [!NOTE]
>  I puntatori inizializzati nelle istruzioni fixed non possono essere modificati.  
  
 Nella modalità di tipo unsafe è possibile allocare la memoria nello stack, che non è necessario bloccare perché non viene sottoposto al Garbage Collection. Per altre informazioni, vedere [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [Buffer a dimensione fissa](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
