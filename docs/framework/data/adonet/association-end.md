---
title: entità finale dell'associazione
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: e549254533f8362ce3475fb3aa5dbaffb3e900e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769615"
---
# <a name="association-end"></a>entità finale dell'associazione
Un' *finale dell'associazione* identifica le [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) sul uno lato di una [associazione](../../../../docs/framework/data/adonet/association-type.md) e il numero di istanze che possono essere presenti in tale entità finale di un'associazione del tipo di entità. Le entità finali dell'associazione sono definite come parte di un'associazione; un'associazione deve disporre esattamente di due entità finali. [Le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) consentono di navigare da un'estremità dell'associazione a altra.  
  
 Una definizione di entità finale dell'associazione contiene le informazioni seguenti:  
  
- Uno dei tipi di entità coinvolti nell'associazione (obbligatorio).  
  
    > [!NOTE]
    >  Per una determinata associazione, il tipo di entità specificato per ogni entità finale dell'associazione può essere lo stesso. In questo modo viene creata un'associazione interna.  
  
- Un' [molteplicità di estremità dell'associazione](../../../../docs/framework/data/adonet/association-end-multiplicity.md) che indica il numero di istanze del tipo di entità che possono essere in un'entità finale dell'associazione. Una molteplicità di entità finale di associazione può avere un valore di uno (1), zero o uno (0..1) o molti (\*).  
  
- Nome per l'entità finale dell'associazione. (facoltativo)  
  
- Informazioni sulle operazioni eseguite sull'entità finale dell'associazione, ad esempio cascade on delete (facoltativo)  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`. Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`. La molteplicità del `Publisher` finale è uno (1) e la molteplicità dell'entità la `Book` finale è molti (\*), che indica che un editore pubblica molti libri e un libro viene pubblicato da un server di pubblicazione.  
  
 ![Modello di esempio con tre tipi di entità](./media/association-end/example-model-three-entity-types.gif)  
  
 ADO.NET Entity Framework Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente. Si noti che il tipo, il nome e la molteplicità di ogni entità finale dell'associazione vengono specificati dagli attributi XML (rispettivamente, gli attributi `Type`, `Role` e `Multiplicity`). Le informazioni facoltative sulle operazioni eseguite su un'entità finale vengono specificate in un elemento XML (l'elemento `OnDelete`). In questo caso, se viene eliminato un editore, vengono eliminati anche tutti i libri associati.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
