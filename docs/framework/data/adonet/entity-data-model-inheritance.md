---
title: "Entity Data Model: ereditarietà"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6e6207087524a1ec1201511a91a810f02449e610
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="entity-data-model-inheritance"></a>Entity Data Model: ereditarietà
Entity Data Model (EDM) supporta l'ereditarietà per [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md). L'ereditarietà in EDM è analoga all'ereditarietà per le classi nei linguaggi di programmazione orientati a oggetti. Come con le classi nei linguaggi orientati a oggetti, in un modello concettuale è possibile definire un tipo di entità (un *tipo derivato*) che eredita da un altro tipo di entità (il *tipo di base*). Tuttavia, a differenza delle classi nella programmazione orientata a oggetti, in un modello concettuale il tipo derivato eredita sempre tutte le [proprietà](../../../../docs/framework/data/adonet/property.md) e [le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) del tipo di base. Non è possibile eseguire l'override delle proprietà ereditate in un tipo derivato.  
  
 In un modello concettuale è possibile compilare gerarchie di ereditarietà nelle quali un tipo derivato eredita da un altro tipo derivato. Il tipo nella parte superiore della gerarchia (il tipo nella gerarchia che non è un tipo derivato) viene chiamato il *tipo radice*. In una gerarchia di ereditarietà, la [chiave di entità](../../../../docs/framework/data/adonet/entity-key.md) devono essere definiti sul tipo radice.  
  
 Non è possibile compilare gerarchie di ereditarietà nelle quali un tipo derivato eredita da più di un tipo. In un modello concettuale con un tipo di entità `Book`, ad esempio, è possibile definire i tipi derivati `FictionBook` e `NonFictionBook` che ereditano ognuno da `Book`. Non è quindi possibile, tuttavia, definire un tipo che eredita sia dal tipo `FictionBook` che dal tipo `NonFictionBook`.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con quattro tipi di entità: `Book`, `FictionBook`, `Publisher` e `Author`. Il tipo di entità `FictionBook` è un tipo derivato, che eredita dal tipo di entità `Book`. Il tipo `FictionBook` eredita le proprietà `ISBN (Key)`, `Title` e `Revision` e definisce una proprietà aggiuntiva chiamata `Genre`.  
  
 ![Ereditarietà](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel seguente linguaggio CSDL viene definito un tipo di entità, `FictionBook`, che eredita dal tipo `Book` (come nel diagramma precedente):  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
