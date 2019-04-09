---
title: tipo complesso
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: 9d63660c441192bbc9ecb48bb3a86030b46461cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160810"
---
# <a name="complex-type"></a>tipo complesso
Oggetto *tipo complesso* è un modello per la definizione di proprietà dettagliate e strutturate sul [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md) o su altri tipi complessi. Ogni modello contiene quanto segue:  
  
-   Un nome univoco. (obbligatorio).  
  
    > [!NOTE]
    >  Il nome di un tipo complesso non può coincidere con il nome di un tipo di entità all'interno dello stesso spazio dei nomi.  
  
-   Dati sotto forma di uno o più [proprietà](../../../../docs/framework/data/adonet/property.md). (Facoltative)  
  
    > [!NOTE]
    >  Una proprietà di un tipo complesso può essere un altro tipo complesso.  
  
 Un tipo complesso è analogo a un tipo di entità in cui un tipo complesso può contenere un payload di dati sotto forma di proprietà di tipo primitivo o di altri tipi complessi. Tuttavia esistono alcune differenze importanti tra i tipi complessi e i tipi di entità:  
  
-   I tipi complessi non dispongono di identità e pertanto non possono esistere indipendentemente. I tipi complessi possono esistere solo come proprietà in tipi di entità o altri tipi complessi.  
  
-   I tipi complessi non possono partecipare [associazioni](../../../../docs/framework/data/adonet/association-type.md). Le entità finali di un'associazione possono essere un tipo complesso e pertanto [le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) non è possibile definire i tipi complessi.  
  
## <a name="example"></a>Esempio  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel linguaggio CSDL seguente viene definito un tipo complesso, Address, con le proprietà di tipo primitivo `StreetAddress`, `City`, `StateOrProvince`, `Country` e `PostalCode`.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 Per definire il tipo complesso `Address` (sopra) come proprietà su un tipo di entità, è necessario dichiarare il tipo di proprietà nella definizione del tipo di entità. Nel linguaggio CSDL seguente viene dichiarata la proprietà `Address` come un tipo complesso di un tipo di entità (Publisher):  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
