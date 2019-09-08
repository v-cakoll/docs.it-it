---
title: funzione dichiarata dal modello
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: cb2fca52604bd57f25469f5621c292a27638c76f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794793"
---
# <a name="model-declared-function"></a>funzione dichiarata dal modello
Una *funzione dichiarata dal modello* è una funzione dichiarata in un modello concettuale, ma non è definita nel modello concettuale. La funzione può essere definita nell'ambiente host o di archiviazione. È possibile, ad esempio, eseguire il mapping di una funzione dichiarata dal modello a una funzione definita in un database, esponendo in tal modo la funzionalità lato server nel modello concettuale.  
  
 La dichiarazione di una funzione dichiarata dal modello contiene le informazioni seguenti:  
  
- Nome della funzione. (obbligatorio).  
  
- Il tipo del valore restituito (facoltativo)  
  
    > [!NOTE]
    > Se non viene specificato alcun valore restituito, il tipo restituito sarà void.  
  
- Informazioni sul parametro, inclusi il nome e il tipo del parametro (facoltativo)  
  
## <a name="example"></a>Esempio  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali. In CSDL, un'implementazione di una funzione dichiarata dal modello è un'importazione di funzioni (mediante l' [elemento FunctionImport](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)). Il seguente linguaggio CSDL definisce un contenitore di entità con una definizione di importazione di funzioni. Si noti che il tipo restituito per la funzione è void perché non è specificato alcun tipo restituito.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
