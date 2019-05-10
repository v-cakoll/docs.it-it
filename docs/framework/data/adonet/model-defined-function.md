---
title: funzione definita dal modello
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 4f98bbc9fdc19159354ec3e414c1a1c26029cb47
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645841"
---
# <a name="model-defined-function"></a><span data-ttu-id="20e7a-102">funzione definita dal modello</span><span class="sxs-lookup"><span data-stu-id="20e7a-102">model-defined function</span></span>
<span data-ttu-id="20e7a-103">Oggetto *funzione definita dal modello* è una funzione che viene definita in un modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="20e7a-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="20e7a-104">Il corpo di una funzione definita dal modello viene espresso [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), che consente la funzione può essere espresso in modo indipendente le regole o dai linguaggi supportati nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="20e7a-104">The body of a model-defined function is expressed in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="20e7a-105">Una definizione per una funzione definita dal modello contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20e7a-105">A definition for a model-defined function contains the following information:</span></span>  
  
- <span data-ttu-id="20e7a-106">Un nome di funzione</span><span class="sxs-lookup"><span data-stu-id="20e7a-106">A function name.</span></span> <span data-ttu-id="20e7a-107">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="20e7a-107">(Required)</span></span>  
  
- <span data-ttu-id="20e7a-108">Il tipo del valore restituito</span><span class="sxs-lookup"><span data-stu-id="20e7a-108">The type of the return value.</span></span> <span data-ttu-id="20e7a-109">(facoltativo)</span><span class="sxs-lookup"><span data-stu-id="20e7a-109">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20e7a-110">Se non viene specificato alcun tipo restituito, il valore restituito sarà void.</span><span class="sxs-lookup"><span data-stu-id="20e7a-110">If no return type is specified, the return value is void.</span></span>  
  
- <span data-ttu-id="20e7a-111">Informazioni sui parametri</span><span class="sxs-lookup"><span data-stu-id="20e7a-111">Parameter information.</span></span> <span data-ttu-id="20e7a-112">(facoltativo)</span><span class="sxs-lookup"><span data-stu-id="20e7a-112">(Optional)</span></span>  
  
- <span data-ttu-id="20e7a-113">Un' [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) espressione che definisce il corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="20e7a-113">An [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="20e7a-114">Si noti che le funzioni definite dal modello non supportano parametri di output.</span><span class="sxs-lookup"><span data-stu-id="20e7a-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="20e7a-115">Questa restrizione esiste perché possano essere create funzioni definite dal modello.</span><span class="sxs-lookup"><span data-stu-id="20e7a-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20e7a-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="20e7a-116">Example</span></span>  
 <span data-ttu-id="20e7a-117">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="20e7a-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![Screenshot che mostra un modello con data di pubblicazione.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 <span data-ttu-id="20e7a-119">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="20e7a-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="20e7a-120">Nel seguente linguaggio CSDL viene definita una funzione nel modello concettuale che restituisce i numeri di anni da quando è stata pubblicata un'istanza di un `Book` (nel diagramma precedente).</span><span class="sxs-lookup"><span data-stu-id="20e7a-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="20e7a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20e7a-121">See also</span></span>

- [<span data-ttu-id="20e7a-122">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="20e7a-122">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="20e7a-123">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="20e7a-123">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
- [<span data-ttu-id="20e7a-124">Entity Data Model: Tipi di dati primitivi</span><span class="sxs-lookup"><span data-stu-id="20e7a-124">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
