---
title: tipo di entità
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 026b0aef7cf2de8fe222721191afa459859701ee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108264"
---
# <a name="entity-type"></a>tipo di entità
Il *tipo di entità* è il blocco predefinito fondamentale per descrivere la struttura dei dati con Entity Data Model (EDM). In un modello concettuale, un tipo di entità rappresenta la struttura di concetti di livello superiore, quale ad esempio clienti o ordini. Un tipo di entità è un modello per le istanze del tipo di entità. Ogni modello contiene le informazioni seguenti:  
  
-   Un nome univoco. Obbligatorio.  
  
-   Un' [chiave di entità](../../../../docs/framework/data/adonet/entity-key.md) definito da una o più proprietà. Obbligatorio.  
  
-   I dati nel formato [proprietà](../../../../docs/framework/data/adonet/property.md). (Facoltative)  
  
-   [Le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) che consentono di navigare da un' [finali](../../../../docs/framework/data/adonet/association-end.md) di un [associazione](../../../../docs/framework/data/adonet/association-type.md) su altra estremità. (facoltativo)  
  
 In un'applicazione, un'istanza di un tipo di entità rappresenta un oggetto specifico, quale ad esempio un cliente o un ordine specifico. Ogni istanza di un tipo di entità deve avere un valore univoco [chiave di entità](../../../../docs/framework/data/adonet/entity-key.md) all'interno di un' [set di entità](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Due istanze di tipi di entità sono considerate uguali solo se sono dello stesso tipo e se i valori delle rispettive chiavi di entità sono uguali.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`:  
  
 ![Modello di esempio con tre tipi di entità](./media/entity-type/example-model-three-entity-types.gif)  
  
 Si noti che le proprietà di ogni tipo di entità che costituiscono la chiave di entità vengono indicate con "(Key)".  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce il tipo di entità `Book` illustrato nel diagramma precedente:  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
- [facet](../../../../docs/framework/data/adonet/facet.md)
