---
title: funzione definita dal modello
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 1418eccecea647204620455969696c6390bd4a18
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783612"
---
# <a name="model-defined-function"></a>funzione definita dal modello
Una *funzione definita dal modello* è una funzione definita in un modello concettuale. Il corpo di una funzione definita dal modello è espresso in [Entity SQL](./ef/language-reference/entity-sql-language.md), che consente di esprimere la funzione indipendentemente dalle regole o dai linguaggi supportati nell'origine dati.  
  
 Una definizione per una funzione definita dal modello contiene le informazioni seguenti:  
  
- Un nome di funzione (obbligatorio).  
  
- Il tipo del valore restituito (facoltativo)  
  
    > [!NOTE]
    > Se non viene specificato alcun tipo restituito, il valore restituito sarà void.  
  
- Informazioni sui parametri (facoltativo)  
  
- Espressione [Entity SQL](./ef/language-reference/entity-sql-language.md) che definisce il corpo della funzione.  
  
 Si noti che le funzioni definite dal modello non supportano parametri di output. Questa restrizione esiste perché possano essere create funzioni definite dal modello.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.  
  
 ![Screenshot che mostra un modello con data di pubblicazione.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel seguente linguaggio CSDL viene definita una funzione nel modello concettuale che restituisce i numeri di anni da quando è stata pubblicata un'istanza di un `Book` (nel diagramma precedente).  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [Entity Data Model: Tipi di dati primitivi](entity-data-model-primitive-data-types.md)
