---
title: entità finale del set di associazioni
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 48ba84d46e380462405551cc2d826d84368b351a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786939"
---
# <a name="association-set-end"></a>entità finale del set di associazioni
Un'entità *finale del set di associazioni* identifica il tipo di [entità](entity-type.md) e il [set di entità](entity-set.md) alla fine di un set di [associazioni](association-set.md). Le entità finali del set di associazioni sono definite come parte di un set di associazioni. Un set di associazioni deve disporre esattamente di due entità finali.  
  
 Una definizione di entità finale del set di associazioni contiene le informazioni seguenti:  
  
- Uno dei tipi di entità coinvolti nel set di associazioni (obbligatorio).  
  
- Il set di entità per il tipo di entità coinvolto nel set di associazioni (obbligatorio).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `WrittenBy` e `PublishedBy`.  
  
 ![Modello di esempio con tre tipi di entità](./media/association-set-end/example-model-three-entity-types.gif)  
  
 Nel diagramma seguente vengono illustrati un set di associazioni (`PublishedBy`) e due set di entità (`Books` e `Publishers`) basati sul modello concettuale illustrato in precedenza. Le fini del set di associazioni sono i set di entità `Books` e `Publishers`. Bi nel set `Books` di entità rappresenta un'istanza `Book` del tipo di entità in fase di esecuzione. Analogamente, PJ rappresenta `Publisher` un'istanza `Publishers` nel set di entità. BiPj rappresenta un'istanza dell' `PublishedBy` associazione `PublishedBy` nel set di associazioni.  
  
 ![Screenshot che mostra un esempio di set.](./media/association-set-end/sets-example-association.gif)  
  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio DSL denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce un contenitore di entità con un set di associazioni per ogni associazione nel diagramma precedente. Si noti che le entità finali del set di associazioni sono definite come parte di ogni definizione di set di associazioni.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
