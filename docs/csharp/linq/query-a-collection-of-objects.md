---
title: Eseguire query in una raccolta di oggetti
description: Come eseguire una query nelle raccolte.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: c690da2ae59d2a9b34a5bd403bc54797c4e95fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="query-a-collection-of-objects"></a>Eseguire query in una raccolta di oggetti
In questo esempio viene illustrato come eseguire una query semplice su un elenco di oggetti `Student`. Ogni oggetto `Student` contiene informazioni di base sullo studente e un elenco che rappresenta i voti dello studente in quattro esami.  
  
 Questa applicazione viene usata come framework per molti altri esempi di questa sezione che usano la stessa origine dati `students`.  
  
## <a name="example"></a>Esempio  
 La query seguente restituisce gli studenti che hanno ricevuto un punteggio pari o superiore a 90 nel primo esame.  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 Questa query è volutamente semplice per consentire la sperimentazione. Ad esempio, è possibile provare altre condizioni nella clausola `where` oppure usare una clausola `orderby` per ordinare i risultati.  
  

## <a name="see-also"></a>Vedere anche  
 [Espressioni di query LINQ](index.md)  
 [Interpolazione di stringhe](../language-reference/tokens/interpolated.md)
