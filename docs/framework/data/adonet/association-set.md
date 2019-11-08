---
title: set di associazioni
ms.date: 03/30/2017
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
ms.openlocfilehash: e279322f9e950cd4359db8c6dce39bfc46d188f6
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732373"
---
# <a name="association-set"></a>set di associazioni
Un *set di associazioni* è un contenitore logico per le istanze di [associazione](association-type.md) dello stesso tipo. Un set di associazioni non è un costrutto di modellazione dati, ovvero non descrive la struttura di dati o relazioni. Un set di associazioni, invece, fornisce un costrutto per un ambiente host o di archiviazione (ad esempio Common Language Runtime o un database SQL Server) per raggruppare le istanze dell'associazione in modo che se ne possa eseguire il mapping a un archivio dati.  
  
 Un set di associazioni viene definito all'interno di un [contenitore di entità](entity-container.md), ovvero un raggruppamento logico di [set di entità](entity-set.md) e set di associazioni.  
  
 Una definizione per un set di associazioni contiene le informazioni seguenti:  
  
- Il nome del set di associazioni (obbligatorio).  
  
- L'associazione della quale conterrà le istanze (obbligatorio).  
  
- [Termina due set di associazioni](association-set-end.md).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`. Anche se le informazioni sui set di associazioni non sono contenute nel diagramma, nel diagramma successivo viene illustrato un esempio di set di associazioni e di set di entità basato su questo modello.  
  
 ![Modello di esempio con tre tipi di entità](./media/association-set/example-model-three-entity-types.gif)  
  
 Nell'esempio seguente vengono illustrati un set di associazioni (`PublishedBy`) e due set di entità (`Books` e `Publishers`) basati sul modello concettuale illustrato in precedenza. Bi nel set di entità `Books` rappresenta un'istanza del tipo di entità `Book` in fase di esecuzione. Analogamente, PJ rappresenta un'istanza di `Publisher` nel set di entità `Publishers`. BiPj rappresenta un'istanza dell'associazione `PublishedBy` nel set di associazioni `PublishedBy`.  
  
 ![Screenshot che mostra un esempio di set.](./media/association-set/sets-example-association.gif)  
  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce un contenitore di entità con un set di associazioni per ogni associazione nel diagramma precedente. Si noti che il nome e l'associazione per ogni set di associazioni sono definiti tramite attributi XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 È possibile definire più set di associazioni per associazione, purché due set di associazioni non condividano un'entità [finale del set di associazioni](association-set-end.md). Nel linguaggio seguente viene definito un contenitore di entità con due set di associazioni per l'associazione `WrittenBy`. Si noti che più set di entità sono stati definiti per i tipi di entità `Book` e `Author` e che nessun set di associazioni condivide un'entità finale del set di associazioni.  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [proprietà di chiave esterna](foreign-key-property.md)
