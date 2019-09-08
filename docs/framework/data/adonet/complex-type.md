---
title: tipo complesso
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: 0d9b8efd08cc0dfba5b26a70773b614b0d63d74f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786756"
---
# <a name="complex-type"></a>tipo complesso
Un *tipo complesso* è un modello per la definizione di proprietà ricche e strutturate sui [tipi di entità](entity-type.md) o su altri tipi complessi. Ogni modello contiene quanto segue:  
  
- Un nome univoco. (obbligatorio).  
  
    > [!NOTE]
    > Il nome di un tipo complesso non può coincidere con il nome di un tipo di entità all'interno dello stesso spazio dei nomi.  
  
- Dati sotto forma di una o più [Proprietà](property.md). (Facoltative)  
  
    > [!NOTE]
    > Una proprietà di un tipo complesso può essere un altro tipo complesso.  
  
 Un tipo complesso è analogo a un tipo di entità in cui un tipo complesso può contenere un payload di dati sotto forma di proprietà di tipo primitivo o di altri tipi complessi. Tuttavia esistono alcune differenze importanti tra i tipi complessi e i tipi di entità:  
  
- I tipi complessi non dispongono di identità e pertanto non possono esistere indipendentemente. I tipi complessi possono esistere solo come proprietà in tipi di entità o altri tipi complessi.  
  
- I tipi complessi non possono partecipare alle [associazioni](association-type.md). Nessuna entità finale di un'associazione può essere un tipo complesso e pertanto non è possibile definire [proprietà di navigazione](navigation-property.md) su tipi complessi.  
  
## <a name="example"></a>Esempio  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel linguaggio CSDL seguente viene definito un tipo complesso, Address, con le proprietà di tipo primitivo `StreetAddress`, `City`, `StateOrProvince`, `Country` e `PostalCode`.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 Per definire il tipo complesso `Address` (sopra) come proprietà su un tipo di entità, è necessario dichiarare il tipo di proprietà nella definizione del tipo di entità. Nel linguaggio CSDL seguente viene dichiarata la proprietà `Address` come un tipo complesso di un tipo di entità (Publisher):  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
