---
title: molteplicità di entità finale dell'associazione
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 59eed56204543adf405cfc7c71a49697a9e18374
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135031"
---
# <a name="association-end-multiplicity"></a>molteplicità di entità finale dell'associazione
*Molteplicità di estremità dell'associazione* definisce il numero di [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) istanze che possono essere a un estremo di una [associazione](../../../../docs/framework/data/adonet/association-type.md).  
  
 Una molteplicità di entità finale dell'associazione può disporre di uno dei valori seguenti:  
  
-   uno (1): Indica a che tale istanza del tipo esattamente un'entità è presente l'estremità dell'associazione.  
  
-   zero o uno (0..1): Indica che presenti zero o più istanze del tipo di entità finale dell'associazione.  
  
-   molte (\*): indica che da zero, uno o più istanze del tipo di entità sono presenti entità finale dell'associazione.  
  
 Un'associazione è spesso caratterizzata dalle molteplicità di entità finale dell'associazione. Ad esempio, se le entità finali di un'associazione dispongono di molteplicità uno (1) e molti (\*), l'associazione viene definita un'associazione uno-a-molti. Nell'esempio seguente, l'associazione `PublishedBy` è un'associazione uno-a-molti (un editore pubblica molti libri e un libro viene pubblicato da un solo editore). L'associazione `WrittenBy` è un'associazione molti-a-molti (un libro può avere più autori e un autore può scrivere più libri).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`. Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`. La molteplicità del `Publisher` finale è uno (1) e la molteplicità dell'entità la `Book` finale è molti (\*).  
  
 ![Modello di esempio con tre tipi di entità](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 ADO.NET Entity Framework Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
