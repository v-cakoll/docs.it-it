---
title: tipo di entità
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 1dafce5f7f95ba6f391c8742944f40a9afa7dcf8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737812"
---
# <a name="entity-type"></a><span data-ttu-id="b3f69-102">tipo di entità</span><span class="sxs-lookup"><span data-stu-id="b3f69-102">entity type</span></span>
<span data-ttu-id="b3f69-103">Il *tipo di entità* è il blocco predefinito fondamentale per la descrizione della struttura dei dati con il Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="b3f69-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="b3f69-104">In un modello concettuale, un tipo di entità rappresenta la struttura di concetti di livello superiore, quale ad esempio clienti o ordini.</span><span class="sxs-lookup"><span data-stu-id="b3f69-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="b3f69-105">Un tipo di entità è un modello per le istanze del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="b3f69-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="b3f69-106">Ogni modello contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3f69-106">Each template contains the following information:</span></span>  
  
- <span data-ttu-id="b3f69-107">Un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="b3f69-107">A unique name.</span></span> <span data-ttu-id="b3f69-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b3f69-108">(Required.)</span></span>  
  
- <span data-ttu-id="b3f69-109">[Chiave di entità](entity-key.md) definita da una o più proprietà.</span><span class="sxs-lookup"><span data-stu-id="b3f69-109">An [entity key](entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="b3f69-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b3f69-110">(Required.)</span></span>  
  
- <span data-ttu-id="b3f69-111">Dati sotto forma di [Proprietà](property.md).</span><span class="sxs-lookup"><span data-stu-id="b3f69-111">Data in the form of [properties](property.md).</span></span> <span data-ttu-id="b3f69-112">(Facoltative)</span><span class="sxs-lookup"><span data-stu-id="b3f69-112">(Optional.)</span></span>  
  
- <span data-ttu-id="b3f69-113">[Proprietà di navigazione](navigation-property.md) che consentono la navigazione da un'entità [finale](association-end.md) di un' [associazione](association-type.md) all'altra estremità.</span><span class="sxs-lookup"><span data-stu-id="b3f69-113">[Navigation properties](navigation-property.md) that allow for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="b3f69-114">(facoltativo)</span><span class="sxs-lookup"><span data-stu-id="b3f69-114">(Optional)</span></span>  
  
 <span data-ttu-id="b3f69-115">In un'applicazione, un'istanza di un tipo di entità rappresenta un oggetto specifico, quale ad esempio un cliente o un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="b3f69-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="b3f69-116">Ogni istanza di un tipo di entità deve avere una [chiave di entità](entity-key.md) univoca all'interno di un [set di entità](entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="b3f69-116">Each instance of an entity type must have a unique [entity key](entity-key.md) within an [entity set](entity-set.md).</span></span>  
  
 <span data-ttu-id="b3f69-117">Due istanze di tipi di entità sono considerate uguali solo se sono dello stesso tipo e se i valori delle rispettive chiavi di entità sono uguali.</span><span class="sxs-lookup"><span data-stu-id="b3f69-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3f69-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3f69-118">Example</span></span>  
 <span data-ttu-id="b3f69-119">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`:</span><span class="sxs-lookup"><span data-stu-id="b3f69-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 ![Modello di esempio con tre tipi di entità](./media/entity-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="b3f69-121">Si noti che le proprietà di ogni tipo di entità che costituiscono la chiave di entità vengono indicate con "(Key)".</span><span class="sxs-lookup"><span data-stu-id="b3f69-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="b3f69-122">Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="b3f69-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="b3f69-123">Il linguaggio CSDL seguente definisce il tipo di entità `Book` illustrato nel diagramma precedente:</span><span class="sxs-lookup"><span data-stu-id="b3f69-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="b3f69-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3f69-124">See also</span></span>

- [<span data-ttu-id="b3f69-125">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b3f69-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="b3f69-126">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b3f69-126">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="b3f69-127">facet</span><span class="sxs-lookup"><span data-stu-id="b3f69-127">facet</span></span>](facet.md)
