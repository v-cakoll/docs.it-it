---
title: molteplicità di entità finale dell'associazione
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: cdcf69e7118620b2f8febd02d7695d429bf8cc2c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786951"
---
# <a name="association-end-multiplicity"></a>molteplicità di entità finale dell'associazione
La *molteplicità* di entità finale dell'associazione definisce il numero di istanze del [tipo di entità](entity-type.md) che possono trovarsi in un'entità finale di un' [associazione](association-type.md).  
  
 Una molteplicità di entità finale dell'associazione può disporre di uno dei valori seguenti:  
  
- uno (1): Indica che esiste esattamente un'istanza del tipo di entità nell'entità finale dell'associazione.  
  
- zero o uno (0.. 1): Indica che nell'entità finale dell'associazione sono presenti zero o un'istanza del tipo di entità.  
  
- molti (\*): Indica che nell'entità finale dell'associazione sono presenti zero, una o più istanze del tipo di entità.  
  
 Un'associazione è spesso caratterizzata dalle molteplicità di entità finale dell'associazione. Se, ad esempio, le entità finali di un'associazione hanno molteplicità uno (1) e\*molti (), l'associazione viene definita associazione uno-a-molti. Nell'esempio seguente, l'associazione `PublishedBy` è un'associazione uno-a-molti (un editore pubblica molti libri e un libro viene pubblicato da un solo editore). L'associazione `WrittenBy` è un'associazione molti-a-molti (un libro può avere più autori e un autore può scrivere più libri).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`. Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`. La molteplicità dell' `Publisher` entità finale è uno (1) e la molteplicità `Book` dell'entità finale è molti (\*).  
  
 ![Modello di esempio con tre tipi di entità](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 Il Entity Framework ADO.NET utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
