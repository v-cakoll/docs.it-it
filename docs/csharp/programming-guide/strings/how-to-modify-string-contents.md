---
title: 'Procedura: modificare il contenuto delle stringhe (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b0810d5722c2c32f7884187bb2e3fc5a039825c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-string-contents-c-programming-guide"></a>Procedura: modificare il contenuto delle stringhe (Guida per programmatori C#)
Poiché le stringhe sono *non modificabili*, non è possibile (senza usare codice unsafe) modificare il valore di un oggetto stringa dopo che è stato creato. Ci sono tuttavia molti modi per modificare il valore di una stringa e archiviare il risultato in un nuovo oggetto stringa. La classe <xref:System.String?displayProperty=nameWithType> fornisce metodi che operano su una stringa di input e restituiscono un nuovo oggetto stringa. In molti casi, è possibile assegnare il nuovo oggetto alla variabile che conteneva la stringa originale. La classe <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> fornisce metodi aggiuntivi che funzionano in modo simile. La classe <xref:System.Text.StringBuilder?displayProperty=nameWithType> fornisce un buffer di caratteri che è possibile modificare "sul posto". Chiamare il metodo <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> per creare un nuovo oggetto stringa che include il contenuto corrente del buffer.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra vari modi per sostituire o rimuovere sottostringhe in una stringa specifica.  
  
 [!code-csharp[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]  
  
## <a name="example"></a>Esempio  
 Per accedere ai singoli caratteri in una stringa tramite una notazione di matrice, è possibile usare l'oggetto <xref:System.Text.StringBuilder>, che esegue l'overload dell'operatore `[]` per fornire l'accesso al buffer di caratteri interno. È anche possibile convertire la stringa in una matrice di caratteri tramite il metodo <xref:System.String.ToCharArray%2A>. L'esempio seguente usa `ToCharArray` per creare la matrice. Alcuni elementi della matrice vengono quindi modificati. Viene quindi chiamato un costruttore di stringhe che accetta una matrice di caratteri come parametro di input per creare una nuova stringa.  
  
 [!code-csharp[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente viene fornito per quelle situazioni molto rare in cui si potrebbe volere modificare una stringa sul posto usando codice unsafe, in modo simile alle matrici di caratteri di tipo C. L'esempio mostra come accedere ai singoli caratteri "sul posto" usando la parola chiave fixed. Mostra anche un possibile effetto collaterale delle operazioni con codice unsafe sulle stringhe, legato al modo in cui il compilatore C# archivia (inserisce) le stringhe internamente. In generale, non è consigliabile usare questa tecnica a meno che non sia assolutamente necessario.  
  
 [!code-csharp[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Stringhe](../../../csharp/programming-guide/strings/index.md)
