---
title: Abilitazione di un'origine dati per l'esecuzione di query LINQ1
ms.date: 07/20/2015
ms.assetid: d2ef04a5-31a6-45cb-af9a-a5ce7732662c
ms.openlocfilehash: 1aa3a22028b0b3d7c705076a3e16379e09323271
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49122699"
---
# <a name="enabling-a-data-source-for-linq-querying"></a>Abilitazione di un'origine dati per l'esecuzione di query LINQ
Esistono diversi modi per estendere [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in modo da consentire l'esecuzione di una query su un'origine dati nel modello [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. L'origine dati potrebbe, ad esempio, essere una struttura ad albero dei dati, un servizio Web, un file system o un database. Il modello [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consente ai client di eseguire una query su un'origine dati per la quale è attivata l'esecuzione di query[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], poiché la sintassi e il modello della query non vengono modificati. Di seguito vengono riportati i modi in cui è possibile estendere [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] a queste origini dati:  
  
-   Implementando l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> in un tipo in modo da consentire l'esecuzione di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects per quel tipo.  
  
-   Creando metodi degli operatori query standard, ad esempio <xref:System.Linq.Enumerable.Where%2A> e <xref:System.Linq.Enumerable.Select%2A>, che estendono un tipo in modo da consentire l'esecuzione di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] personalizzate per quel tipo.  
  
-   Creando un provider per l'origine dati che implementi l'interfaccia <xref:System.Linq.IQueryable%601>. Un provider che implementa questa interfaccia riceve le query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sotto forma di strutture ad albero dell'espressione, che possono essere eseguite in modo personalizzato, ad esempio in modalità remota.  
  
-   Creazione di un provider per l'origine dati in grado di sfruttare una tecnologia [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] esistente. Tale provider consentirebbe non solo l'esecuzione di query, ma anche le operazioni di inserimento, aggiornamento ed eliminazione e il mapping per i tipi definiti dall'utente.  
  
 In questo argomento vengono descritte queste opzioni.  
  
## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Come attivare l'esecuzione di query LINQ sull'origine dati  
  
### <a name="in-memory-data"></a>Dati in memoria  
 Per consentire l'esecuzione di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sui dati in memoria sono disponibili due modi. Se il tipo di dati implementa <xref:System.Collections.Generic.IEnumerable%601>, è possibile eseguire una query sui dati utilizzando [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects. Se non ha senso abilitare l'enumerazione del tipo implementando l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, è possibile definire i metodi degli operatori query standard [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in quel tipo oppure creare metodi degli operatori query standard [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] che estendono il tipo. Le implementazioni personalizzate degli operatori di query standard devono utilizzare l'esecuzione posticipata per restituire i risultati.  
  
### <a name="remote-data"></a>Dati remoti  
 L'opzione migliore per abilitare l'esecuzione di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] su un'origine dati remota consiste nell'implementare l'interfaccia <xref:System.Linq.IQueryable%601>. È tuttavia diverso dall'estendere un provider come [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] per un'origine dati. In Visual Studio 2008 non sono disponibili modelli di provider per l'estensione di tecnologie [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] esistenti, ad esempio [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], ad altri tipi di origine dati.
  
## <a name="iqueryable-linq-providers"></a>Provider LINQ IQueryable  
 I provider [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] che implementano <xref:System.Linq.IQueryable%601> possono variare notevolmente per quanto riguarda la complessità. In questa sezione vengono illustrati i diversi livelli di complessità.  
  
 Un provider `IQueryable` meno complesso potrebbe interfacciarsi con un singolo metodo di un servizio Web. Questo tipo di provider è molto specifico poiché prevede informazioni specifiche nelle query che gestisce. Ha un sistema del tipo chiuso, forse esponendo un solo tipo di risultato. La maggior parte dell'esecuzione della query avviene localmente, utilizzando ad esempio le implementazioni <xref:System.Linq.Enumerable> degli operatori di query standard. Un provider meno complesso potrebbe esaminare solo un'espressione della chiamata al metodo nella struttura ad albero dell'espressione che rappresenta la query facendo sì che la logica rimanente della query venga gestita altrove.  
  
 Un provider `IQueryable` mediamente complesso potrebbe essere destinato a un'origine dati che ha un linguaggio di query parzialmente espressivo. Se è destinato a un servizio Web, potrebbe interagire con più metodi del servizio Web e selezionare il metodo da chiamare in base alla domanda posta dalla query. Un provider mediamente complesso può avere un sistema di tipi più dettagliato rispetto a un provider semplice, ma rimane sempre un sistema di tipi fisso. Ad esempio, il provider può esporre tipi che hanno relazioni uno-a-molti che possono essere attraversate, ma non fornisce la tecnologia di mapping per i tipi definiti dall'utente.  
  
 Un provider `IQueryable` complesso, ad esempio il provider [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], può convertire le query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] complete in un linguaggio di query espressivo, ad esempio SQL. Un provider complesso è più generale di un provider meno complesso, poiché può gestire un'ampia gamma di domande nella query. Ha anche un sistema di tipi aperto e pertanto deve contenere un'infrastruttura completa per eseguire il mapping dei tipi definiti dall'utente. Lo sviluppo di un provider complesso è molto impegnativo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.IQueryable%601>  
- <xref:System.Collections.Generic.IEnumerable%601>  
- <xref:System.Linq.Enumerable>  
- [Cenni preliminari sugli operatori di query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
