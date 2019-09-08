---
title: 'Entity Data Model: Ereditarietà'
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: 21dbdff63c07dbcdac8de7bf4b3a8e5d0ece7901
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784077"
---
# <a name="entity-data-model-inheritance"></a>Entity Data Model: Ereditarietà
Il Entity Data Model (EDM) supporta l'ereditarietà per i [tipi di entità](entity-type.md). L'ereditarietà in EDM è analoga all'ereditarietà per le classi nei linguaggi di programmazione orientati a oggetti. Analogamente a quanto avviene con le classi nei linguaggi orientati a oggetti, in un modello concettuale è possibile definire un tipo di entità (un *tipo derivato*) che eredita da un altro tipo di entità (il *tipo di base*). Tuttavia, a differenza delle classi nella programmazione orientata a oggetti, in un modello concettuale il tipo derivato eredita sempre tutte le [Proprietà](property.md) e le [proprietà di navigazione](navigation-property.md) del tipo di base. Non è possibile eseguire l'override delle proprietà ereditate in un tipo derivato.  
  
 In un modello concettuale è possibile compilare gerarchie di ereditarietà nelle quali un tipo derivato eredita da un altro tipo derivato. Il tipo all'inizio della gerarchia (il tipo nella gerarchia che non è un tipo derivato) viene definito *tipo radice*. In una gerarchia di ereditarietà, la [chiave di entità](entity-key.md) deve essere definita nel tipo radice.  
  
 Non è possibile compilare gerarchie di ereditarietà nelle quali un tipo derivato eredita da più di un tipo. In un modello concettuale con un tipo di entità `Book`, ad esempio, è possibile definire i tipi derivati `FictionBook` e `NonFictionBook` che ereditano ognuno da `Book`. Non è quindi possibile, tuttavia, definire un tipo che eredita sia dal tipo `FictionBook` che dal tipo `NonFictionBook`.  
  
## <a name="example"></a>Esempio  

Nel diagramma seguente viene illustrato un modello concettuale con quattro tipi `Book`di `FictionBook`entità `Publisher`:, `Author`, e. Il tipo di entità `FictionBook` è un tipo derivato, che eredita dal tipo di entità `Book`. Il tipo `FictionBook` eredita le proprietà `ISBN (Key)`, `Title` e `Revision` e definisce una proprietà aggiuntiva chiamata `Genre`.  
  
 ![Diagramma che mostra un modello concettuale con quattro tipi di entità.](./media/entity-data-model-inheritance/entity-type-inheritance.gif)  
  
 Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel seguente linguaggio CSDL viene definito un tipo di entità, `FictionBook`, che eredita dal tipo `Book` (come nel diagramma precedente):  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
