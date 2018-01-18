---
title: 'Entity Data Model: spazi dei nomi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b3e69017b5f617cff9bf2c159d5538a8c41e4cc0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="entity-data-model-namespaces"></a>Entity Data Model: spazi dei nomi
Uno spazio dei nomi in Entity Data Model (EDM) è un contenitore astratto per [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md), [tipi complessi](../../../../docs/framework/data/adonet/complex-type.md), e [associazioni](../../../../docs/framework/data/adonet/association-type.md). Gli spazi dei nomi in EDM sono analoghi agli spazi dei nomi in un linguaggio di programmazione: forniscono il contesto per gli oggetti che contengono e un modo per distinguere gli oggetti con lo stesso nome (ma contenuti in spazi dei nomi diversi).  
  
## <a name="example"></a>Esempio  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel codice CSDL seguente viene usato uno spazio dei nomi per identificare un tipo definito in un modello concettuale diverso. Nell'esempio viene definito un tipo di entità (`Publisher`) che dispone di una proprietà di tipo complesso (`Address`) importata dallo spazio dei nomi `ExtendedBooksModel`. Si noti che l'elemento `Using` indica che è stato importato uno spazio dei nomi. Si noti inoltre il tipo della proprietà `Address` viene definito usando il nome completo (`ExtendedBooksModel.Address`), a indicare che questo tipo è definito nello spazio dei nomi `ExtendedBooksModel`.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
