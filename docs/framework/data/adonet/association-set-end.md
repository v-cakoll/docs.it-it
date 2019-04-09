---
title: entità finale del set di associazioni
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 7b6c646592c1878ea30396d98b4976dc8fa0be12
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134628"
---
# <a name="association-set-end"></a>entità finale del set di associazioni
Un *fine del set di associazioni* identifica le [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) e il [set di entità](../../../../docs/framework/data/adonet/entity-set.md) alla fine di un [set di associazioni](../../../../docs/framework/data/adonet/association-set.md). Le entità finali del set di associazioni sono definite come parte di un set di associazioni. Un set di associazioni deve disporre esattamente di due entità finali.  
  
 Una definizione di entità finale del set di associazioni contiene le informazioni seguenti:  
  
-   Uno dei tipi di entità coinvolti nel set di associazioni (obbligatorio).  
  
-   Il set di entità per il tipo di entità coinvolto nel set di associazioni (obbligatorio).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `WrittenBy` e `PublishedBy`.  
  
 ![Modello di esempio con tre tipi di entità](./media/association-set-end/example-model-three-entity-types.gif)  
  
 Nel diagramma seguente vengono illustrati un set di associazioni (`PublishedBy`) e due set di entità (`Books` e `Publishers`) basati sul modello concettuale illustrato in precedenza. Le fini del set di associazioni sono i set di entità `Books` e `Publishers`. Business Intelligence nel `Books` set di entità rappresenta un'istanza del `Book` tipo di entità in fase di esecuzione. Analogamente, Pj rappresenta un `Publisher` dell'istanza nel `Publishers` set di entità. BiPj rappresenta un'istanza del `PublishedBy` association nel `PublishedBy` set di associazioni.  
  
 ![Screenshot che mostra un esempio di set.](./media/association-set-end/sets-example-association.gif)  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio DSL denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce un contenitore di entità con un set di associazioni per ogni associazione nel diagramma precedente. Si noti che le entità finali del set di associazioni sono definite come parte di ogni definizione di set di associazioni.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
