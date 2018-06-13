---
title: Risoluzione dell'overload di funzioni (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
ms.openlocfilehash: 517bdb682213deff90a37eafcf32946fef63921f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762858"
---
# <a name="function-overload-resolution-entity-sql"></a>Risoluzione dell'overload di funzioni (Entity SQL)
In questo argomento viene descritto come vengono risolte le funzioni [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 È possibile definire più funzioni con lo stesso nome purché le rispettive firme siano univoche.  
  
 In una situazione di questo tipo, è necessario applicare i criteri seguenti per determinare la funzione a cui una determinata espressione fa riferimento. Questi criteri vengono applicati in sequenza. Il primo criterio che si applica solo a un'unica funzione rappresenta la funzione risolta.  
  
1.  **Il parametro numero**. La funzione ha lo stesso numero di parametri specificato nell'espressione.  
  
2.  **Corrispondenza esatta del tipo**. Ogni tipo di argomento della funzione corrisponde esattamente al tipo di parametro o è costituito dal valore letterale Null.  
  
3.  **Corrispondenza del sottotipo**. Ogni tipo di argomento della funzione corrisponde esattamente al tipo di parametro o è un sottotipo del tipo di parametro oppure l'argomento è costituito dal valore letterale Null. Nel caso in cui diverse funzioni differiscano solo nel numero di conversioni dei sottotipi richieste, la funzione con il minor numero di conversioni dei sottotipi è la funzione risolta.  
  
4.  **Corrispondenza del sottotipo o promozione del tipo**. Ogni tipo di argomento della funzione corrisponde esattamente al tipo di parametro o è un sottotipo del tipo di parametro o può essere promosso al tipo di parametro oppure l'argomento è costituito dal valore letterale Null. Anche in questo caso, se diverse funzioni differiscono solo nel numero di promozioni e di conversioni dei sottotipi, la funzione con il minor numero di promozioni e di conversioni dei sottotipi è la funzione risolta.  
  
 Se nessuno di questi criteri consente la selezione di una singola funzione, l'espressione di chiamata della funzione è ambigua.  
  
 Anche nel caso in cui usando queste regole sia possibile estrarre una singola funzione, gli argomenti potrebbero comunque non corrispondere ai parametri. In tal caso, viene generato un errore.  
  
 Per le funzioni definite dall'utente, la definizione per una funzione inline della query ha la precedenza anche in presenza di una funzione definita dal modello con una firma che è una corrispondenza migliore per la funzione definita dall'utente.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Funzioni](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
