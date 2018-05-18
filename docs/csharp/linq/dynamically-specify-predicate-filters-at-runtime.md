---
title: Specificare dinamicamente i filtri dei predicati in fase di esecuzione
description: 'Procedura: specificare dinamicamente i filtri dei predicati in fase di esecuzione.'
ms.date: 12/1/2016
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: fa3426a513758d8c30bf381ec480b9b8d12a5f81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a>Specificare dinamicamente i filtri dei predicati in fase di esecuzione

In alcuni casi, fino alla fase di esecuzione non si sa quanti predicati è necessario applicare agli elementi di origine nella clausola `where`. Un modo per specificare dinamicamente più filtri di predicato consiste nell'usare il metodo <xref:System.Linq.Enumerable.Contains%2A>, come illustrato nell'esempio seguente. L'esempio si costruisce in due modi. Innanzitutto viene eseguito il progetto applicando filtri basati sui valori forniti nel programma. Il progetto viene quindi eseguito di nuovo usando l'input fornito in fase di esecuzione.  
  
## <a name="to-filter-by-using-the-contains-method"></a>Per applicare un filtro usando il metodo Contains  
  
1.  Aprire una nuova applicazione console e denominarla `PredicateFilters`.  
  
2.  Copiare la classe `StudentClass` da [Eseguire query in una raccolta di oggetti](query-a-collection-of-objects.md) e incollarla nello spazio dei nomi `PredicateFilters` sotto la classe `Program`. `StudentClass` fornisce un elenco di oggetti `Student`.  
  
3.  Impostare il metodo `Main` come commento in `StudentClass`.  
  
4.  Sostituire la classe `Program` con il codice seguente.  
  
     [!code-csharp[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  Aggiungere la riga seguente al metodo `Main` nella classe `DynamicPredicates`, sotto la dichiarazione di `ids`.  
  
     ```csharp
     QueryById(ids);
     ```

6.  Eseguire il progetto.  
  
7.  Nella finestra della console verrà visualizzato l'output seguente:  
  
     Garcia: 114  
  
     O'Donnell: 112  
  
     Omelchenko: 111  
  
8.  Il passaggio successivo consiste nell'eseguire nuovamente il progetto, questa volta usando l'input immesso in fase di esecuzione anziché la matrice `ids`. Cambiare `QueryByID(ids)` in `QueryByID(args)` nel metodo `Main`.  
  
9. Eseguire il progetto con gli argomenti della riga di comando `122 117 120 115`. Quando il progetto viene eseguito, questi valori diventano elementi di `args`, il parametro del metodo `Main`.  
  
10. Nella finestra della console verrà visualizzato l'output seguente:  
  
     Adams: 120  
  
     Feng: 117  
  
     Garcia: 115  
  
     Tucker: 122  
  
## <a name="to-filter-by-using-a-switch-statement"></a>Per filtrare tramite un'istruzione switch  
  
1.  È possibile usare un'istruzione `switch` per scegliere tra query alternative predefinite. Nell'esempio seguente `studentQuery` usa una clausola `where` diversa a seconda di quale livello o anno viene specificato in fase di esecuzione.  
  
2.  Copiare il metodo seguente e incollarlo nella classe `DynamicPredicates`.  
  
     [!code-csharp[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  Nel metodo `Main` sostituire la chiamata di `QueryByID` con la chiamata seguente che invia il primo elemento dalla matrice `args` come suo argomento: `QueryByYear(args[0])`.  
  
4.  Eseguire il progetto usando come argomento della riga di comando un valore intero compreso tra 1 e 4.  
  
 
## <a name="see-also"></a>Vedere anche  
 [Espressioni di query LINQ](index.md)  
 [Clausola where](../language-reference/keywords/where-clause.md)
