---
title: tipo di associazione
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: e1430e6255dce2bae6d82411db5d2a9f11f46e1a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738560"
---
# <a name="association-type"></a>tipo di associazione
Un *tipo di associazione* (detto anche associazione) è il blocco predefinito fondamentale per la descrizione delle relazioni nell'Entity Data Model (EDM). In un modello concettuale, un'associazione rappresenta una relazione tra due [tipi di entità](entity-type.md) , ad esempio `Customer` e `Order`. In un'applicazione, un'istanza di un'associazione rappresenta un'associazione specifica (ad esempio, un'associazione tra un'istanza di `Customer` e una di `Order`). Le istanze di associazione vengono raggruppate logicamente in un [set di associazioni](association-set.md).  
  
 Una definizione di associazione contiene le informazioni seguenti:  
  
- Un nome univoco. (obbligatorio).  
  
- Due entità [finali dell'associazione](association-end.md), una per ogni tipo di entità nella relazione. (obbligatorio).  
  
    > [!NOTE]
    > Un'associazione non può rappresentare una relazione tra più di due tipi di entità. Un'associazione può tuttavia definire una relazione interna specificando lo stesso tipo di entità per ognuna delle entità finali dell'associazione.  
  
- [Vincolo di integrità referenziale](referential-integrity-constraint.md). (facoltativo)  
  
 Ogni entità finale dell'associazione deve specificare una [molteplicità](association-end-multiplicity.md) di entità finale dell'associazione che indica il numero di istanze del tipo di entità che possono trovarsi in un'entità finale dell'associazione. Una molteplicità di entità finale dell'associazione può avere un valore pari a uno (1), zero o uno (0.. 1) o molti (\*). È possibile accedere alle istanze del tipo di entità in un'entità finale di un'associazione tramite [proprietà di navigazione](navigation-property.md) o chiavi esterne se sono esposte in un tipo di entità. Per ulteriori informazioni, vedere [Entity Data Model: chiavi esterne](foreign-key-property.md).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`. Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`. La molteplicità del `Publisher` end è uno (1) e la molteplicità dell'estremità `Book` è molti (\*), a indicare che un editore pubblica molti libri e un libro viene pubblicato da un solo editore.  
  
 ![Modello di esempio con tre tipi di entità](./media/association-type/example-model-three-entity-types.gif)  
  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
