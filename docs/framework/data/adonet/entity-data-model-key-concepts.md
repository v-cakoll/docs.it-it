---
title: Concetti chiave di Entity Data Model
ms.date: 03/30/2017
ms.assetid: c635a16d-6674-45aa-9344-dcb7df992bab
ms.openlocfilehash: b3a2f8eb9fa5b83eec5ba7c2a56c348d050d1938
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737826"
---
# <a name="entity-data-model-key-concepts"></a>Concetti chiave di Entity Data Model
Il Entity Data Model (EDM) utilizza tre concetti chiave per descrivere la struttura dei dati, ovvero il *tipo di entità*, il *tipo di associazione*e la *proprietà*. Si tratta dei concetti più importanti nella descrizione della struttura di dati in qualsiasi implementazione di EDM.  
  
## <a name="entity-type"></a>Tipo di entità  
 Il [tipo di entità](entity-type.md) è il blocco predefinito fondamentale per descrivere la struttura dei dati con l'Entity Data Model. In un modello concettuale, i tipi di entità vengono costruiti dalle [Proprietà](property.md) e descrivono la struttura dei concetti di primo livello, ad esempio i clienti e gli ordini in un'applicazione aziendale. Esattamente come una definizione di classe in un programma informatico è un modello per le istanze della classe, un tipo di entità è un modello per le entità. Un'entità rappresenta un oggetto specifico (ad esempio un cliente o un ordine specifico). Ogni entità deve avere una [chiave di entità](entity-key.md) univoca all'interno di un [set di entità](entity-set.md).  Un set di entità è una raccolta di istanze di un tipo di entità specifico. I set di entità e i [set di associazioni](association-set.md)sono raggruppati logicamente in un [contenitore di entità](entity-container.md).  
  
 L'ereditarietà è supportata con i tipi di entità, ovvero un tipo di entità può essere derivato da un altro. Per ulteriori informazioni, vedere [Entity Data Model: ereditarietà](entity-data-model-inheritance.md).  
  
## <a name="association-type"></a>Tipo di associazione  
 Un [tipo di associazione](association-type.md) (detto anche associazione) è il blocco predefinito fondamentale per la descrizione delle relazioni nell'Entity Data Model. In un modello concettuale, un'associazione rappresenta una relazione tra due tipi di entità (ad esempio, Customer e Order). Ogni associazione dispone di due entità [finali di associazione](association-end.md) che specificano i tipi di entità necessari per l'associazione. Ogni entità finale dell'associazione specifica anche una [molteplicità](association-end-multiplicity.md) di entità finale dell'associazione che indica il numero di entità che possono trovarsi a tale entità finale dell'associazione. Una molteplicità di entità finale dell'associazione può avere un valore pari a uno (1), zero o uno (0.. 1) o molti (\*). È possibile accedere alle entità a un'estremità di un'associazione tramite [proprietà di navigazione](navigation-property.md)o chiavi esterne se sono esposte in un tipo di entità. Per ulteriori informazioni, vedere [proprietà di chiave esterna](foreign-key-property.md).  
  
 In un'applicazione, un'istanza di un'associazione rappresenta un'associazione specifica (ad esempio, un'associazione tra un'istanza relativa al cliente e istanze relative all'ordine). Le istanze di associazione vengono raggruppate logicamente in un [set di associazioni](association-set.md). I set di associazioni e i [set di entità](entity-set.md)sono raggruppati logicamente in un [contenitore di entità](entity-container.md).  
  
## <a name="property"></a>proprietà  
 I [tipi di entità](entity-type.md) contengono [Proprietà](property.md) che definiscono la struttura e le caratteristiche. È, ad esempio, possibile che un tipo di entità Customer disponga di proprietà quali CustomerId, Name e Address.  
  
 Le proprietà in un modello concettuale sono analoghe alle proprietà definite su una classe in un programma informatico. Nello stesso modo in cui le proprietà su una classe definiscono la forma della classe e forniscono informazioni su oggetti, le proprietà in un modello concettuale definiscono la forma di un tipo di entità e forniscono informazioni su istanze del tipo di entità.  
  
 Una proprietà può contenere dati primitivi (ad esempio una stringa, un Integer o un valore booleano) o dati strutturati (ad esempio un tipo complesso). Per ulteriori informazioni, vedere [Entity Data Model: tipi di dati primitivi](entity-data-model-primitive-data-types.md).  
  
## <a name="representations-of-a-conceptual-model"></a>Rappresentazioni di un modello concettuale  
 Un *modello concettuale* è una rappresentazione specifica della struttura di alcuni dati come entità e relazioni. È possibile rappresentare un modello concettuale tramite un diagramma. Nel diagramma seguente viene rappresentato un modello concettuale con tre tipi di entità (`Book`, `Publisher` e `Author`) e due associazioni (`PublishedBy` e `WrittenBy`):  
  
 ![Diagramma che illustra un modello concettuale con tre tipi di entità.](./media/entity-data-model-key-concepts/conceptual-model-entity-types-associations.gif)  
  
 Questa rappresentazione, tuttavia, presenta alcuni difetti quando è necessario illustrare alcuni dettagli relativi al modello. Le informazioni sul tipo di proprietà e sul set di entità, ad esempio, non sono illustrate nel diagramma. La ricchezza di un modello concettuale può essere illustrata più chiaramente con un linguaggio DSL. Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio DSL basato su XML denominato *Conceptual Schema Definition Language* ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali. Di seguito è riportata la definizione CSDL del modello concettuale nel diagramma precedente:  
  
 [!code-xml[EDM_Example_Model#EDMExampleCSDL](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#edmexamplecsdl)]  
  
## <a name="see-also"></a>Vedere anche

- [Entity Data Model](entity-data-model.md)
