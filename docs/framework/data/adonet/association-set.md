---
title: set di associazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db293cbc636d0ae4e532f24b2852444395f603c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="association-set"></a>set di associazioni
Un *set di associazioni* è un contenitore logico per [associazione](../../../../docs/framework/data/adonet/association-type.md) istanze dello stesso tipo. Un set di associazioni non è un costrutto di modellazione dati, ovvero non descrive la struttura di dati o relazioni. Un set di associazioni, invece, fornisce un costrutto per un ambiente host o di archiviazione (ad esempio Common Language Runtime o un database SQL Server) per raggruppare le istanze dell'associazione in modo che se ne possa eseguire il mapping a un archivio dati.  
  
 Un set di associazioni è definito all'interno di un [contenitore di entità](../../../../docs/framework/data/adonet/entity-container.md), ovvero un raggruppamento logico di [set di entità](../../../../docs/framework/data/adonet/entity-set.md) e set di associazioni.  
  
 Una definizione per un set di associazioni contiene le informazioni seguenti:  
  
-   Il nome del set di associazioni (obbligatorio).  
  
-   L'associazione della quale conterrà le istanze (obbligatorio).  
  
-   Due [estremità del set di associazioni](../../../../docs/framework/data/adonet/association-set-end.md).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`. Anche se le informazioni sui set di associazioni non sono contenute nel diagramma, nel diagramma successivo viene illustrato un esempio di set di associazioni e di set di entità basato su questo modello.  
  
 ![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Nell'esempio seguente vengono illustrati un set di associazioni (`PublishedBy`) e due set di entità (`Books` e `Publishers`) basati sul modello concettuale illustrato in precedenza. Business Intelligence nel `Books` set di entità rappresenta un'istanza del `Book` il tipo di entità in fase di esecuzione. Analogamente, Pj rappresenta un `Publisher` dell'istanza nel `Publishers` set di entità. BiPj rappresenta un'istanza di `PublishedBy` associazione nel `PublishedBy` set di associazioni.  
  
 ![Esempio](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce un contenitore di entità con un set di associazioni per ogni associazione nel diagramma precedente. Si noti che il nome e l'associazione per ogni set di associazioni sono definiti tramite attributi XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 È possibile definire più set di associazioni per l'associazione, purché Nessuna condivisione di set di due entità un [fine del set di associazioni](../../../../docs/framework/data/adonet/association-set-end.md). Nel linguaggio seguente viene definito un contenitore di entità con due set di associazioni per l'associazione `WrittenBy`. Si noti che più set di entità sono stati definiti per i tipi di entità `Book` e `Author` e che nessun set di associazioni condivide un'entità finale del set di associazioni.  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [proprietà di chiave esterna](../../../../docs/framework/data/adonet/foreign-key-property.md)
