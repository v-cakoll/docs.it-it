---
title: "Procedura: concatenare più stringhe (Guida per programmatori C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca240523e2483289e11433fd58d9630a31721b33
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a>Procedura: concatenare più stringhe (Guida per programmatori C#)
La *concatenazione* è il processo di aggiunta di una stringa alla fine di un'altra stringa. Quando si concatenano valori letterali stringa o costanti di stringa usando l'operatore `+`, il compilatore crea una singola stringa. Non viene eseguita alcuna concatenazione in fase di esecuzione. Le variabili di stringa tuttavia possono essere concatenate solo in fase di esecuzione. In questo caso, è necessario comprendere le implicazioni dei vari approcci sulle prestazioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come suddividere un valore letterale stringa lungo in stringhe più piccole, per migliorare la leggibilità nel codice sorgente. Queste parti verranno concatenate in una singola stringa in fase di compilazione. Non c'è alcun impatto sulle prestazioni in fase di esecuzione, indipendentemente dal numero di stringhe coinvolte.  
  
 [!code-csharp[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## <a name="example"></a>Esempio  
 Per concatenare le variabili di stringa, è possibile usare gli operatori `+` o `+=` oppure i metodi <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>. L'operatore `+` è facile da usare e rende il codice intuitivo. Anche se si usano diversi operatori + in un'unica istruzione, il contenuto della stringa viene copiato una sola volta. Se però si ripete l'operazione più volte, ad esempio in un ciclo, potrebbero verificarsi problemi di efficienza. Ad esempio, si noti il codice seguente:  
  
 [!code-csharp[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  Nelle operazioni di concatenazione di stringhe il compilatore C# tratta una stringa Null come se fosse una stringa vuota, ma non converte il valore della stringa Null originale.  
  
 Se non si deve concatenare un elevato numero di stringhe (ad esempio, in un ciclo), il costo in termini di prestazioni di questo codice è probabilmente poco rilevante. Lo stesso vale per i metodi <xref:System.String.Concat%2A?displayProperty=nameWithType> e <xref:System.String.Format%2A?displayProperty=nameWithType>.  
  
 Tuttavia, quando le prestazioni sono importanti, è sempre opportuno usare la classe <xref:System.Text.StringBuilder> per concatenare le stringhe. Il codice seguente usa il metodo <xref:System.Text.StringBuilder.Append%2A> della classe <xref:System.Text.StringBuilder> per concatenare le stringhe senza l'effetto di concatenazione dell'operatore `+`.  
  
 [!code-csharp[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Stringhe](../../../csharp/programming-guide/strings/index.md)
