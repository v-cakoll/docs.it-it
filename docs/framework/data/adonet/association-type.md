---
title: tipo di associazione
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: e75037223b235cf09df0bca85c6a4feb0b340174
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786889"
---
# <a name="association-type"></a>tipo di associazione
Un *tipo di associazione* (detto anche associazione) è il blocco predefinito fondamentale per la descrizione delle relazioni nell'Entity Data Model (EDM). In un modello concettuale, un'associazione rappresenta una relazione tra due [tipi di entità](entity-type.md) ( `Customer` ad `Order`esempio e). In un'applicazione, un'istanza di un'associazione rappresenta un'associazione specifica (ad esempio, un'associazione tra un'istanza di `Customer` e una di `Order`). Le istanze di associazione vengono raggruppate logicamente in un [set di associazioni](association-set.md).  
  
 Una definizione di associazione contiene le informazioni seguenti:  
  
- Un nome univoco. (obbligatorio).  
  
- Due entità [finali dell'associazione](association-end.md), una per ogni tipo di entità nella relazione. (obbligatorio).  
  
    > [!NOTE]
    > Un'associazione non può rappresentare una relazione tra più di due tipi di entità. Un'associazione può tuttavia definire una relazione interna specificando lo stesso tipo di entità per ognuna delle entità finali dell'associazione.  
  
- [Vincolo di integrità referenziale](referential-integrity-constraint.md). (facoltativo)  
  
 Ogni entità finale dell'associazione deve specificare una [molteplicità](association-end-multiplicity.md) di entità finale dell'associazione che indica il numero di istanze del tipo di entità che possono trovarsi in un'entità finale dell'associazione. Una molteplicità di entità finale dell'associazione può avere un valore pari a uno (1), zero o uno (0.. 1)\*o molti (). È possibile accedere alle istanze del tipo di entità in un'entità finale di un'associazione tramite [proprietà di navigazione](navigation-property.md) o chiavi esterne se sono esposte in un tipo di entità. Per ulteriori informazioni, vedere [Entity Data Model: Chiavi](foreign-key-property.md)esterne.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`. Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`. La molteplicità della `Publisher` fine è uno (1) e la molteplicità `Book` dell'entità finale è molti (\*), che indica che un editore pubblica molti libri e un libro viene pubblicato da un solo editore.  
  
 ![Modello di esempio con tre tipi di entità](./media/association-type/example-model-three-entity-types.gif)  
  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
