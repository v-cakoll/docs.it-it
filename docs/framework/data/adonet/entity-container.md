---
title: contenitore di entità
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 58642c6cc794f931387ac7a76dd64d368957f14b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586952"
---
# <a name="entity-container"></a>contenitore di entità
Un' *contenitore di entità* è un raggruppamento logico delle [i set di entità](../../../../docs/framework/data/adonet/entity-set.md), [set di associazioni](../../../../docs/framework/data/adonet/association-set.md), e [funzione importazioni](../../../../docs/framework/data/adonet/model-declared-function.md).  
  
 Le affermazioni seguenti relative a un contenitore di entità definito in un modello concettuale devono essere vere:  
  
- In ogni modello concettuale deve essere definito almeno un contenitore di entità.  
  
- Il contenitore di entità deve disporre di un nome univoco all'interno di ogni modello concettuale.  
  
 Un contenitore di entità può definire set di entità o set di associazioni che usano i tipi o le associazioni di entità definite in uno o più spazi dei nomi. Per altre informazioni, vedere [Entity Data Model: Gli spazi dei nomi](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.  Per altre informazioni, vedere l'esempio successivo.  
  
 ![Modello di esempio con tre tipi di entità](./media/entity-container/example-model-three-entity-types.gif)  
  
 Anche se nel diagramma non sono contenute informazioni sul contenitore di entità, il modello concettuale deve definire un contenitore di entità. Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio DSL denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce un contenitore di entità per il modello concettuale illustrato nel diagramma precedente. Si noti che il nome del contenitore di entità è definito in un attributo XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
