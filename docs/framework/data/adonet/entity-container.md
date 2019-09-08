---
title: contenitore di entità
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 95740fb9d8b357a4fa160af6fdafb139711283cd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795252"
---
# <a name="entity-container"></a>contenitore di entità
Un *contenitore di entità* è un raggruppamento logico di [set di entità](entity-set.md), [set di associazioni](association-set.md)e [importazioni di funzioni](model-declared-function.md).  
  
 Le affermazioni seguenti relative a un contenitore di entità definito in un modello concettuale devono essere vere:  
  
- In ogni modello concettuale deve essere definito almeno un contenitore di entità.  
  
- Il contenitore di entità deve disporre di un nome univoco all'interno di ogni modello concettuale.  
  
 Un contenitore di entità può definire set di entità o set di associazioni che usano i tipi o le associazioni di entità definite in uno o più spazi dei nomi. Per ulteriori informazioni, vedere [Entity Data Model: Spazi dei nomi.](entity-data-model-namespaces.md)  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.  Per altre informazioni, vedere l'esempio successivo.  
  
 ![Modello di esempio con tre tipi di entità](./media/entity-container/example-model-three-entity-types.gif)  
  
 Anche se nel diagramma non sono contenute informazioni sul contenitore di entità, il modello concettuale deve definire un contenitore di entità. Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio DSL denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce un contenitore di entità per il modello concettuale illustrato nel diagramma precedente. Si noti che il nome del contenitore di entità è definito in un attributo XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
