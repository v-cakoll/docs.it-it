---
title: Istruzione lock (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb48c2b1554ad2817406eaef42b4cb336ea46862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lock-statement-c-reference"></a>Istruzione lock (Riferimenti per C#)
La parola chiave `lock` contrassegna un blocco di istruzioni come sezione critica ottenendo il blocco a esclusione reciproca per un determinato oggetto, eseguendo un'istruzione e rilasciando in seguito il blocco. L'esempio seguente illustra un'istruzione `lock`.  
  
```csharp  
class Account  
{  
    decimal balance;  
    private Object thisLock = new Object();  
  
    public void Withdraw(decimal amount)  
    {  
        lock (thisLock)  
        {  
            if (amount > balance)  
            {  
                throw new Exception("Insufficient funds");  
            }  
            balance -= amount;  
        }  
    }  
}  
```  
  
 Per altre informazioni, vedere [Sincronizzazione di thread](../../programming-guide/concepts/threading/thread-synchronization.md).  
  
## <a name="remarks"></a>Note  
 La parola chiave `lock` impedisce a un thread di entrare in una sezione critica del codice se è già presente un altro thread. Se un altro thread tenta di accedere a un codice bloccato, attenderà (in stato di blocco) finché l'oggetto non verrà rilasciato.  
  
 Nella sezione [Threading](../../programming-guide/concepts/threading/index.md) vengono specificate informazioni sul threading.  
  
 La parola chiave `lock` chiama <xref:System.Threading.Monitor.Enter%2A> all'inizio del blocco e <xref:System.Threading.Monitor.Exit%2A> alla fine del blocco. Viene generata un'eccezione <xref:System.Threading.ThreadInterruptedException> se <xref:System.Threading.Thread.Interrupt%2A> interrompe un thread in attesa di immettere un'istruzione `lock`.  
  
 In generale è opportuno evitare il blocco su un tipo `public` o su istanze oltre il controllo del codice. I costrutti comuni `lock (this)`, `lock (typeof (MyType))` e `lock ("myLock")` non rispettano questa regola:  
  
-   `lock (this)` costituisce un problema se l'accesso all'istanza può avvenire pubblicamente.  
  
-   `lock (typeof (MyType))` costituisce un problema se l'accesso a `MyType` può avvenire pubblicamente.  
  
-   `lock("myLock")` costituisce un problema poiché qualsiasi altro codice nel processo che usa la stessa stringa condividerà lo stesso blocco.  
  
 La procedura consigliata consiste nel definire un oggetto `private` da bloccare o una variabile oggetto `private static` per proteggere i dati comuni a tutte le istanze.  
  
 Non è possibile usare la parola chiave [await](../../../csharp/language-reference/keywords/await.md) nel corpo di un'istruzione `lock`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un uso semplificato dei thread senza blocco in C#.  
  
 [!code-csharp[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito vengono usati thread e `lock`. Finché è presente l'istruzione `lock`, il blocco di istruzioni rimarrà una sezione critica e `balance` non diventerà mai un numero negativo.  
  
 [!code-csharp[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Reflection.MethodImplAttributes>  
 <xref:System.Threading.Mutex>  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Threading](../../programming-guide/concepts/threading/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Parole chiave per le istruzioni](../../../csharp/language-reference/keywords/statement-keywords.md)  
 <xref:System.Threading.Monitor>  
 [Operazioni interlocked](../../../standard/threading/interlocked-operations.md)  
 [AutoResetEvent](../../../standard/threading/autoresetevent.md)  
 [Sincronizzazione di thread](../../programming-guide/concepts/threading/thread-synchronization.md)
