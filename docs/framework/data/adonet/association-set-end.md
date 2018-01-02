---
title: "entità finale del set di associazioni"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ddb7dc758de8d40a2c80a09f93d44600b7c75b56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="association-set-end"></a>entità finale del set di associazioni
Un *fine del set di associazioni* identifica il [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) e [set di entità](../../../../docs/framework/data/adonet/entity-set.md) alla fine di un [set di associazioni](../../../../docs/framework/data/adonet/association-set.md). Le entità finali del set di associazioni sono definite come parte di un set di associazioni. Un set di associazioni deve disporre esattamente di due entità finali.  
  
 Una definizione di entità finale del set di associazioni contiene le informazioni seguenti:  
  
-   Uno dei tipi di entità coinvolti nel set di associazioni (obbligatorio).  
  
-   Il set di entità per il tipo di entità coinvolto nel set di associazioni (obbligatorio).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `WrittenBy` e `PublishedBy`.  
  
 ![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Nel diagramma seguente vengono illustrati un set di associazioni (`PublishedBy`) e due set di entità (`Books` e `Publishers`) basati sul modello concettuale illustrato in precedenza. Le fini del set di associazioni sono i set di entità `Books` e `Publishers`. Business Intelligence nel `Books` set di entità rappresenta un'istanza del `Book` il tipo di entità in fase di esecuzione. Analogamente, Pj rappresenta un `Publisher` dell'istanza nel `Publishers` set di entità. BiPj rappresenta un'istanza di `PublishedBy` associazione nel `PublishedBy` set di associazioni.  
  
 ![Esempio](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio DSL detto linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce un contenitore di entità con un set di associazioni per ogni associazione nel diagramma precedente. Si noti che le entità finali del set di associazioni sono definite come parte di ogni definizione di set di associazioni.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
