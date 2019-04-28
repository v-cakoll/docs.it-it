---
title: Controllo dell'utilizzo di risorse e miglioramento delle prestazioni
ms.date: 03/30/2017
ms.assetid: 9a829669-5f76-4c88-80ec-92d0c62c0660
ms.openlocfilehash: 11d1333ed0ae8b46f8f87fa6f4643d4b31fac3ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785060"
---
# <a name="controlling-resource-consumption-and-improving-performance"></a>Controllo dell'utilizzo di risorse e miglioramento delle prestazioni
Questo argomento descrive le varie proprietà in aree diverse dell'architettura Windows Communication Foundation (WCF) che utilizzano il consumo di risorse di controllo e influire sulle metriche delle prestazioni.

## <a name="properties-that-constrain-resource-consumption-in-wcf"></a>Proprietà che limitano l'utilizzo di risorse in WCF
 Windows Communication Foundation (WCF) applicati vincoli ad alcuni tipi di processi per scopi di sicurezza o prestazioni. I vincoli si presentano in due forme principali: quote e velocità. *Le quote* sono limiti che volta raggiunti o superati, generano un'eccezione immediata in un determinato momento nel sistema. *Limita* sono riportati i limiti che non causano immediatamente di essere generata un'eccezione. Quando viene raggiunto un limite di velocità, invece, l'elaborazione continua rimanendo nei limiti impostati dal valore della velocità. Questa elaborazione limitata potrebbe generare un'eccezione in un altro punto, ma questo dipende dall'applicazione.

 Oltre alla distinzione tra quote e velocità, alcune proprietà di limitazione si trovano al livello della serializzazione, alcune al livello del trasporto e alcune al livello dell'applicazione. La proprietà <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=nameWithType> della quota, ad esempio, implementata da tutti gli elementi dell'associazione del trasporto forniti dal sistema, è pari a 65.536 byte per impostazione predefinita per impedire a client dannosi di effettuare attacchi Denial of Service contro un servizio provocando un consumo di memoria eccessivo. È in genere possibile migliorare le prestazioni abbassando questo valore.

 Un esempio di quota di serializzazione è la proprietà <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=nameWithType>, che specifica il numero massimo di oggetti serializzati o deserializzati dal serializzatore in una sola chiamata al metodo <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A>. Un esempio di limite a livello di applicazione è la proprietà <xref:System.ServiceModel.Dispatcher.ServiceThrottle.MaxConcurrentSessions%2A?displayProperty=nameWithType> che per impostazione predefinita limita a 10 il numero di connessioni simultanee del canale con sessione. A differenza delle quote, se viene raggiunto questo valore limite, l'applicazione continua l'elaborazione ma non accetta nuovi canali con sessione. Non è quindi possibile connettere nuovi client fino a quando uno degli altri canali con sessione non è stato terminato.

 Questi controlli sono stati progettati per fornire una mitigazione automatica di alcuni tipi di attacchi o per migliorare la misurazione delle prestazioni, ad esempio footprint di memoria, ora di avvio e così via. A seconda dell'applicazione, tuttavia, questi controlli possono limitare le prestazioni dell'applicazione di servizio o ostacolare del tutto il funzionamento dell'applicazione. Un'applicazione progettata per trasmettere video, ad esempio, può facilmente superare il valore della proprietà <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=nameWithType>. In questo argomento fornisce una panoramica dei vari controlli applicati alle applicazioni a tutti i livelli di WCF, vengono descritti vari modi per ottenere altre informazioni sul fatto che un'impostazione è che impediscono l'applicazione e vengono descritte le modalità per risolvere vari problemi. Molte velocità e alcune quote sono disponibili a livello di applicazione, anche quando la proprietà di base è un limite per la serializzazione o il trasporto. È ad esempio possibile impostare la proprietà <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=nameWithType> utilizzando la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.MaxItemsInObjectGraph%2A?displayProperty=nameWithType> nella classe del servizio.

> [!NOTE]
> Se si dispone di un particolare problema, è consigliabile leggere innanzitutto le [Guida rapida di risoluzione dei problemi di WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) per vedere se è presente il problema (e una soluzione).

 Vengono elencate le proprietà che limitano i processi di serializzazione [considerazioni sulla sicurezza per i dati](../../../docs/framework/wcf/feature-details/security-considerations-for-data.md). Vengono elencate le proprietà che limitano l'utilizzo di risorse relativamente ai trasporti [le quote dei trasporti](../../../docs/framework/wcf/feature-details/transport-quotas.md). Le proprietà che limitano l'utilizzo di risorse a livello di applicazione sono membri della classe <xref:System.ServiceModel.Dispatcher.ServiceThrottle>.

## <a name="detecting-application-and-performance-issues-related-to-quota-settings"></a>Rilevazione di problemi in applicazioni e prestazioni relativi alle impostazioni delle quote
 Le impostazioni predefinite dei valori precedenti sono state scelte per abilitare le funzionalità di base dell'applicazione in un'ampia gamma di tipi di applicazioni pur fornendo una protezione di base nei confronti di problemi di sicurezza comuni. Concezioni diverse delle applicazioni possono, tuttavia, superare una o più impostazioni della velocità sebbene l'applicazione sia per altri versi protetta e il suo funzionamento sia quello previsto. In questi casi è necessario identificare il valore di velocità superato e il livello al quale si è verificato il superamento e decidere l'intervento appropriato per aumentare la velocità effettiva dell'applicazione.

 In genere, durante la scrittura dell'applicazione e l'esecuzione del debug, la proprietà <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> viene impostata su `true` nel file di configurazione o a livello di programmazione. Ciò indica a WCF di restituire tracce dello stack eccezione del servizio all'applicazione client per la visualizzazione. Questa funzionalità consente di segnalare la maggior parte delle eccezioni a livello di applicazione in modo da visualizzare le impostazioni delle quote interessate, se questo è il problema.

 Alcune eccezioni si verificano in fase di esecuzione e non sono visibili al livello dell'applicazione, quindi non vengono restituite con questo meccanismo e potrebbero non essere gestite da un'implementazione <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType> personalizzata. In un ambiente di sviluppo quale Microsoft Visual Studio la maggior parte di queste eccezioni viene visualizzata automaticamente. Tuttavia, alcune eccezioni possono essere mascherate da impostazioni di ambiente di sviluppo, ad esempio [Just My Code](/visualstudio/debugger/just-my-code) Visual Studio.

 Indipendentemente dalle funzionalità dell'ambiente di sviluppo, è possibile usare le funzionalità di traccia WCF e la registrazione dei messaggi per tutte le eccezioni di debug e ottimizzare le prestazioni delle applicazioni. Per altre informazioni, vedere [Using Tracing per risolvere i problemi dell'applicazione](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).

## <a name="performance-issues-and-xmlserializer"></a>Problemi di prestazioni e XmlSerializer
 I servizi e le applicazioni client che utilizzano tipi di dati serializzabili tramite <xref:System.Xml.Serialization.XmlSerializer> generano e compilano il codice di serializzazione per tali dati in fase di esecuzione, il che può rallentare le prestazioni all'avvio.

> [!NOTE]
> Un codice di serializzazione pregenerato può essere utilizzato solamente nelle applicazioni client e non nei servizi.

 Il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) può migliorare le prestazioni di avvio per queste applicazioni generando il codice di serializzazione necessario dagli assembly compilati per l'applicazione. Per altre informazioni, vedere [Procedura: Migliorare l'avvio tempo di applicazioni Client WCF usando XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).

## <a name="performance-issues-when-hosting-wcf-services-under-aspnet"></a>Problemi di prestazioni quando ASP.NET ospita servizi WCF
 Quando un servizio WCF viene ospitato da IIS e ASP.NET, le impostazioni di configurazione di IIS e ASP.NET possono influire sulla velocità effettiva e sul footprint di memoria del servizio WCF.  Per altre informazioni sulle prestazioni ASP.NET, vedere [miglioramento delle prestazioni ASP.NET](https://go.microsoft.com/fwlink/?LinkId=186462).  Un'impostazione che potrebbe avere conseguenze impreviste è <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A>, che è una proprietà di <xref:System.Web.Configuration.ProcessModelSection>. Se l'applicazione dispone di un numero fisso o piccolo di client, l'impostazione di <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A> su 2 potrebbe fornire una spinta di velocità effettiva in un computer con multiprocessore con un utilizzo della CPU vicino al 100%. Questo aumento nelle prestazioni ha comunque un costo: determinerà anche un aumento dell'utilizzo della memoria, con conseguente riduzione della scalabilità.

## <a name="see-also"></a>Vedere anche

- [Amministrazione e diagnostica](../../../docs/framework/wcf/diagnostics/index.md)
- [Dati di grandi dimensioni e streaming](../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)
