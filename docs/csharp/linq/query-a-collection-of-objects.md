---
title: Eseguire query in una raccolta di oggetti
description: Come eseguire una query nelle raccolte.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 74d6c1f080c3e70867f5d2f074315bd1d8486bf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 [Stringhe interpolate](../language-reference/keywords/interpolated-strings.md)
