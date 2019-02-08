---
title: funzione dichiarata dal modello
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: 31efbab4b8323ff8cec9498fa20fa40b1efb819e
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904070"
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
 Il [ADO.NET Entity Framework](./ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali. In CSDL, un'implementazione di una funzione dichiarata dal modello è un oggetto function import (usando il [elemento FunctionImport](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)). Il seguente linguaggio CSDL definisce un contenitore di entità con una definizione di importazione di funzioni. Si noti che il tipo restituito per la funzione è void perché non è specificato alcun tipo restituito.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>Vedere anche
- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
