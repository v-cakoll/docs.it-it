---
title: proprietà
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: 59b4ccf18b0e1f9054fd2a253fcd39072ed10e98
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946284"
---
# <a name="property"></a>proprietà
Le *Proprietà* sono i blocchi predefiniti fondamentali di [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md) e [tipi complessi](../../../../docs/framework/data/adonet/complex-type.md). Le proprietà definiscono la forma e le caratteristiche dei dati che saranno contenuti in un'istanza di un tipo di entità o in un'istanza di un tipo complesso. Le proprietà in un modello concettuale sono analoghe alle proprietà definite su una classe. Nello stesso modo in cui le proprietà su una classe definiscono la forma della classe e forniscono informazioni su oggetti, le proprietà in un modello concettuale definiscono la forma di un tipo di entità e forniscono informazioni su istanze del tipo di entità.  
  
> [!NOTE]
> Le proprietà descritte in questo argomento sono diverse dalle proprietà di navigazione. Per ulteriori informazioni, vedere [proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md).  
  
 Una definizione di proprietà contiene le informazioni seguenti:  
  
- Un nome di proprietà (obbligatorio).  
  
- Un tipo di proprietà (obbligatorio).  
  
- Set di [facet](../../../../docs/framework/data/adonet/facet.md). (facoltativo)  
  
 Una proprietà può contenere dati primitivi (ad esempio una stringa, un Integer o un valore booleano) o dati strutturati (ad esempio un tipo complesso). Le proprietà di tipo primitivo sono dette anche proprietà scalari. Per ulteriori informazioni, vedere [Entity Data Model: Tipi](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)di dati primitivi.  
  
> [!NOTE]
> Un tipo complesso può, di per sé, disporre di proprietà che sono tipi complessi.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`. Ogni tipo di entità dispone di diverse proprietà, anche se nel diagramma non sono contenute informazioni sul tipo per ogni proprietà. Le proprietà che sono [chiavi di entità](../../../../docs/framework/data/adonet/entity-key.md) sono denotate con (chiave).  
  
 ![Modello di esempio con tre tipi di entità](./media/property/example-model-three-entity-types.gif)  
  
 Il [Entity Framework ADO.NET](../../../../docs/framework/data/adonet/ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il seguente linguaggio CSDL definisce il tipo di entità `Book` (come illustrato nel diagramma precedente) e indica il tipo e il nome di ogni proprietà usando attributi XML. Un facet facoltativo, `Nullable`, è definito anche tramite un attributo XML.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 È possibile che una delle proprietà illustrate nel diagramma sia una proprietà di tipo complesso. La proprietà `Address` sul tipo di entità `Publisher`, ad esempio, potrebbe essere una proprietà di tipo complesso costituita da diverse proprietà scalari, quali `StreetAddress`, `City`, `StateOrProvince`, `Country` e `PostalCode`. La rappresentazione CSDL di tale tipo complesso sarà come segue:  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
