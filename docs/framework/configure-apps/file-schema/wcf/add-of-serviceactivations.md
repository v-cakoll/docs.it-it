---
title: '&lt;add&gt; di &lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: d0e1f45cc8ff5b544eff5ff5dae33d5989aaf405
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587635"
---
# <a name="ltaddgt-of-ltserviceactivationsgt"></a>&lt;add&gt; di &lt;serviceActivations&gt;
Elemento di configurazione che consente di definire impostazioni di attivazione di servizi virtuali che eseguono il mapping ai tipi di servizio Windows Communication Foundation (WCF). In questo modo è possibile attivare servizi ospitati in WAS/IIS senza un file con estensione svc.  
  
 \<system.ServiceModel>  
\<ServiceHostingEnvironment>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|factory|Stringa che specifica il tipo CLR della factory che genera un elemento di attivazione del servizio.|  
|service|ServiceType che implementa il servizio, ossia il Typename completo o il Typename breve, quando viene inserito nella cartella App_Code.|  
|relativeAddress|Indirizzo relativo all'interno dell'applicazione IIS corrente, ad esempio “Service.svc". In WCF 4.0 questo indirizzo relativo deve contenere una delle estensioni di file note (svc, xamlx, ecc.). Nessun file fisico deve esistere per l'URL relativo|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Sezione di configurazione in cui vengono descritte le impostazioni di attivazione.|  
  
## <a name="remarks"></a>Note  
 Nell'esempio seguente viene illustrato come configurare le impostazioni di attivazione all'interno del file web.config.  
  
```xml  
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```  
  
 L'utilizzo di questa configurazione consente di attivare GreetingService senza usare un file con estensione svc.  
  
 Si noti che `<serviceHostingEnvironment>` è una configurazione a livello di applicazione. È necessario posizionare il file `web.config` contenente la configurazione nella radice dell'applicazione virtuale. Inoltre, `serviceHostingEnvironment` è una sezione ereditabile di machinetoApplication. Se si registra un servizio nella radice del computer, ogni servizio dell'applicazione erediterà tale servizio.  
  
 L'attivazione basata sulla configurazione supporta l'attivazione sul protocollo http e non http. A tale scopo sono necessarie le estensioni nell'indirizzo relativo, ovvero nei file con estensione svc, xoml o xamlx. È possibile eseguire il mapping di estensioni personalizzate ai provider di compilazione noti, consentendo in tal modo l'attivazione di servizi su qualsiasi estensione. In caso di conflitto, la sezione `<serviceActivations>` esegue l'override delle registrazioni nel file con estensione svc.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
