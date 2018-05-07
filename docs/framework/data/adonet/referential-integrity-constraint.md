---
title: vincolo di integrità referenziale
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: a4d63e07da0c75b8a0369933fccfc0cc66fcc40b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="referential-integrity-constraint"></a>vincolo di integrità referenziale
Oggetto *vincolo di integrità referenziale* in Entity Data Model (EDM) è simile a un vincolo di integrità referenziale in un database relazionale. Nello stesso modo che una colonna (colonne) da una tabella di database può fare riferimento o la chiave primaria di un'altra tabella, una [proprietà](../../../../docs/framework/data/adonet/property.md) (o proprietà) di un [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) possono fare riferimento il [chiave di entità ](../../../../docs/framework/data/adonet/entity-key.md) di un altro tipo di entità. Il tipo di entità a cui fa riferimento viene chiamato il *finale principale* del vincolo. Il tipo di entità che fa riferimento l'entità finale principale viene chiamato il *estremità dipendente* del vincolo.  
  
 Un vincolo di integrità referenziale è definito come parte di un [associazione](../../../../docs/framework/data/adonet/association-type.md) tra due tipi di entità. La definizione per un vincolo di integrità referenziale specifica le informazioni seguenti:  
  
-   Entità finale principale del vincolo (un tipo di entità alla cui chiave di entità è fatto riferimento dall'entità finale dipendente).  
  
-   Chiave di entità dell'entità finale principale.  
  
-   Entità finale dipendente del vincolo (un tipo di entità che dispone di una o più proprietà che fanno riferimento alla chiave di entità dell'entità finale principale).  
  
-   La proprietà o le proprietà di riferimento dell'entità finale dipendente.  
  
 Lo scopo dei vincoli di integrità referenziali in EDM è di assicurare che esistano sempre associazioni valide. Per ulteriori informazioni, vedere [proprietà di chiave esterna](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `WrittenBy` e `PublishedBy`. Il tipo di entità `Book` dispone di una proprietà, `PublisherId`, che fa riferimento alla chiave di entità del tipo di entità `Publisher` quando si definisce un vincolo di integrità referenziale sull'associazione `PublishedBy`.  
  
 ![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel seguente linguaggio CSDL viene definito un vincolo di integrità referenziale sull'associazione `PublishedBy` illustrata nel modello concettuale precedente.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
