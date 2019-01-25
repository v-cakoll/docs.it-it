---
title: 'Entity Data Model: Ereditarietà'
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: 1a5ac0e4f5d4b8fe58b5d8577a27b26163d94952
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684203"
---
# <a name="entity-data-model-inheritance"></a>Entity Data Model: Ereditarietà
Entity Data Model (EDM) supporta l'ereditarietà per [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md). L'ereditarietà in EDM è analoga all'ereditarietà per le classi nei linguaggi di programmazione orientati a oggetti. Come con le classi nei linguaggi orientate a oggetti, in un modello concettuale è possibile definire un tipo di entità (un *tipo derivato*) che eredita da un altro tipo di entità (il *tipo di base*). Tuttavia, a differenza delle classi nella programmazione orientata agli oggetti, in un modello concettuale il tipo derivato eredita sempre tutte le [delle proprietà](../../../../docs/framework/data/adonet/property.md) e [le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) del tipo di base. Non è possibile eseguire l'override delle proprietà ereditate in un tipo derivato.  
  
 In un modello concettuale è possibile compilare gerarchie di ereditarietà nelle quali un tipo derivato eredita da un altro tipo derivato. Il tipo nella parte superiore della gerarchia (il tipo della gerarchia che non è un tipo derivato) viene chiamato il *tipo radice*. In una gerarchia di ereditarietà, il [chiave di entità](../../../../docs/framework/data/adonet/entity-key.md) deve essere definito nel tipo radice.  
  
 Non è possibile compilare gerarchie di ereditarietà nelle quali un tipo derivato eredita da più di un tipo. In un modello concettuale con un tipo di entità `Book`, ad esempio, è possibile definire i tipi derivati `FictionBook` e `NonFictionBook` che ereditano ognuno da `Book`. Non è quindi possibile, tuttavia, definire un tipo che eredita sia dal tipo `FictionBook` che dal tipo `NonFictionBook`.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con quattro tipi di entità: `Book`, `FictionBook`, `Publisher` e `Author`. Il tipo di entità `FictionBook` è un tipo derivato, che eredita dal tipo di entità `Book`. Il tipo `FictionBook` eredita le proprietà `ISBN (Key)`, `Title` e `Revision` e definisce una proprietà aggiuntiva chiamata `Genre`.  
  
 ![Inheritance](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel seguente linguaggio CSDL viene definito un tipo di entità, `FictionBook`, che eredita dal tipo `Book` (come nel diagramma precedente):  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>Vedere anche
- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
