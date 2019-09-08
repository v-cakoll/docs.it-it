---
title: 'Entity Data Model: Spazi dei nomi'
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: a8629a1f162f5d942390f62d5a2ac20e2135c531
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784007"
---
# <a name="entity-data-model-namespaces"></a><span data-ttu-id="c16ff-102">Entity Data Model: Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="c16ff-102">Entity Data Model: Namespaces</span></span>
<span data-ttu-id="c16ff-103">Uno spazio dei nomi nel Entity Data Model (EDM) è un contenitore astratto per [tipi di entità](entity-type.md), [tipi complessi](complex-type.md)e [associazioni](association-type.md).</span><span class="sxs-lookup"><span data-stu-id="c16ff-103">A namespace in the Entity Data Model (EDM) is an abstract container for [entity types](entity-type.md), [complex types](complex-type.md), and [associations](association-type.md).</span></span> <span data-ttu-id="c16ff-104">Gli spazi dei nomi in EDM sono analoghi agli spazi dei nomi in un linguaggio di programmazione: forniscono il contesto per gli oggetti che contengono e un modo per distinguere gli oggetti con lo stesso nome (ma contenuti in spazi dei nomi diversi).</span><span class="sxs-lookup"><span data-stu-id="c16ff-104">Namespaces in the EDM are similar to namespaces in a programming language: they provide context for the objects that they contain and they provide a way to disambiguate objects that have the same name (but are contained in different namespaces).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c16ff-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c16ff-105">Example</span></span>  
 <span data-ttu-id="c16ff-106">Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="c16ff-106">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="c16ff-107">Nel codice CSDL seguente viene usato uno spazio dei nomi per identificare un tipo definito in un modello concettuale diverso.</span><span class="sxs-lookup"><span data-stu-id="c16ff-107">The following CSDL code uses a namespace to identify a type that is defined in a different conceptual model.</span></span> <span data-ttu-id="c16ff-108">Nell'esempio viene definito un tipo di entità (`Publisher`) che dispone di una proprietà di tipo complesso (`Address`) importata dallo spazio dei nomi `ExtendedBooksModel`.</span><span class="sxs-lookup"><span data-stu-id="c16ff-108">The example defines an entity type (`Publisher`) that has a complex type property (`Address`) that is imported from the `ExtendedBooksModel` namespace.</span></span> <span data-ttu-id="c16ff-109">Si noti che l'elemento `Using` indica che è stato importato uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c16ff-109">Note that the `Using` element indicates that a namespace has been imported.</span></span> <span data-ttu-id="c16ff-110">Si noti inoltre il tipo della proprietà `Address` viene definito usando il nome completo (`ExtendedBooksModel.Address`), a indicare che questo tipo è definito nello spazio dei nomi `ExtendedBooksModel`.</span><span class="sxs-lookup"><span data-stu-id="c16ff-110">Also note that the type of the `Address` property is defined by using its fully qualified name (`ExtendedBooksModel.Address`), indicating that this type is defined in the `ExtendedBooksModel` namespace.</span></span>  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a><span data-ttu-id="c16ff-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c16ff-111">See also</span></span>

- [<span data-ttu-id="c16ff-112">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="c16ff-112">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="c16ff-113">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="c16ff-113">Entity Data Model</span></span>](entity-data-model.md)
