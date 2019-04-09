---
title: set di entità
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: 7fcaa2cb9bac02271940a712d4d044df25d7d4cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126620"
---
# <a name="entity-set"></a>set di entità
Un' *set di entità* è un contenitore logico per istanze di un [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) e le istanze di qualsiasi tipo derivato da tale tipo di entità. (Per informazioni sui tipi derivati, vedere [Entity Data Model: Ereditarietà](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).) La relazione tra un tipo di entità e un set di entità è analoga alla relazione tra una riga e una tabella in un database relazionale: Analogamente a una riga, un tipo di entità descrive la struttura dei dati e, analogamente a una tabella, un set di entità contiene istanze di una determinata struttura. Un set di entità non è un costrutto di modellazione dati e non descrive la struttura di dati. Un set di entità, invece, fornisce un costrutto per un ambiente host o di archiviazione (ad esempio Common Language Runtime o un database SQL Server) per raggruppare le istanze del tipo di entità in modo che se ne possa eseguire il mapping a un archivio dati.  
  
 Un set di entità è definito all'interno di un' [contenitore di entità](../../../../docs/framework/data/adonet/entity-container.md), ovvero un raggruppamento logico di set di entità e [set di associazioni](../../../../docs/framework/data/adonet/association-set.md).  
  
 Perché un'istanza di un tipo di entità esista in un set di entità, devono essere osservate le seguenti condizioni:  
  
-   Il tipo dell'istanza è lo stesso del tipo di entità su cui si basa il set di entità oppure il tipo dell'istanza è un sottotipo del tipo di entità.  
  
-   Il [chiave di entità](../../../../docs/framework/data/adonet/entity-key.md) per l'istanza è univoco all'interno del set di entità.  
  
-   L'istanza non esiste in nessun altro set di entità.  
  
    > [!NOTE]
    >  È possibile definire più set di entità tramite lo stesso tipo di entità, ma un'istanza di un determinato tipo di entità può esistere in un solo set di entità.  
  
 Non è necessario definire un set di entità per ogni tipo di entità in un modello concettuale.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.  
  
 ![Modello di esempio con tre tipi di entità](./media/entity-set/example-model-three-entity-types.gif)  
  
 Nel diagramma seguente vengono illustrati due set di entità (`Books` e `Publishers`) e un set di associazioni (`PublishedBy`) basati sul modello concettuale illustrato in precedenza. Business Intelligence nel `Books` set di entità rappresenta un'istanza del `Book` tipo di entità in fase di esecuzione. Analogamente, Pj rappresentano un `Publisher` dell'istanza nel `Publishers` set di entità. BiPj rappresenta un'istanza del `PublishedBy` association nel `PublishedBy` set di associazioni.  
  
 ![Screenshot che mostra un esempio di set.](./media/entity-set/sets-example-association.gif)  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce un contenitore di entità con un set di entità per ogni tipo di entità nel modello concettuale illustrato in precedenza. Si noti che il nome e il tipo di entità per ogni set di entità sono definiti tramite attributi XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 È possibile definire più set di entità per tipo (MEST). Il linguaggio CSDL seguente definisce un contenitore di entità con due set di entità per il tipo di entità `Book`:  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
