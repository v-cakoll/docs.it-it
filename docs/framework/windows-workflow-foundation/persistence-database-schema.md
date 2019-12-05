---
title: Schema di database di persistenza
ms.date: 03/30/2017
ms.assetid: 34f69f4c-df81-4da7-b281-a525a9397a5c
ms.openlocfilehash: 025e04acb0d9cf75ea54814274c1875f8661eb88
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802505"
---
# <a name="persistence-database-schema"></a>Schema di database di persistenza
In questo argomento vengono descritte le visualizzazioni pubbliche supportate dall'archivio di istanze del flusso di lavoro SQL.  
  
## <a name="instances-view"></a>Visualizzazione Istanze  
 Nella visualizzazione **istanze** sono contenute informazioni generali su tutte le istanze del flusso di lavoro nel database.  
  
|Nome colonna|Tipo di colonna|Descrizione|  
|-----------------|-----------------|-----------------|  
|InstanceId|UniqueIdentifier|ID di un'istanza del flusso di lavoro.|  
|PendingTimer|DateTime|Indica che il flusso di lavoro è bloccato in un'attività Delay e sarà ripreso dopo la scadenza del timer. Questo valore può essere Null se il flusso di lavoro non è bloccato in attesa della scadenza di un timer.|  
|CreationTime|DateTime|Indica quando è stato creato il flusso di lavoro.|  
|LastUpdatedTime|DateTime|Indica l'ora in cui il flusso di lavoro è stato salvato l'ultima volta in modo permanente nel database.|  
|ServiceDeploymentId|BigInt|Si comporta come una chiave esterna della visualizzazione [ServiceDeployments]. Se l'istanza del flusso di lavoro corrente è un'istanza di un servizio ospitato su Web, in questa colonna è presente un valore, in caso contrario è impostata su NULL.|  
|SuspensionExceptionName|Nvarchar(450)|Indica il tipo di eccezione, ad esempio InvalidOperationException, che ha causato la sospensione del flusso di lavoro.|  
|SuspensionReason|Nvarchar(max)|Indica il motivo per cui l'istanza del flusso di lavoro è stata sospesa. Se un'eccezione ha causato la sospensione dell'istanza, in questa colonna è presente il messaggio associato all'eccezione.<br /><br /> Se l'istanza è stata sospesa manualmente, in questa colonna è presente il motivo della sospensione dell'istanza specificato dall'utente.|  
|ActiveBookmarks|Nvarchar(max)|Se l'istanza del flusso di lavoro è inattiva, questa proprietà indica i segnalibri sui quali è bloccata l'istanza. Se l'istanza non è inattiva, questa colonna è NULL.|  
|CurrentMachine|Nvarchar(128)|Indica il nome del computer in cui l'istanza del flusso di lavoro è attualmente caricata in memoria.|  
|Last Machine.|Nvarchar(450)|Indica l'ultimo computer in cui è stata caricata l'istanza del flusso di lavoro.|  
|ExecutionStatus|Nvarchar(450)|Indica lo stato di esecuzione corrente del flusso di lavoro. Gli stati possibili includono l' **esecuzione**, l' **inattività**, la **chiusura**.|  
|IsInitialized|Bit|Indica se l'istanza del flusso di lavoro è stata inizializzata. Un'istanza del flusso di lavoro inizializzata è stata salvata in modo permanente almeno una volta.|  
|IsSuspended|Bit|Indica se l'istanza del flusso di lavoro è stata sospesa.|  
|IsCompleted|Bit|Indica se l'esecuzione dell'istanza del flusso di lavoro è stata completata. **Nota:**  IIf la proprietà **InstanceCompletionAction** è impostata su **DeleteAll**, dopo il completamento le istanze vengono rimosse dalla visualizzazione.|  
|EncodingOption|TinyInt|Descrive la codifica usata per serializzare le proprietà dei dati.<br /><br /> -0: nessuna codifica<br />-1 – GzipStream|  
|ReadWritePrimitiveDataProperties|Varbinary(max)|Contiene le proprietà dei dati dell'istanza serializzata che saranno restituiti all'esecuzione del flusso di lavoro quando l'istanza viene caricata.<br /><br /> Ogni proprietà primitiva è un tipo CLR nativo e indica che non sono necessari assembly speciali per deserializzare il BLOB.|  
|WriteOnlyPrimitiveDataProperties|Varbinary(max)|Contiene le proprietà dei dati dell'istanza serializzata che non vengono restituiti all'esecuzione del flusso di lavoro quando l'istanza viene caricata.<br /><br /> Ogni proprietà primitiva è un tipo CLR nativo e indica che non sono necessari assembly speciali per deserializzare il BLOB.|  
|ReadWriteComplexDataProperties|Varbinary(max)|Contiene le proprietà dei dati dell'istanza serializzata che saranno restituiti all'esecuzione del flusso di lavoro quando l'istanza viene caricata.<br /><br /> Un deserializzatore richiederebbe la conoscenza di tutti i tipi di oggetti archiviati in questo BLOB.|  
|WriteOnlyComplexDataProperties|Varbinary(max)|Contiene le proprietà dei dati dell'istanza serializzata che non vengono restituiti all'esecuzione del flusso di lavoro quando l'istanza viene caricata.<br /><br /> Un deserializzatore richiederebbe la conoscenza di tutti i tipi di oggetti archiviati in questo BLOB.|  
|IdentityName|Nvarchar(max)|Il nome della definizione del flusso di lavoro.|  
|IdentityPackage|Nvarchar(max)|Le informazioni sul pacchetto fornite quando il flusso di lavoro viene creato (come il nome dell'assembly).|  
|Compila|BigInt|Numero di build della versione del flusso di lavoro.|  
|Principale|BigInt|Il numero principale della versione del flusso di lavoro.|  
|Secondaria|BigInt|Il numero secondario della versione del flusso di lavoro.|  
|Revision|BigInt|Numero di revisione della versione del flusso di lavoro.|  
  
> [!CAUTION]
> La visualizzazione **instances** contiene anche un trigger DELETE. Gli utenti con autorizzazioni appropriate possono eseguire istruzioni di eliminazione a fronte di questa visualizzazione per la rimozione forzata delle istanze del flusso di lavoro dal database. Si consiglia di procedere all'eliminazione diretta dalla visualizzazione solo come ultima risorsa, perché l'eliminazione di un'istanza dall'esecuzione del flusso di lavoro potrebbe comportare conseguenze impreviste. Usare invece l'endpoint di gestione dell'istanza del flusso di lavoro affinché l'istanza venga terminata dall'esecuzione del flusso di lavoro. Se si desidera eliminare un numero elevato di istanze dalla visualizzazione, assicurarsi che non siano presenti esecuzioni attive che potrebbe essere in corso su queste istanze.  
  
## <a name="servicedeployments-view"></a>Visualizzazione ServiceDeployments  
 La vista **ServiceDeployments** contiene informazioni sulla distribuzione per tutti i servizi del flusso di lavoro Web (IIS/was) ospitati. Ogni istanza del flusso di lavoro ospitata sul Web conterrà un **ServiceDeploymentId** che fa riferimento a una riga in questa visualizzazione.  
  
|Nome colonna|Tipo di colonna|Descrizione|  
|-----------------|-----------------|-----------------|  
|ServiceDeploymentId|BigInt|Chiave primaria per questa visualizzazione.|  
|SiteName|Nvarchar(max)|Rappresenta il nome del sito che contiene il servizio del flusso di lavoro, ad esempio il **sito Web predefinito**.|  
|RelativeServicePath|Nvarchar(max)|Rappresenta il percorso virtuale relativo del sito che punta al servizio flusso di lavoro es.  **/App1/PurchaseOrderService.svc**).|  
|RelativeApplicationPath|Nvarchar(max)|Rappresenta il percorso virtuale relativo del sito che punta a un'applicazione contenente il servizio flusso di lavoro (ad esempio **/App1**).|  
|ServiceName|Nvarchar(max)|Rappresenta il nome del servizio flusso di lavoro (ad esempio **PurchaseOrderService**).|  
|ServiceNamespace|Nvarchar(max)|Rappresenta lo spazio dei nomi del servizio flusso di lavoro (ad esempio, **MyCompany**).|  
  
 La visualizzazione ServiceDeployments contiene inoltre un trigger di eliminazione. Gli utenti con autorizzazioni appropriate possono eseguire istruzioni di eliminazione a fronte di questa visualizzazione per la rimozione di voci di ServiceDeployment dal database. Come puoi notare:  
  
1. L'eliminazione di voci da questa visualizzazione consuma molte risorse, in quanto è necessario bloccare l'intero database prima dell'esecuzione di questa operazione. Ciò è necessario per evitare lo scenario in cui un'istanza del flusso di lavoro potrebbe fare riferimento a una voce di ServiceDeployment inesistente. Procedere all'eliminazione da questa visualizzazione solo durante i periodi di inattività o manutenzione.  
  
2. Qualsiasi tentativo di eliminare una riga ServiceDeployment a cui fanno riferimento le voci nella visualizzazione **istanze** genererà un no-op. È possibile eliminare solo righe di ServiceDeployment prive di riferimenti.  
  
## <a name="instancepromotedproperties-view"></a>Visualizzazione InstancePromotedProperties  
 La visualizzazione **InstancePromotedProperties** contiene informazioni per tutte le proprietà innalzate di grado specificate dall'utente. Una proprietà promossa funziona come una proprietà di prima classe che può essere usata da un utente nelle query per recuperare istanze.  Ad esempio, un utente potrebbe aggiungere una promozione PurchaseOrder che archivia sempre il costo di un ordine nella colonna **value1** . Ciò consentirebbe a un utente di eseguire una query per tutti gli ordini di acquisto il cui costo supera un determinato valore.  
  
|Tipo di colonna|Tipo di colonna|Descrizione|  
|-|-|-|  
|InstanceId|UniqueIdentifier|ID dell'istanza del flusso di lavoro.|  
|EncodingOption|TinyInt|Descrive la codifica usata per serializzare le proprietà binarie promosse.<br /><br /> -0: nessuna codifica<br />-1 – GZipStream|  
|PromotionName|Nvarchar(400)|Nome della promozione associata a questa istanza. PromotionName è necessario per aggiungere contesto alle colonne generiche in questa riga.<br /><br /> Ad esempio, un PromotionName di PurchaseOrder potrebbe indicare che Value1 contiene il costo dell'ordine, Value2 contiene il nome del cliente che ha inserito l'ordine, Value3 contiene l'indirizzo del cliente e così via.|  
|Value[1-32]|SqlVariant|Value[1-32] contiene valori che possono essere archiviati in una colonna SqlVariant. Una singola promozione non può contenere più di 32 SqlVariant.|  
|Value[33-64]|Varbinary(max)|Value[33-64] contiene valori serializzati. Ad esempio, Value33 potrebbe contenere un'immagine JPEG di un elemento in fase di acquisto. Una singola promozione non può contenere più di 32 proprietà binarie.|  
  
 La visualizzazione InstancePromotedProperties è associata allo schema e ciò significa che gli utenti possono aggiungere indici in una o più colonne per ottimizzare le query basate su questa visualizzazione.  
  
> [!NOTE]
> Una visualizzazione indicizzata richiede più spazio di archiviazione e comporta un aumento del sovraccarico di elaborazione. Per ulteriori informazioni, fare riferimento a [miglioramento delle prestazioni con SQL Server 2008 viste indicizzate](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd171921(v=sql.100)) .
