---
title: tipo complesso
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: 8daeac8309434b3c4e090d8e75f2de02d63e8b11
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756813"
---
# <a name="complex-type"></a>tipo complesso
Oggetto *tipo complesso* è un modello per la definizione di proprietà dettagliate e strutturate sui [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md) o su altri tipi complessi. Ogni modello contiene quanto segue:  
  
-   Un nome univoco. (obbligatorio).  
  
    > [!NOTE]
    >  Il nome di un tipo complesso non può coincidere con il nome di un tipo di entità all'interno dello stesso spazio dei nomi.  
  
-   Dati sotto forma di uno o più [proprietà](../../../../docs/framework/data/adonet/property.md). (Facoltative)  
  
    > [!NOTE]
    >  Una proprietà di un tipo complesso può essere un altro tipo complesso.  
  
 Un tipo complesso è analogo a un tipo di entità in cui un tipo complesso può contenere un payload di dati sotto forma di proprietà di tipo primitivo o di altri tipi complessi. Tuttavia esistono alcune differenze importanti tra i tipi complessi e i tipi di entità:  
  
-   I tipi complessi non dispongono di identità e pertanto non possono esistere indipendentemente. I tipi complessi possono esistere solo come proprietà in tipi di entità o altri tipi complessi.  
  
-   Tipi complessi non possono partecipare [associazioni](../../../../docs/framework/data/adonet/association-type.md). Le entità finali di un'associazione possono essere un tipo complesso e pertanto [le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) non può essere definito per i tipi complessi.  
  
## <a name="example"></a>Esempio  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel linguaggio CSDL seguente viene definito un tipo complesso, Address, con le proprietà di tipo primitivo `StreetAddress`, `City`, `StateOrProvince`, `Country` e `PostalCode`.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 Per definire il tipo complesso `Address` (sopra) come proprietà su un tipo di entità, è necessario dichiarare il tipo di proprietà nella definizione del tipo di entità. Nel linguaggio CSDL seguente viene dichiarata la proprietà `Address` come un tipo complesso di un tipo di entità (Publisher):  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
