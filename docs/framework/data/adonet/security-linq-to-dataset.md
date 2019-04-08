---
title: Sicurezza (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
ms.openlocfilehash: aa281cb4d6019ca2df85137eb505724e55b8060a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087334"
---
# <a name="security-linq-to-dataset"></a>Sicurezza (LINQ to DataSet)
In questo argomento vengono illustrati i problemi di sicurezza riscontrati in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  
  
## <a name="passing-a-query-to-an-untrusted-component"></a>Passaggio di una query a un componente non attendibile  
 Oggetto [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query possono essere formulate in un punto di un programma ed eseguiti in uno diverso. Nel punto in cui viene formulata, la query può fare riferimento a qualsiasi elemento visibile, ovvero membri private della classe cui appartiene il metodo chiamante oppure simboli che rappresentano variabili/argomenti locali. In fase di esecuzione la query sarà effettivamente in grado di accedere ai membri cui è stato fatto riferimento durante la formulazione anche se tali membri non sono visibili al codice di chiamata. Il codice che esegue la query non dispone di visibilità arbitraria aggiunta, in quanto non è in grado di scegliere gli elementi cui accedere. Può infatti accedere esclusivamente agli elementi accessibili alla query e solo tramite la query stessa.  
  
 Se pertanto un riferimento a una query viene passato a un'altra porzione di codice, il componente che riceve la query viene ritenuto attendibile e può accedere a tutti i membri public e private cui fa riferimento la query. In generale, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query non deve essere passata ai componenti non attendibili, a meno che la query è stata costruita con attenzione in modo che non espone informazioni che devono essere mantenute private.  
  
## <a name="external-input"></a>Input esterno  
 Le applicazioni accettano spesso input esterno, ad esempio da un utente o da un altro agente esterno, ed eseguono azioni sulla base di tale input.  Nel caso di [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], l'applicazione può costruire una query in un modo specifico, basato su input esterno oppure usare input nella query esterno. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] le query accettano parametri ovunque che vengono accettati i valori letterali. Gli sviluppatori di applicazioni devono usare query con parametri, anziché inserire valori letterali direttamente nella query tramite un agente esterno.  
  
 Eventuale input derivato in modo diretto o indiretto dall'utente o da un agente esterno può includere contenuto che sfrutta la sintassi del linguaggio di destinazione per eseguire azioni non autorizzate. Tale fenomeno è noto come attacco SQL injection, il cui nome deriva da uno schema di attacco in cui il linguaggio di destinazione è Transact-SQL. L'input utente inserito direttamente nella query viene usato per rimuovere una tabella di database, determinare un attacco di tipo Denial of Service o alterare in altro modo la natura dell'operazione da eseguire. Sebbene la composizione di query sia possibile in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], essa viene eseguita attraverso l'API del modello a oggetti. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] non vengono composte mediante la manipolazione o la concatenazione, come avviene in Transact-SQL e non sono soggette agli attacchi SQL injection in senso tradizionale.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
