---
title: Eseguire query in una raccolta di oggetti (LINQ in C#)
description: Informazioni su come eseguire query in una raccolta usando LINQ in C#.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 87c7bbe789c165a6e189231df1979fc264a34dce
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "37403921"
---
# <a name="query-a-collection-of-objects"></a>Eseguire query in una raccolta di oggetti

In questo esempio viene illustrato come eseguire una query semplice su un elenco di oggetti `Student`. Ogni oggetto `Student` contiene informazioni di base sullo studente e un elenco che rappresenta i voti dello studente in quattro esami.  
  
Questa applicazione viene usata come framework per molti altri esempi di questa sezione che usano la stessa origine dati `students`.  
  
## <a name="example"></a>Esempio

La query seguente restituisce gli studenti che hanno ricevuto un punteggio pari o superiore a 90 nel primo esame.  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
Questa query è volutamente semplice per consentire la sperimentazione. Ad esempio, è possibile provare altre condizioni nella clausola `where` oppure usare una clausola `orderby` per ordinare i risultati.  
  
## <a name="see-also"></a>Vedere anche

[LINQ (Language-Integrated Query)](index.md)  
[Interpolazione di stringhe](../language-reference/tokens/interpolated.md)