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
# <a name="model-declared-function"></a><span data-ttu-id="dc24f-102">funzione dichiarata dal modello</span><span class="sxs-lookup"><span data-stu-id="dc24f-102">model-declared function</span></span>
<span data-ttu-id="dc24f-103">Oggetto *funzione dichiarata dal modello* è una funzione che viene dichiarata in un modello concettuale, ma non è definita nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="dc24f-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="dc24f-104">La funzione può essere definita nell'ambiente host o di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="dc24f-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="dc24f-105">È possibile, ad esempio, eseguire il mapping di una funzione dichiarata dal modello a una funzione definita in un database, esponendo in tal modo la funzionalità lato server nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="dc24f-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="dc24f-106">La dichiarazione di una funzione dichiarata dal modello contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc24f-106">The declaration of a model-declared function contains the following information:</span></span>  
  
-   <span data-ttu-id="dc24f-107">Nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="dc24f-107">The name of the function.</span></span> <span data-ttu-id="dc24f-108">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="dc24f-108">(Required)</span></span>  
  
-   <span data-ttu-id="dc24f-109">Il tipo del valore restituito</span><span class="sxs-lookup"><span data-stu-id="dc24f-109">The type of the return value.</span></span> <span data-ttu-id="dc24f-110">(facoltativo)</span><span class="sxs-lookup"><span data-stu-id="dc24f-110">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dc24f-111">Se non viene specificato alcun valore restituito, il tipo restituito sarà void.</span><span class="sxs-lookup"><span data-stu-id="dc24f-111">If no return value is specified, the return type is void.</span></span>  
  
-   <span data-ttu-id="dc24f-112">Informazioni sul parametro, inclusi il nome e il tipo del parametro</span><span class="sxs-lookup"><span data-stu-id="dc24f-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="dc24f-113">(facoltativo)</span><span class="sxs-lookup"><span data-stu-id="dc24f-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc24f-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc24f-114">Example</span></span>  
 <span data-ttu-id="dc24f-115">Il [ADO.NET Entity Framework](./ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="dc24f-115">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="dc24f-116">In CSDL, un'implementazione di una funzione dichiarata dal modello è un oggetto function import (usando il [elemento FunctionImport](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span><span class="sxs-lookup"><span data-stu-id="dc24f-116">In CSDL, one implementation of a model-declared function is a function import (using the [FunctionImport element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span></span> <span data-ttu-id="dc24f-117">Il seguente linguaggio CSDL definisce un contenitore di entità con una definizione di importazione di funzioni.</span><span class="sxs-lookup"><span data-stu-id="dc24f-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="dc24f-118">Si noti che il tipo restituito per la funzione è void perché non è specificato alcun tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="dc24f-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="dc24f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc24f-119">See also</span></span>
- [<span data-ttu-id="dc24f-120">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="dc24f-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="dc24f-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="dc24f-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
