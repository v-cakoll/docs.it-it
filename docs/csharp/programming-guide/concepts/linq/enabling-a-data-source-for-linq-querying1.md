---
title: Abilitazione di un'origine dati per l'esecuzione di query LINQ
ms.date: 07/20/2015
ms.assetid: d2ef04a5-31a6-45cb-af9a-a5ce7732662c
ms.openlocfilehash: 9a143f0da74d4e91ef697f468d7fda225e75245b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635769"
---
# <a name="enabling-a-data-source-for-linq-querying"></a>Abilitazione di un'origine dati per l'esecuzione di query LINQ
Esistono vari modi per estendere LINQ per consentire a qualsiasi origine dati di eseguire query nel modello LINQ. L'origine dati potrebbe, ad esempio, essere una struttura ad albero dei dati, un servizio Web, un file system o un database. Il modello LINQ consente ai client di eseguire facilmente query su un'origine dati per cui è abilitata l'esecuzione di query LINQ, poiché la sintassi e il modello della query non vengono modificati. Di seguito sono riportati i modi in cui LINQ può essere esteso a queste origini dati:  
  
- Implementazione <xref:System.Collections.Generic.IEnumerable%601> dell'interfaccia in un tipo per abilitare l'esecuzione di query LINQ to Objects di tale tipo.  
  
- Creazione di metodi dell'operatore di query standard, ad esempio <xref:System.Linq.Enumerable.Where%2A> e <xref:System.Linq.Enumerable.Select%2A> che estendono un tipo, per abilitare l'esecuzione di query LINQ personalizzate di tale tipo.  
  
- Creando un provider per l'origine dati che implementi l'interfaccia <xref:System.Linq.IQueryable%601>. Un provider che implementa questa interfaccia riceve query LINQ sotto forma di alberi delle espressioni, che può essere eseguita in modo personalizzato, ad esempio in modalità remota.  
  
- Creazione di un provider per l'origine dati che sfrutta una tecnologia LINQ esistente. Tale provider consentirebbe non solo l'esecuzione di query, ma anche le operazioni di inserimento, aggiornamento ed eliminazione e il mapping per i tipi definiti dall'utente.  
  
 In questo argomento vengono descritte queste opzioni.  
  
## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Come attivare l'esecuzione di query LINQ sull'origine dati  
  
### <a name="in-memory-data"></a>Dati in memoria  
 Esistono due modi per abilitare l'esecuzione di query LINQ di dati in memoria. Se i dati sono di <xref:System.Collections.Generic.IEnumerable%601>un tipo che implementa , è possibile eseguire query sui dati utilizzando LINQ to Objects. Se non ha senso abilitare l'enumerazione <xref:System.Collections.Generic.IEnumerable%601> del tipo implementando l'interfaccia, è possibile definire i metodi dell'operatore di query standard LINQ in tale tipo o creare metodi dell'operatore di query standard LINQ che estendono il tipo. Le implementazioni personalizzate degli operatori di query standard devono utilizzare l'esecuzione posticipata per restituire i risultati.  
  
### <a name="remote-data"></a>Dati remoti  
 L'opzione migliore per abilitare l'esecuzione di <xref:System.Linq.IQueryable%601> query LINQ di un'origine dati remota consiste nell'implementare l'interfaccia. È tuttavia diverso dall'estendere un provider come [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] per un'origine dati. In Visual Studio 2008 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]non sono disponibili modelli di provider per l'estensione delle tecnologie LINQ esistenti, ad esempio , ad altri tipi di origine dati.
  
## <a name="iqueryable-linq-providers"></a>Provider LINQ IQueryable  
 I provider <xref:System.Linq.IQueryable%601> LINQ che implementano possono variare notevolmente nella loro complessità. In questa sezione vengono illustrati i diversi livelli di complessità.  
  
 Un provider `IQueryable` meno complesso potrebbe interfacciarsi con un singolo metodo di un servizio Web. Questo tipo di provider è molto specifico poiché prevede informazioni specifiche nelle query che gestisce. Ha un sistema del tipo chiuso, forse esponendo un solo tipo di risultato. La maggior parte dell'esecuzione della query avviene localmente, utilizzando ad esempio le implementazioni <xref:System.Linq.Enumerable> degli operatori di query standard. Un provider meno complesso potrebbe esaminare solo un'espressione della chiamata al metodo nella struttura ad albero dell'espressione che rappresenta la query facendo sì che la logica rimanente della query venga gestita altrove.  
  
 Un provider `IQueryable` mediamente complesso potrebbe essere destinato a un'origine dati che ha un linguaggio di query parzialmente espressivo. Se è destinato a un servizio Web, potrebbe interagire con più metodi del servizio Web e selezionare il metodo da chiamare in base alla domanda posta dalla query. Un provider mediamente complesso può avere un sistema di tipi più dettagliato rispetto a un provider semplice, ma rimane sempre un sistema di tipi fisso. Ad esempio, il provider può esporre tipi che hanno relazioni uno-a-molti che possono essere attraversate, ma non fornisce la tecnologia di mapping per i tipi definiti dall'utente.  
  
 Un `IQueryable` provider complesso, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] ad esempio il provider, potrebbe convertire le query LINQ complete in un linguaggio di query espressivo, ad esempio SQL. Un provider complesso è più generale di un provider meno complesso, poiché può gestire un'ampia gamma di domande nella query. Ha anche un sistema di tipi aperto e pertanto deve contenere un'infrastruttura completa per eseguire il mapping dei tipi definiti dall'utente. Lo sviluppo di un provider complesso è molto impegnativo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.IQueryable%601>
- <xref:System.Collections.Generic.IEnumerable%601>
- <xref:System.Linq.Enumerable>
- [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)
- [LINQ to Objects (C#)](./linq-to-objects.md)
