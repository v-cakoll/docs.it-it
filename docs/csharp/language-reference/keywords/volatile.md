---
title: volatile (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: be7e081b18702710c00b5b86a9bc152800f0cf3d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526219"
---
# <a name="volatile-c-reference"></a>volatile (Riferimenti per C#)
La parola chiave `volatile` indica che un campo potrebbe essere modificato da più thread eseguiti contemporaneamente. Un campo dichiarato `volatile` non è soggetto a ottimizzazioni del compilatore che presuppongono l'accesso da parte di un singolo thread. Queste limitazioni garantiscono che tutti i thread considereranno scritture di tipo volatile eseguite da altri thread nell'ordine in cui sono stati eseguiti. Non c'è garanzia di un singolo ordinamento totale delle scritture volatili come osservato da tutti i thread di esecuzione.  
  
 Il modificatore `volatile` si usa in genere per un campo a cui accedono più thread senza usare l'istruzione [lock](../../../csharp/language-reference/keywords/lock-statement.md) per serializzare l'accesso.  
  
 La parola chiave `volatile` può essere applicata ai campi di questi tipi:  
  
-   Tipi di riferimento.  
  
-   Tipi di puntatore (in un contesto non sicuro). Si noti che sebbene il puntatore in sé possa essere volatile, non può esserlo l'oggetto a cui punta. In altre parole, non è possibile dichiarare un "puntatore a volatile".  
  
-   Tipi come sbyte, byte, short, ushort, int, uint, char, float e bool.  
  
-   Un tipo enum con uno dei seguenti tipi di base: byte, sbyte, short, ushort, int o uint.  
  
-   Parametri di tipo generico noti come tipi di riferimento.  
  
-   <xref:System.IntPtr> e <xref:System.UIntPtr>.  
  
 La parola chiave volatile può essere applicata solo a campi di una classe o struct. Le variabili locali non possono essere dichiarate `volatile`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrato come dichiarare `volatile` una variabile di campo pubblico.  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come un thread di lavoro o ausiliario può essere creato e usato per eseguire l'elaborazione in parallelo con quella del thread principale. Per informazioni di base sul multithreading, vedere [Managed Threading](../../../standard/threading/index.md) (Threading gestito) e [Threading (C#)](../../programming-guide/concepts/threading/index.md).  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
- [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)
