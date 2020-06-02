---
title: vincolo di integrità referenziale
description: Informazioni sui vincoli di integrità referenziale nell'Entity Data Model, che garantiscono che le associazioni valide esistano sempre tra i tipi di entità.
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: 65c811b2a12a64870107ff771d5acc64e86f2c1f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286624"
---
# <a name="referential-integrity-constraint"></a>vincolo di integrità referenziale
Un *vincolo di integrità referenziale* nel Entity Data Model (EDM) è simile a un vincolo di integrità referenziale in un database relazionale. Nello stesso modo in cui una colonna (o più colonne) da una tabella di database può fare riferimento alla chiave primaria di un'altra tabella, una [Proprietà](property.md) (o più proprietà) di un [tipo di entità](entity-type.md) può fare riferimento alla [chiave di entità](entity-key.md) di un altro tipo di entità. Il tipo di entità a cui si fa riferimento viene chiamato *entità finale principale* del vincolo. Il tipo di entità che fa riferimento all'entità finale principale viene chiamato entità *finale dipendente* del vincolo.  
  
 Un vincolo di integrità referenziale viene definito come parte di un' [associazione](association-type.md) tra due tipi di entità. La definizione per un vincolo di integrità referenziale specifica le informazioni seguenti:  
  
- Entità finale principale del vincolo (un tipo di entità alla cui chiave di entità è fatto riferimento dall'entità finale dipendente).  
  
- Chiave di entità dell'entità finale principale.  
  
- Entità finale dipendente del vincolo (un tipo di entità che dispone di una o più proprietà che fanno riferimento alla chiave di entità dell'entità finale principale).  
  
- La proprietà o le proprietà di riferimento dell'entità finale dipendente.  
  
 Lo scopo dei vincoli di integrità referenziali in EDM è di assicurare che esistano sempre associazioni valide. Per ulteriori informazioni, vedere [proprietà di chiave esterna](foreign-key-property.md).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `WrittenBy` e `PublishedBy`. Il tipo di entità `Book` dispone di una proprietà, `PublisherId`, che fa riferimento alla chiave di entità del tipo di entità `Publisher` quando si definisce un vincolo di integrità referenziale sull'associazione `PublishedBy`.  
  
 ![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Esempio di modello di vincolo referenziale")  
  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali. Nel seguente linguaggio CSDL viene definito un vincolo di integrità referenziale sull'associazione `PublishedBy` illustrata nel modello concettuale precedente.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
