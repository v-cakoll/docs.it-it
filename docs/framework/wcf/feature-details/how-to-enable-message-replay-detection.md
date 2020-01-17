---
title: 'Procedura: attivare il rilevamento di attacchi di tipo replay dei messaggi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF security
- replay detection [WCF]
- WCF, custom bindings
- WCF, security
ms.assetid: 8b847e91-69a3-49e1-9e5f-0c455e50d804
ms.openlocfilehash: 450a99fc6604ccb3fa796e8a73e1ddc3e3adff9e
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964653"
---
# <a name="how-to-enable-message-replay-detection"></a>Procedura: attivare il rilevamento di attacchi di tipo replay dei messaggi
Un attacco di tipo replay si verifica quando un utente malintenzionato copia un flusso di messaggi tra due parti e lo riproduce verso una o più parti. Se l'attacco non viene contrastato, i computer colpiti elaboreranno il flusso come se i messaggi fossero legittimi, determinando una serie di conseguenze negative, ad esempio ordini ridondanti di un elemento.  
  
 Per ulteriori informazioni sul rilevamento della riproduzione dei messaggi, vedere [rilevamento della riproduzione dei messaggi](https://docs.microsoft.com/previous-versions/msp-n-p/ff649371(v=pandp.10)).  
  
 Nella procedura riportata di seguito vengono illustrate varie proprietà che è possibile utilizzare per controllare il rilevamento della riproduzione mediante Windows Communication Foundation (WCF).  
  
### <a name="to-control-replay-detection-on-the-client-using-code"></a>Per controllare il rilevamento di attacchi di tipo replay nel client mediante il codice  
  
1. Creare un elemento <xref:System.ServiceModel.Channels.SecurityBindingElement> da utilizzare in una classe <xref:System.ServiceModel.Channels.CustomBinding>. Per altre informazioni, vedere [procedura: creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md). Nell'esempio seguente si utilizza un elemento <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> creato con il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> della classe <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
2. Utilizzare la proprietà <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> per restituire un riferimento alla classe <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> e impostare le proprietà seguenti, in base alle esigenze:  
  
    1. `DetectReplay`. Valore Boolean. Determina se il client deve rilevare attacchi di tipo replay dal server. Il valore predefinito è `true`.  
  
    2. `MaxClockSkew`. Valore <xref:System.TimeSpan>. Determina lo sfasamento temporale tollerato dal meccanismo di replay tra client e server. Il meccanismo di sicurezza esamina il timestamp inviato e stabilisce se è troppo vecchio. Il valore predefinito è 5 minuti.  
  
    3. `ReplayWindow`. Valore `TimeSpan`. Determina quanto tempo un messaggio può permanere nella rete dopo l'invio dal server (tramite intermediari) prima di raggiungere il client. Il client tiene traccia delle firme dei messaggi inviati all'interno dell'ultimo `ReplayWindow` a scopo di rilevamento di attacchi di tipo replay.  
  
    4. `ReplayCacheSize`. Valore intero. Il client archivia le firme del messaggio in una cache. Questa impostazione specifica quante firme che possono essere archiviate nella cache. Se il numero dei messaggi inviati all'interno dell'ultima finestra di replay raggiunge il limite della cache, i messaggi nuovi vengono respinti finché le firme più vecchie contenute nella cache non raggiungono il limite di tempo. Il valore predefinito è 500000.  
  
### <a name="to-control-replay-detection-on-the-service-using-code"></a>Per controllare il rilevamento di attacchi di tipo replay nel servizio mediante il codice  
  
1. Creare un elemento <xref:System.ServiceModel.Channels.SecurityBindingElement> da utilizzare in una classe <xref:System.ServiceModel.Channels.CustomBinding>.  
  
2. Utilizzare la proprietà <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> per restituire un riferimento alla classe <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> e impostare le proprietà come descritto in precedenza.  
  
### <a name="to-control-replay-detection-in-configuration-for-the-client-or-service"></a>Per controllare il rilevamento di attacchi di tipo replay nella configurazione per il client o il servizio  
  
1. Creare un [> di\<CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
2. Creare un elemento `<security>`.  
  
3. Creare una [\<> LocalClientSettings](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md) o [\<> LocalServiceSettings](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md).  
  
4. Se necessario, impostare gli attributi seguenti: `detectReplays`, `maxClockSkew`, `replayWindow` e `replayCacheSize`. Nell'esempio seguente vengono impostati entrambi gli elementi `<localServiceSettings>`&lt;localClientSettings&gt; e`<localClientSettings>`.  
  
    ```xml  
    <customBinding>  
      <binding name="NewBinding0">  
       <textMessageEncoding />  
        <security>  
         <localClientSettings   
          replayCacheSize="800000"   
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
         <localServiceSettings   
          replayCacheSize="800000"   
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
        <secureConversationBootstrap />  
       </security>  
      <httpTransport />  
     </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una classe <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> utilizzando il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> e vengono impostate le proprietà di replay dell'associazione.  
  
 [!code-csharp[c_ReplayDetection#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_replaydetection/cs/source.cs#1)]
 [!code-vb[c_ReplayDetection#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_replaydetection/vb/source.vb#1)]  
  
## <a name="scope-of-replay-message-security-only"></a>Ambito di attacchi di tipo replay: solo sicurezza messaggi  
 Si noti che le procedure seguenti si riferiscono solo alla modalità di sicurezza messaggio. Per le modalità di trasporto e di trasporto con credenziali messaggio, i meccanismi di trasporto rilevano gli attacchi di tipo replay.  
  
## <a name="secure-conversation-notes"></a>Note sulla conversazione protetta  
 Per le associazioni che consentono conversazioni protette, è possibile regolare queste impostazioni sia per il canale dell'applicazione che per l'associazione del bootstrap della conversazione protetta. È ad esempio possibile disattivare gli attacchi di tipo replay per il canale dell'applicazione abilitandoli tuttavia per il canale del bootstrap che stabilisce la conversazione protetta.  
  
 Se non si utilizzano sessioni di conversazione protetta, il rilevamento di attacchi di tipo replay non garantisce il rilevamento di attacchi in scenari di server farm e quando il processo viene riciclato. Ciò vale per le associazioni fornite dal sistema seguenti:  
  
- <xref:System.ServiceModel.BasicHttpBinding>.  
  
- <xref:System.ServiceModel.WSHttpBinding> con la proprietà <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> impostata su `false`.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Per compilare il codice sono necessari gli spazi dei nomi seguenti:  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Conversazioni e sessioni sicure](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)
- [\<localClientSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)
- [Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
