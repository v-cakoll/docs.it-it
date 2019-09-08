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
# <a name="entity-data-model-namespaces"></a>Entity Data Model: Spazi dei nomi
Uno spazio dei nomi nel Entity Data Model (EDM) è un contenitore astratto per [tipi di entità](entity-type.md), [tipi complessi](complex-type.md)e [associazioni](association-type.md). Gli spazi dei nomi in EDM sono analoghi agli spazi dei nomi in un linguaggio di programmazione: forniscono il contesto per gli oggetti che contengono e un modo per distinguere gli oggetti con lo stesso nome (ma contenuti in spazi dei nomi diversi).  
  
## <a name="example"></a>Esempio  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel codice CSDL seguente viene usato uno spazio dei nomi per identificare un tipo definito in un modello concettuale diverso. Nell'esempio viene definito un tipo di entità (`Publisher`) che dispone di una proprietà di tipo complesso (`Address`) importata dallo spazio dei nomi `ExtendedBooksModel`. Si noti che l'elemento `Using` indica che è stato importato uno spazio dei nomi. Si noti inoltre il tipo della proprietà `Address` viene definito usando il nome completo (`ExtendedBooksModel.Address`), a indicare che questo tipo è definito nello spazio dei nomi `ExtendedBooksModel`.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
