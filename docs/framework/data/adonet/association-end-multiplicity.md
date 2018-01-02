---
title: "molteplicità di entità finale dell'associazione"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0d66c141b83402b011fdebbb04c0b2a9adc5ec29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="association-end-multiplicity"></a>molteplicità di entità finale dell'associazione
*Molteplicità di entità finale associazione* definisce il numero di [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) istanze che possono essere a un estremo di una [associazione](../../../../docs/framework/data/adonet/association-type.md).  
  
 Una molteplicità di entità finale dell'associazione può disporre di uno dei valori seguenti:  
  
-   uno (1): indica che nell'entità finale dell'associazione è presente esattamente un'istanza del tipo di entità.  
  
-   zero o uno (0..1): indica che nell'entità finale dell'associazione sono presenti zero o una istanza del tipo di entità.  
  
-   molte (*): indica che nell'entità finale dell'associazione sono presenti zero, una o più istanze del tipo di entità.  
  
 Un'associazione è spesso caratterizzata dalle molteplicità di entità finale dell'associazione. Se, ad esempio, le entità finali di un'associazione dispongono di molteplicità uno (1) e molti (*), l'associazione è detta associazione uno-a-molti. Nell'esempio seguente, l'associazione `PublishedBy` è un'associazione uno-a-molti (un editore pubblica molti libri e un libro viene pubblicato da un solo editore). L'associazione `WrittenBy` è un'associazione molti-a-molti (un libro può avere più autori e un autore può scrivere più libri).  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`. Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`. La molteplicità dell'entità finale `Publisher` è uno (1) e la molteplicità dell'entità finale `Book` è molti (*).  
  
 ![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 ADO.NET Entity Framework Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
