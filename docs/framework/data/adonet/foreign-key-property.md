---
title: proprietà di chiave esterna
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: a77f7479ce38cb34830377021157f312916baca4
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738403"
---
# <a name="foreign-key-property"></a>proprietà di chiave esterna
Una *proprietà di chiave esterna* nel Entity Data Model (EDM) è una [Proprietà](property.md) di tipo primitivo (o un set di proprietà di tipo primitivo) in un [tipo di entità](entity-type.md) che contiene la chiave di [entità](entity-key.md) di un altro tipo di entità.  
  
 Una proprietà di chiave esterna è analoga a una colonna di chiave esterna in un database relazionale. Nello stesso modo in cui le colonne chiave esterna vengono utilizzate in un database relazionale per creare relazioni tra le righe nelle tabelle, le proprietà di chiave esterna in un modello concettuale vengono utilizzate per stabilire [associazioni](association-type.md) tra tipi di entità. Un [vincolo di integrità referenziale](referential-integrity-constraint.md) viene utilizzato per definire un'associazione tra due tipi di entità quando uno dei tipi dispone di una proprietà di chiave esterna.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`. Il tipo di entità `Book` dispone di una proprietà, `PublisherId`, che fa riferimento alla chiave di entità del tipo di entità `Publisher` quando si definisce un vincolo di integrità referenziale sull'associazione `PublishedBy`.  
  
 ![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Esempio di modello di vincolo referenziale")  
  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali. Il linguaggio CSDL seguente usa la proprietà di chiave esterna `PublisherId` per definire un vincolo di integrità referenziale sull'associazione `PublishedBy` illustrata nel modello concettuale precedente.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
