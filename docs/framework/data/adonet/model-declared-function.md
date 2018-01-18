---
title: funzione dichiarata dal modello
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 85fb07b3577e7e61536664a346154ba9602cd9f3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="model-declared-function"></a>funzione dichiarata dal modello
Oggetto *funzione dichiarata dal modello* è una funzione che viene dichiarata in un modello concettuale, ma non è definita nel modello concettuale. La funzione può essere definita nell'ambiente host o di archiviazione. È possibile, ad esempio, eseguire il mapping di una funzione dichiarata dal modello a una funzione definita in un database, esponendo in tal modo la funzionalità lato server nel modello concettuale.  
  
 La dichiarazione di una funzione dichiarata dal modello contiene le informazioni seguenti:  
  
-   Nome della funzione. (obbligatorio).  
  
-   Il tipo del valore restituito (facoltativo)  
  
    > [!NOTE]
    >  Se non viene specificato alcun valore restituito, il tipo restituito sarà void.  
  
-   Informazioni sul parametro, inclusi il nome e il tipo del parametro (facoltativo)  
  
## <a name="example"></a>Esempio  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. In CSDL, un'implementazione di una funzione dichiarata dal modello è un [importazione di funzioni](http://msdn.microsoft.com/en-us/125704ae-56c7-4233-80b7-389a10f3a65d). Il seguente linguaggio CSDL definisce un contenitore di entità con una definizione di importazione di funzioni. Si noti che il tipo restituito per la funzione è void perché non è specificato alcun tipo restituito.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
