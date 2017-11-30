---
title: "Lettura delle dichiarazioni di entità e dei riferimenti a entità nel DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86dba977-5cc4-4567-964f-027ffabc47b2
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6370db06cbe7ff8d46258b0315059f5c37587fea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a>Lettura delle dichiarazioni di entità e dei riferimenti a entità nel DOM
Un'entità è una dichiarazione che stabilisce il nome da usare in XML al posto del contenuto o del markup. Le entità sono composte da due parti. Innanzitutto, è necessario associare un nome al contenuto di sostituzione tramite una dichiarazione di entità. La dichiarazione di entità viene creata mediante la sintassi `<!ENTITY name "value">` in una DTD (Document Type Definition) o in uno schema XML. Successivamente, il nome definito nella dichiarazione di entità viene usato in XML e, in questo caso, viene denominato riferimento all'entità. Ad esempio, la dichiarazione di entità seguente dichiara un'entità il cui nome `publisher` viene associato al contenuto di "Microsoft Press".  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 Nel seguente esempio è illustrato l'uso di questa dichiarazione di entità in XML come riferimento all'entità.  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 Alcuni parser consentono di espandere automaticamente le entità quando viene caricato un documento in memoria. Quindi, quando l'XML viene letto in memoria, le dichiarazioni di entità vengono memorizzate e salvate. Durante il successivo rilevamento dei caratteri `&;`, che identificano un riferimento a un'entità generale, il parser ricercherà quel determinato nome in una tabella delle dichiarazioni di entità. Il riferimento `&publisher;` verrà sostituito dal contenuto che rappresenta. Usando il seguente codice XML,  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 espandendo il riferimento all'entità e sostituendo `&publisher;` con il contenuto di Microsoft Press viene fornito il seguente codice XML espanso.  
  
 **Output**  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 Esistono molti tipi di entità. Nel diagramma seguente è riportata la suddivisione dei tipi di entità e della terminologia.  
  
 ![diagramma di flusso della gerarchia dei tipi di entità](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")  
  
 Il valore predefinito per l'implementazione di Microsoft .NET Framework dell'oggetto modello DOM (Document XML) è di preservare i riferimenti a entità e non le entità vengono espanse quando si carica il XML. L'implicazione di ciò è che quando un documento viene caricato nel DOM, un **XmlEntityReference** nodo che contiene la variabile di riferimento `&publisher;` viene creato, i nodi figlio che rappresenta il contenuto dell'entità dichiarata nella DTD.  
  
 Utilizzando il `<!ENTITY publisher "Microsoft Press">` dichiarazione di entità, il diagramma seguente mostra il **XmlEntity** e **XmlText** nodi creati da questa dichiarazione.  
  
 ![nodi creati da dichiarazioni di entità](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")  
  
 Il fatto che i riferimenti alle entità vengano espansi o meno determina quali nodi vengono generati nell'albero DOM, in memoria. La differenza tra i nodi generati è descritta negli argomenti [riferimenti alle entità conservati](../../../../docs/standard/data/xml/entity-references-are-preserved.md) e [i riferimenti alle entità vengono espansi e non conservati](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
