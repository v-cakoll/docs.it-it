---
title: funzione definita dal modello
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e1c9d438840a0b9c15597177ca4e6d870d526756
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="model-defined-function"></a>funzione definita dal modello
Oggetto *definita dal modello di funzione* è una funzione definita in un modello concettuale. Il corpo di una funzione definita dal modello viene espresso [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), che consente la funzione di esprimere in modo indipendente da regole o dai linguaggi supportati nell'origine dati.  
  
 Una definizione per una funzione definita dal modello contiene le informazioni seguenti:  
  
-   Un nome di funzione (obbligatorio).  
  
-   Il tipo del valore restituito (facoltativo)  
  
    > [!NOTE]
    >  Se non viene specificato alcun tipo restituito, il valore restituito sarà void.  
  
-   Informazioni sui parametri (facoltativo)  
  
-   Un [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) espressione che definisce il corpo della funzione.  
  
 Si noti che le funzioni definite dal modello non supportano parametri di output. Questa restrizione esiste perché possano essere create funzioni definite dal modello.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.  
  
 ![Modello con data pubblicata](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel seguente linguaggio CSDL viene definita una funzione nel modello concettuale che restituisce i numeri di anni da quando è stata pubblicata un'istanza di un `Book` (nel diagramma precedente).  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [Entity Data Model: tipi di dati primitivi](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
