---
title: Eseguire query in una raccolta di oggetti (LINQ in C#)
description: Informazioni su come eseguire query in una raccolta usando LINQ in C#.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 9b2f5dd09c540800e9a2498d48883357f58c0116
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659813"
---
# <a name="query-a-collection-of-objects"></a>Eseguire query in una raccolta di oggetti

In questo esempio viene illustrato come eseguire una query semplice su un elenco di oggetti `Student`. Ogni oggetto `Student` contiene informazioni di base sullo studente e un elenco che rappresenta i voti dello studente in quattro esami.  
  
Questa applicazione viene usata come framework per molti altri esempi di questa sezione che usano la stessa origine dati `students`.  
  
## <a name="example"></a>Esempio

La query seguente restituisce gli studenti che hanno ricevuto un punteggio pari o superiore a 90 nel primo esame.  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
Questa query è volutamente semplice per consentire la sperimentazione. Ad esempio, è possibile provare altre condizioni nella clausola `where` oppure usare una clausola `orderby` per ordinare i risultati.  
  
## <a name="see-also"></a>Vedere anche

- [Language Integrated Query (LINQ)](index.md)
- [Interpolazione di stringhe](../language-reference/tokens/interpolated.md)
