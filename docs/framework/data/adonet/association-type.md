---
title: tipo di associazione
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 895d7fdc464741723322717c3ace027dc49eed9c
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411447"
---
# <a name="association-type"></a>tipo di associazione
Un' *tipo di associazione* (detto anche associazione) è il blocco predefinito fondamentale per la descrizione delle relazioni in Entity Data Model (EDM). In un modello concettuale, un'associazione rappresenta una relazione tra due [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md) (ad esempio `Customer` e `Order`). In un'applicazione, un'istanza di un'associazione rappresenta un'associazione specifica (ad esempio, un'associazione tra un'istanza di `Customer` e una di `Order`). Le istanze dell'associazione sono raggruppate logicamente in un [set di associazioni](../../../../docs/framework/data/adonet/association-set.md).  
  
 Una definizione di associazione contiene le informazioni seguenti:  
  
-   Un nome univoco. (obbligatorio).  
  
-   Due [estremità dell'associazione](../../../../docs/framework/data/adonet/association-end.md), uno per ogni tipo di entità nella relazione. (obbligatorio).  
  
    > [!NOTE]
    >  Un'associazione non può rappresentare una relazione tra più di due tipi di entità. Un'associazione può tuttavia definire una relazione interna specificando lo stesso tipo di entità per ognuna delle entità finali dell'associazione.  
  
-   Oggetto [vincolo di integrità referenziale](../../../../docs/framework/data/adonet/referential-integrity-constraint.md). (facoltativo)  
  
 Ogni entità finale dell'associazione deve specificare una [molteplicità di estremità dell'associazione](../../../../docs/framework/data/adonet/association-end-multiplicity.md) che indica il numero di istanze del tipo di entità che possono essere in un'entità finale dell'associazione. Una molteplicità di entità finale di associazione può avere un valore di uno (1), zero o uno (0..1) o molti (\*). Istanze del tipo di entità in un'entità finale di un'associazione sono accessibili attraverso [le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) o chiavi esterne se sono esposte in un tipo di entità. Per altre informazioni, vedere [Entity Data Model: Le chiavi esterne](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`. Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`. La molteplicità del `Publisher` finale è uno (1) e la molteplicità dell'entità la `Book` finale è molti (\*), che indica che un editore pubblica molti libri e un libro viene pubblicato da un server di pubblicazione.  
  
 ![Modello di esempio con tre tipi di entità](./media/association-type/example-model-three-entity-types.gif)  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
