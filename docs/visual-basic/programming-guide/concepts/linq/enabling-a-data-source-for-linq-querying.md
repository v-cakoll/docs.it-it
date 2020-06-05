---
title: Abilitazione di un'origine dati per Querying2 LINQ
ms.date: 07/20/2015
ms.assetid: c412f0cf-ff0e-4993-ab3d-1b49e23f00f8
ms.openlocfilehash: 4ab0e2a2fc3d04eb375a4646e4133e6e5cbb47db
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375304"
---
# <a name="enabling-a-data-source-for-linq-querying"></a>Abilitazione di un'origine dati per l'esecuzione di query LINQ

Sono disponibili diversi modi per estendere LINQ in modo da consentire la query su qualsiasi origine dati nel modello LINQ. L'origine dati potrebbe, ad esempio, essere una struttura ad albero dei dati, un servizio Web, un file system o un database. Il modello LINQ rende più semplice per i client eseguire una query su un'origine dati per cui è abilitata l'esecuzione di query LINQ, perché la sintassi e il modello della query non cambiano. I modi in cui LINQ può essere esteso a queste origini dati sono i seguenti:

- Implementazione dell' <xref:System.Collections.Generic.IEnumerable%601> interfaccia in un tipo per abilitare LINQ to Objects l'esecuzione di query su quel tipo.

- Creazione di metodi di operatori di query standard, ad esempio <xref:System.Linq.Enumerable.Where%2A> e <xref:System.Linq.Enumerable.Select%2A> , che estendono un tipo, per consentire l'esecuzione di query LINQ personalizzate su tale tipo.

- Creando un provider per l'origine dati che implementi l'interfaccia <xref:System.Linq.IQueryable%601>. Un provider che implementa questa interfaccia riceve le query LINQ sotto forma di alberi delle espressioni, che può essere eseguito in modo personalizzato, ad esempio in modalità remota.

- Creazione di un provider per l'origine dati che sfrutta una tecnologia LINQ esistente. Tale provider consentirebbe non solo l'esecuzione di query, ma anche le operazioni di inserimento, aggiornamento ed eliminazione e il mapping per i tipi definiti dall'utente.

In questo argomento vengono descritte queste opzioni.

## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Come attivare l'esecuzione di query LINQ sull'origine dati

### <a name="in-memory-data"></a>Dati in memoria
 Esistono due modi per abilitare l'esecuzione di query LINQ sui dati in memoria. Se i dati sono di un tipo che implementa <xref:System.Collections.Generic.IEnumerable%601> , è possibile eseguire una query sui dati utilizzando LINQ to Objects. Se non ha senso abilitare l'enumerazione del tipo implementando l' <xref:System.Collections.Generic.IEnumerable%601> interfaccia, è possibile definire i metodi degli operatori di query standard LINQ in quel tipo o creare metodi dell'operatore di query standard LINQ che estendono il tipo. Le implementazioni personalizzate degli operatori di query standard devono utilizzare l'esecuzione posticipata per restituire i risultati.

### <a name="remote-data"></a>Dati remoti
 L'opzione migliore per abilitare l'esecuzione di query LINQ su un'origine dati remota consiste nell'implementare l' <xref:System.Linq.IQueryable%601> interfaccia. È tuttavia diverso dall'estendere un provider come [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] per un'origine dati. In Visual Studio 2008 non sono disponibili modelli di provider per l'estensione di tecnologie LINQ esistenti, ad esempio [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] , ad altri tipi di origine dati.

## <a name="iqueryable-linq-providers"></a>Provider LINQ IQueryable
 I provider LINQ che implementano <xref:System.Linq.IQueryable%601> possono variare notevolmente nella loro complessità. In questa sezione vengono illustrati i diversi livelli di complessità.

 Un provider `IQueryable` meno complesso potrebbe interfacciarsi con un singolo metodo di un servizio Web. Questo tipo di provider è molto specifico poiché prevede informazioni specifiche nelle query che gestisce. Ha un sistema del tipo chiuso, forse esponendo un solo tipo di risultato. La maggior parte dell'esecuzione della query avviene localmente, utilizzando ad esempio le implementazioni <xref:System.Linq.Enumerable> degli operatori di query standard. Un provider meno complesso potrebbe esaminare solo un'espressione della chiamata al metodo nella struttura ad albero dell'espressione che rappresenta la query facendo sì che la logica rimanente della query venga gestita altrove.

 Un provider `IQueryable` mediamente complesso potrebbe essere destinato a un'origine dati che ha un linguaggio di query parzialmente espressivo. Se è destinato a un servizio Web, potrebbe interagire con più metodi del servizio Web e selezionare il metodo da chiamare in base alla domanda posta dalla query. Un provider mediamente complesso può avere un sistema di tipi più dettagliato rispetto a un provider semplice, ma rimane sempre un sistema di tipi fisso. Ad esempio, il provider può esporre tipi che hanno relazioni uno-a-molti che possono essere attraversate, ma non fornisce la tecnologia di mapping per i tipi definiti dall'utente.

 Un `IQueryable` provider complesso, ad esempio il [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] provider, potrebbe tradurre le query LINQ complete in un linguaggio di query espressivo, ad esempio SQL. Un provider complesso è più generale di un provider meno complesso, poiché può gestire un'ampia gamma di domande nella query. Ha anche un sistema di tipi aperto e pertanto deve contenere un'infrastruttura completa per eseguire il mapping dei tipi definiti dall'utente. Lo sviluppo di un provider complesso è molto impegnativo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.IQueryable%601>
- <xref:System.Collections.Generic.IEnumerable%601>
- <xref:System.Linq.Enumerable>
- [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)
- [LINQ to Objects (Visual Basic)](linq-to-objects.md)
