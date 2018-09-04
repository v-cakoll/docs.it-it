---
title: Abilitazione dinamica della traccia analitica
ms.date: 03/30/2017
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
ms.openlocfilehash: f03d2ce381be430121a11df95341886a4be667e2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529519"
---
# <a name="dynamically-enabling-analytic-tracing"></a>Abilitazione dinamica della traccia analitica
Utilizzando gli strumenti forniti con il sistema operativo Windows, è possibile abilitare o disabilitare la traccia in modo dinamico utilizzando Traccia eventi per Windows (ETW). Per tutti i [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] servizi Windows Communication Foundation (WCF), traccia analitica può essere abilitata e disabilitata in modo dinamico senza modificare file Web. config dell'applicazione o il riavvio del servizio. In questo modo l'applicazione che genera gli eventi di traccia non subisce variazioni.  
  
 Le opzioni di traccia di WCF possono essere configurate in modo analogo. È ad esempio possibile impostare il livello di gravità da **Error** su **Information** senza interferire con l'applicazione. A tale scopo utilizzare gli strumenti seguenti:  
  
-   **Logman** : strumento da riga di comando per la configurazione, il controllo e l'esecuzione di query sui dati di traccia. Per altre informazioni, vedere [Logman creare traccia](https://go.microsoft.com/fwlink/?LinkId=165426) e [Logman Update Trace](https://go.microsoft.com/fwlink/?LinkId=165427).  
  
-   **EventViewer** : strumento di gestione grafica Windows per visualizzare i risultati della traccia. Per altre informazioni, vedere [i servizi WCF e traccia eventi per Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md) e [Visualizzatore eventi](https://go.microsoft.com/fwlink/?LinkId=165428).  
  
-   **Perfmon** : strumento di gestione grafica Windows che utilizza contatori per monitorare i contatori di tracce e gli effetti della traccia sulle prestazioni. Per altre informazioni, vedere [creare una Data Collector Set manualmente](https://go.microsoft.com/fwlink/?LinkId=165429).  
  
### <a name="keywords"></a>Parole chiave  
 In caso di utilizzo della classe <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> , i messaggi di traccia di .NET Framework vengono in genere filtrati in base al livello di gravità (ad esempio, Error, Warning e Information). ETW supporta il concetto del livello di gravità, ma introduce un nuovo meccanismo di filtro flessibile mediante parole chiave. Le parole chiave sono costituite da valori testuali arbitrari che consentono agli eventi di traccia di fornire contesto aggiuntivo sul significato dell'evento.  
  
 Per la traccia analitica WCF, ogni evento di traccia è disponibili due tipi di parole chiave. Ogni evento dispone in primo luogo di una o più parole chiave di scenari. Queste parole chiave indicano gli scenari che l'evento deve supportare. Sono presenti tre parole chiave di scenari, ognuna progettata per un fine specifico, come indicato nella tabella seguente. Il filtro utilizzando le parole chiave può essere modificato in modo dinamico senza interferire con il servizio WCF. Ciò significa che è possibile modificare in modo dinamico lo scenario di traccia corrente e la quantità di informazioni raccolte sulla traccia. È ad esempio possibile impostare `HealthMonitoring` su `Troubleshooting` e aumentare la granularità dell'evento di traccia.  
  
|Parola chiave|Descrizione|  
|-------------|-----------------|  
|`HealthMonitoring`|Traccia molto leggera, minima che consente di monitorare l'attività del servizio.|  
|`EndToEndMonitoring`|Eventi utilizzati per supportare la traccia del flusso di messaggi.|  
|`Troubleshooting`|Eventi più granulari intorno ai punti di estendibilità di WCF.|  
  
 Il secondo gruppo di parole chiave definisce il componente di [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] che ha generato l'evento.  
  
|Parola chiave|Descrizione|  
|-------------|-----------------|  
|`UserEvents`|Eventi generati dal codice utente e non da [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].|  
|`ServiceModel`|Eventi generati dal runtime di WCF.|  
|`ServiceHost`|Eventi generati dall'host del servizio.|  
|`WCFMessageLogging`|Eventi di registrazione messaggi WCF.|  
  
## <a name="see-also"></a>Vedere anche  
 [WCF Services e Event Tracing for Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
