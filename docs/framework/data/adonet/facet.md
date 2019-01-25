---
title: facet
ms.date: 03/30/2017
ms.assetid: 91c4e6aa-3e54-4b6c-a38a-abf27808cc85
ms.openlocfilehash: 9994aff7337dd842e1d70c22ea288d2fda5648d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648232"
---
# <a name="facet"></a>facet
Oggetto *facet* viene usato per aggiungere dettagli alla definizione di una proprietà di tipo primitivo. Oggetto [proprietà](../../../../docs/framework/data/adonet/property.md) definizione contiene informazioni sul tipo di proprietà, ma spesso sono necessari ulteriori dettagli. Un tipo di entità in un modello concettuale, ad esempio, potrebbe disporre di una proprietà di tipo `String` il cui valore non può essere impostato su null. I facet consentono di specificare questo livello di dettaglio.  
  
 Nella tabella seguente vengono descritti i facet supportati in EDM.  
  
> [!NOTE]
>  I valori e i comportamenti esatti dei facet sono determinati dall'ambiente di runtime che usa un'implementazione EDM.  
  
|Facet|Descrizione|Si applica a|  
|-----------|-----------------|----------------|  
|`Collation`|Specifica la sequenza di ordinamento da usare quando si eseguono operazioni di confronto e di ordinamento su valori della proprietà.|`String`|  
|`ConcurrencyMode`|Indica che il valore della proprietà deve essere usato per le verifiche della concorrenza ottimistica.|Tutte le proprietà di tipo primitivo|  
|`Default`|Specifica il valore predefinito della proprietà se durante la creazione di istanze non viene fornito alcun valore.|Tutte le proprietà di tipo primitivo|  
|`FixedLength`|Specifica se la lunghezza del valore della proprietà può variare.|`Binary`, `String`|  
|`MaxLength`|Specifica la lunghezza massima del valore della proprietà.|`Binary`, `String`|  
|`Nullable`|Specifica se la proprietà può avere un valore null.|Tutte le proprietà di tipo primitivo|  
|`Precision`|Per le proprietà di tipo `Decimal`, specifica il numero di cifre che un valore della proprietà può avere. Per le proprietà di tipo `Time`, `DateTime` e `DateTimeOffset`, specifica il numero di cifre per la parte frazionaria di secondi del valore della proprietà.|`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,|  
|`Scale`|Specifica il numero di cifre a destra del separatore decimale per il valore della proprietà.|Decimal|  
|`Unicode`|Viene indicato se il valore della proprietà viene archiviato come Unicode.|`String`|  
  
## <a name="example"></a>Esempio  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Nel linguaggio CSDL seguente viene definito un tipo di entità `Book`. Si noti che i facet vengono implementati come attributi XML. I valori dei facet indicano che nessuna proprietà può essere impostata su null e che `Scale` e `Precision` della proprietà `Revision` sono entrambi impostati su 29.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Vedere anche
- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
