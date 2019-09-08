---
title: Abilitazione dinamica della traccia analitica
ms.date: 03/30/2017
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
ms.openlocfilehash: bea64ac9a9312d17b7f47e72a46d876552e20a12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798106"
---
# <a name="dynamically-enabling-analytic-tracing"></a>Abilitazione dinamica della traccia analitica
Utilizzando gli strumenti forniti con il sistema operativo Windows, è possibile abilitare o disabilitare la traccia in modo dinamico utilizzando Traccia eventi per Windows (ETW). Per tutti [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] i servizi Windows Communication Foundation (WCF), la traccia analitica può essere abilitata e disabilitata in modo dinamico senza modificare il file Web. config dell'applicazione o riavviare il servizio. In questo modo l'applicazione che genera gli eventi di traccia non subisce variazioni.  
  
 Le opzioni di traccia di WCF possono essere configurate in modo analogo. È ad esempio possibile impostare il livello di gravità da **Error** su **Information** senza interferire con l'applicazione. A tale scopo utilizzare gli strumenti seguenti:  
  
- **Logman** : strumento da riga di comando per la configurazione, il controllo e l'esecuzione di query sui dati di traccia. Per ulteriori informazioni, vedere [logman create trace](https://go.microsoft.com/fwlink/?LinkId=165426) e [Logman Update Trace](https://go.microsoft.com/fwlink/?LinkId=165427).  
  
- **EventViewer** : strumento di gestione grafica Windows per visualizzare i risultati della traccia. Per ulteriori informazioni, vedere [servizi WCF e Event Tracing for Windows](../../samples/wcf-services-and-event-tracing-for-windows.md) e [Visualizzatore eventi](https://go.microsoft.com/fwlink/?LinkId=165428).  
  
- **Perfmon** : strumento di gestione grafica Windows che utilizza contatori per monitorare i contatori di tracce e gli effetti della traccia sulle prestazioni. Per ulteriori informazioni, vedere [creare manualmente un insieme agenti di raccolta dati](https://go.microsoft.com/fwlink/?LinkId=165429).  
  
### <a name="keywords"></a>Parole chiave  
 In caso di utilizzo della classe <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> , i messaggi di traccia di .NET Framework vengono in genere filtrati in base al livello di gravità (ad esempio, Error, Warning e Information). ETW supporta il concetto del livello di gravità, ma introduce un nuovo meccanismo di filtro flessibile mediante parole chiave. Le parole chiave sono costituite da valori testuali arbitrari che consentono agli eventi di traccia di fornire contesto aggiuntivo sul significato dell'evento.  
  
 Per la traccia analitica WCF, ogni evento di traccia dispone di due tipi di parole chiave. Ogni evento dispone in primo luogo di una o più parole chiave di scenari. Queste parole chiave indicano gli scenari che l'evento deve supportare. Sono presenti tre parole chiave di scenari, ognuna progettata per un fine specifico, come indicato nella tabella seguente. Il filtraggio tramite parole chiave può essere modificato dinamicamente senza compromettere il servizio WCF. Ciò significa che è possibile modificare in modo dinamico lo scenario di traccia corrente e la quantità di informazioni raccolte sulla traccia. È ad esempio possibile impostare `HealthMonitoring` su `Troubleshooting` e aumentare la granularità dell'evento di traccia.  
  
|Parola chiave|DESCRIZIONE|  
|-------------|-----------------|  
|`HealthMonitoring`|Traccia molto leggera, minima che consente di monitorare l'attività del servizio.|  
|`EndToEndMonitoring`|Eventi utilizzati per supportare la traccia del flusso di messaggi.|  
|`Troubleshooting`|Eventi più granulari intorno ai punti di estensibilità di WCF.|  
  
 Il secondo gruppo di parole chiave definisce il componente della .NET Framework ha generato l'evento.  
  
|Parola chiave|Descrizione|  
|-------------|-----------------|  
|`UserEvents`|Eventi generati dal codice utente e non dal .NET Framework.|  
|`ServiceModel`|Eventi generati dal runtime WCF.|  
|`ServiceHost`|Eventi generati dall'host del servizio.|  
|`WCFMessageLogging`|Eventi di registrazione messaggi WCF.|  
  
## <a name="see-also"></a>Vedere anche

- [WCF Services e Event Tracing for Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
