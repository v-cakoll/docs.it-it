---
title: Come eseguire il codice di pulitura usando C# infine la guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: 00cc7e40220397f4154de5be1e78a894e37374e8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346266"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a>Come eseguire il codice di pulizia con finally (C# guida per programmatori)
Lo scopo di un'istruzione `finally` consiste nel garantire che la pulizia necessaria di oggetti, in genere oggetti che contengono risorse esterne, venga eseguita immediatamente, anche se viene generata un'eccezione. Un esempio di questo tipo di pulizia è la chiamata di <xref:System.IO.Stream.Close%2A> in un oggetto <xref:System.IO.FileStream> immediatamente dopo l'uso, invece di aspettare che l'oggetto venga sottoposto a Garbage Collection da Common Language Runtime, come illustrato di seguito:  
  
 [!code-csharp[csProgGuideExceptions#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#16)]  
  
## <a name="example"></a>Esempio  
 Per trasformare il codice precedente in un'istruzione `try-catch-finally`, il codice di pulitura viene separato dal codice di lavoro, come indicato di seguito.  
  
 [!code-csharp[csProgGuideExceptions#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#17)]  
  
 Poiché può verificarsi un'eccezione in qualsiasi momento all'interno del blocco `try` prima della chiamata a `OpenWrite()`, oppure la chiamata a `OpenWrite()` stessa potrebbe non riuscire, non esiste alcuna garanzia che il file sia aperto quando si tenta di chiuderlo. Il blocco `finally` aggiunge un controllo per verificare che l'oggetto <xref:System.IO.FileStream> non sia `null` prima di chiamare il metodo <xref:System.IO.Stream.Close%2A>. Senza il controllo di `null`, il blocco `finally` potrebbe generare la propria eccezione <xref:System.NullReferenceException>, ma la generazione di eccezioni nei blocchi `finally` deve essere evitata, se possibile.  
  
 Una connessione di database è un altro elemento ideale da chiudere in un blocco `finally`. Poiché il numero di connessioni consentite in un server di database è talvolta limitato, è necessario chiudere le connessioni di database il più rapidamente possibile. Se viene generata un'eccezione prima che la connessione venga chiusa, l'uso del blocco `finally` è preferibile rispetto all'attesa di Garbage Collection.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Eccezioni e gestione delle eccezioni](./index.md)
- [Gestione delle eccezioni](./exception-handling.md)
- [Istruzione using](../../language-reference/keywords/using-statement.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
