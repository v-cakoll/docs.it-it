---
title: set di entità
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: b74d6bf373925ac90a998e2c4425c053e533f82a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784000"
---
# <a name="entity-set"></a>set di entità
Un *set di entità* è un contenitore logico per istanze di un [tipo di entità](entity-type.md) e istanze di qualsiasi tipo derivato da tale tipo di entità. Per informazioni sui tipi derivati, [vedere Entity Data Model: Ereditarietà](entity-data-model-inheritance.md).) La relazione tra un tipo di entità e un set di entità è analoga alla relazione tra una riga e una tabella in un database relazionale: Analogamente a una riga, un tipo di entità descrive la struttura dei dati e, come una tabella, un set di entità contiene istanze di una determinata struttura. Un set di entità non è un costrutto di modellazione dati e non descrive la struttura di dati. Un set di entità, invece, fornisce un costrutto per un ambiente host o di archiviazione (ad esempio Common Language Runtime o un database SQL Server) per raggruppare le istanze del tipo di entità in modo che se ne possa eseguire il mapping a un archivio dati.  
  
 Un set di entità viene definito all'interno di un [contenitore di entità](entity-container.md), ovvero un raggruppamento logico di set di entità e [set di associazioni](association-set.md).  
  
 Perché un'istanza di un tipo di entità esista in un set di entità, devono essere osservate le seguenti condizioni:  
  
- Il tipo dell'istanza è lo stesso del tipo di entità su cui si basa il set di entità oppure il tipo dell'istanza è un sottotipo del tipo di entità.  
  
- La [chiave di entità](entity-key.md) per l'istanza è univoca all'interno del set di entità.  
  
- L'istanza non esiste in nessun altro set di entità.  
  
    > [!NOTE]
    > È possibile definire più set di entità tramite lo stesso tipo di entità, ma un'istanza di un determinato tipo di entità può esistere in un solo set di entità.  
  
 Non è necessario definire un set di entità per ogni tipo di entità in un modello concettuale.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.  
  
 ![Modello di esempio con tre tipi di entità](./media/entity-set/example-model-three-entity-types.gif)  
  
 Nel diagramma seguente vengono illustrati due set di entità (`Books` e `Publishers`) e un set di associazioni (`PublishedBy`) basati sul modello concettuale illustrato in precedenza. Bi nel set `Books` di entità rappresenta un'istanza `Book` del tipo di entità in fase di esecuzione. Analogamente, PJ rappresenta `Publisher` un'istanza `Publishers` nel set di entità. BiPj rappresenta un'istanza dell' `PublishedBy` associazione `PublishedBy` nel set di associazioni.  
  
 ![Screenshot che mostra un esempio di set.](./media/entity-set/sets-example-association.gif)  
  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce un contenitore di entità con un set di entità per ogni tipo di entità nel modello concettuale illustrato in precedenza. Si noti che il nome e il tipo di entità per ogni set di entità sono definiti tramite attributi XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 È possibile definire più set di entità per tipo (MEST). Il linguaggio CSDL seguente definisce un contenitore di entità con due set di entità per il tipo di entità `Book`:  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
