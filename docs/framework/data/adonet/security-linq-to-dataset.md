---
title: Sicurezza (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
ms.openlocfilehash: d6f00fccb0ea2f49c19b640e31d96e575c0d48b9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782790"
---
# <a name="security-linq-to-dataset"></a>Sicurezza (LINQ to DataSet)
In questo argomento vengono illustrati i problemi di sicurezza in LINQ to DataSet.  
  
## <a name="passing-a-query-to-an-untrusted-component"></a>Passaggio di una query a un componente non attendibile  
 Una query di LINQ to DataSet può essere formulata in un punto di un programma ed eseguita in una diversa. Nel punto in cui viene formulata, la query può fare riferimento a qualsiasi elemento visibile, ovvero membri private della classe cui appartiene il metodo chiamante oppure simboli che rappresentano variabili/argomenti locali. In fase di esecuzione la query sarà effettivamente in grado di accedere ai membri cui è stato fatto riferimento durante la formulazione anche se tali membri non sono visibili al codice di chiamata. Il codice che esegue la query non dispone di visibilità arbitraria aggiunta, in quanto non è in grado di scegliere gli elementi cui accedere. Può infatti accedere esclusivamente agli elementi accessibili alla query e solo tramite la query stessa.  
  
 Se pertanto un riferimento a una query viene passato a un'altra porzione di codice, il componente che riceve la query viene ritenuto attendibile e può accedere a tutti i membri public e private cui fa riferimento la query. In generale, le query LINQ to DataSet non devono essere passate a componenti non attendibili, a meno che la query non sia stata costruita con attenzione in modo da non esporre le informazioni che devono essere mantenute private.  
  
## <a name="external-input"></a>Input esterno  
 Le applicazioni accettano spesso input esterno, ad esempio da un utente o da un altro agente esterno, ed eseguono azioni sulla base di tale input.  Nel caso di LINQ to DataSet, l'applicazione potrebbe creare una query in un certo modo, in base all'input esterno o usare input esterno nella query. LINQ to DataSet le query accettano parametri ovunque siano accettati i valori letterali. Gli sviluppatori di applicazioni devono usare query con parametri, anziché inserire valori letterali direttamente nella query tramite un agente esterno.  
  
 Eventuale input derivato in modo diretto o indiretto dall'utente o da un agente esterno può includere contenuto che sfrutta la sintassi del linguaggio di destinazione per eseguire azioni non autorizzate. Tale fenomeno è noto come attacco SQL injection, il cui nome deriva da uno schema di attacco in cui il linguaggio di destinazione è Transact-SQL. L'input utente inserito direttamente nella query viene usato per rimuovere una tabella di database, determinare un attacco di tipo Denial of Service o alterare in altro modo la natura dell'operazione da eseguire. Sebbene la composizione di query sia possibile in LINQ to DataSet, viene eseguita tramite l'API del modello a oggetti. LINQ to DataSet le query non vengono composte mediante la manipolazione o la concatenazione di stringhe, come avviene in Transact-SQL, e non sono soggette ad attacchi intrusivi nel codice SQL nel senso tradizionale.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori](programming-guide-linq-to-dataset.md)
