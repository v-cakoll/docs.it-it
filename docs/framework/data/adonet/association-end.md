---
title: entità finale dell'associazione
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 489802ca18708e076c0cd5dd380ad1361916ad5f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732367"
---
# <a name="association-end"></a>entità finale dell'associazione
Un'entità *finale dell'associazione* identifica il tipo di entità in un' [entità](entity-type.md) finale di un' [associazione](association-type.md) e il numero di istanze del tipo di entità che possono esistere a tale estremità di un'associazione. Le entità finali dell'associazione sono definite come parte di un'associazione; un'associazione deve disporre esattamente di due entità finali. Le [proprietà di navigazione](navigation-property.md) consentono l'esplorazione da un'entità finale dell'associazione all'altra.  
  
 Una definizione di entità finale dell'associazione contiene le informazioni seguenti:  
  
- Uno dei tipi di entità coinvolti nell'associazione (obbligatorio).  
  
    > [!NOTE]
    > Per una determinata associazione, il tipo di entità specificato per ogni entità finale dell'associazione può essere lo stesso. In questo modo viene creata un'associazione interna.  
  
- [Molteplicità](association-end-multiplicity.md) di entità finale dell'associazione che indica il numero di istanze del tipo di entità che possono trovarsi in un'entità finale dell'associazione. Una molteplicità di entità finale dell'associazione può avere un valore pari a uno (1), zero o uno (0.. 1) o molti (\*).  
  
- Nome per l'entità finale dell'associazione. (facoltativo)  
  
- Informazioni sulle operazioni eseguite sull'entità finale dell'associazione, ad esempio cascade on delete (facoltativo)  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`. Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`. La molteplicità del `Publisher` end è uno (1) e la molteplicità dell'estremità `Book` è molti (\*), a indicare che un editore pubblica molti libri e un libro viene pubblicato da un solo editore.  
  
 ![Modello di esempio con tre tipi di entità](./media/association-end/example-model-three-entity-types.gif)  
  
 Il Entity Framework ADO.NET utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente. Si noti che il tipo, il nome e la molteplicità di ogni entità finale dell'associazione vengono specificati dagli attributi XML (rispettivamente, gli attributi `Type`, `Role` e `Multiplicity`). Le informazioni facoltative sulle operazioni eseguite su un'entità finale vengono specificate in un elemento XML (l'elemento `OnDelete`). In questo caso, se viene eliminato un editore, vengono eliminati anche tutti i libri associati.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
