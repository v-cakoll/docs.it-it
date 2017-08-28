---
title: "Procedura: concatenare più stringhe (Guida per programmatori C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b191a61258a496115a4d7045046f9b4a2dbee58c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a>Procedura: concatenare più stringhe (Guida per programmatori C#)
La *concatenazione* è il processo di aggiunta di una stringa alla fine di un'altra stringa. Quando si concatenano valori letterali stringa o costanti di stringa usando l'operatore `+`, il compilatore crea una singola stringa. Non viene eseguita alcuna concatenazione in fase di esecuzione. Le variabili di stringa tuttavia possono essere concatenate solo in fase di esecuzione. In questo caso, è necessario comprendere le implicazioni dei vari approcci sulle prestazioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come suddividere un valore letterale stringa lungo in stringhe più piccole, per migliorare la leggibilità nel codice sorgente. Queste parti verranno concatenate in una singola stringa in fase di compilazione. Non c'è alcun impatto sulle prestazioni in fase di esecuzione, indipendentemente dal numero di stringhe coinvolte.  
  
 [!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## <a name="example"></a>Esempio  
 Per concatenare le variabili di stringa, è possibile usare gli operatori `+` o `+=` oppure i metodi <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>. L'operatore `+` è facile da usare e rende il codice intuitivo. Anche se si usano diversi operatori + in un'unica istruzione, il contenuto della stringa viene copiato una sola volta. Se però si ripete l'operazione più volte, ad esempio in un ciclo, potrebbero verificarsi problemi di efficienza. Ad esempio, si noti il codice seguente:  
  
 [!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  Nelle operazioni di concatenazione di stringhe il compilatore C# tratta una stringa Null come se fosse una stringa vuota, ma non converte il valore della stringa Null originale.  
  
 Se non si deve concatenare un elevato numero di stringhe (ad esempio, in un ciclo), il costo in termini di prestazioni di questo codice è probabilmente poco rilevante. Lo stesso vale per i metodi <xref:System.String.Concat%2A?displayProperty=fullName> e <xref:System.String.Format%2A?displayProperty=fullName>.  
  
 Tuttavia, quando le prestazioni sono importanti, è sempre opportuno usare la classe <xref:System.Text.StringBuilder> per concatenare le stringhe. Il codice seguente usa il metodo <xref:System.Text.StringBuilder.Append%2A> della classe <xref:System.Text.StringBuilder> per concatenare le stringhe senza l'effetto di concatenazione dell'operatore `+`.  
  
 [!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.String>   
 <xref:System.Text.StringBuilder>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Stringhe](../../../csharp/programming-guide/strings/index.md)

