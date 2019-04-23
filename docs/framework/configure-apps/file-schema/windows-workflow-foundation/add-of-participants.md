---
title: <add> di <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: 291d1a006bc16769e36774dd9507017cb555e547
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079123"
---
# <a name="add-of-participants"></a>\<aggiungere > di \<partecipanti >
Configurare un partecipante del rilevamento che ascolta i record di rilevamento generati direttamente durante la fase di esecuzione e li elabora in base alle impostazioni configurate. Tali impostazioni includono la scrittura in un output specifico, ad esempio file, console, ETW, l'elaborazione/aggregazione dei record o qualsiasi altra combinazione che potrebbe essere richiesta.  
  
 Per altre informazioni sul rilevamento del flusso di lavoro e sui partecipanti di rilevamento, vedere [flusso di lavoro di rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [partecipanti del rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).  
  
\<system.serviceModel>  
\<tracking>  
\<i partecipanti >  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|name|Stringa che specifica il nome di un partecipante del rilevamento.|  
|profileName|Stringa che specifica il nome del profilo di rilevamento che definisce i record di rilevamento sottoscritti dal partecipante del rilevamento.|  
|tipo|Stringa che specifica il tipo di un partecipante del rilevamento.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|Elenco di partecipanti del rilevamento.|  
  
## <a name="remarks"></a>Note  
 I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti. Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.  
  
 Più partecipanti del rilevamento possono usare simultaneamente gli eventi di rilevamento. Ogni partecipante del rilevamento può essere associato a un profilo di rilevamento diverso.  
  
 Viene fornito un partecipante del rilevamento standard che scrive i record di rilevamento in una sessione ETW. Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione. L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi. Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.  
  
 L'Id del Provider usato dal partecipante del rilevamento ETW per scrivere i record di rilevamento in ETW è definito nel  **\<diagnostica >** sezione. Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto. Ciò viene definito dal **profileName** attributo il  **\<aggiungere >** elemento. Dopo aver definito tali elementi, viene aggiunto il partecipante di rilevamento per il  **\<etwTracking >** comportamento del servizio. che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.  
  
```xml  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [Rilevamento e analisi del flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Partecipanti di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
