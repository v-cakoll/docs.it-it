---
title: '&lt;transport&gt; di &lt;basicHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a69be01146e71e71ba7e901de288d84c533b1e1c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltbasichttpbindinggt"></a>&lt;transport&gt; di &lt;basicHttpBinding&gt;
Definisce proprietà che controllano i parametri di autenticazione per il trasporto HTTP.  
  
 \<System. ServiceModel >  
\<associazioni >  
\<basicHttpBinding >  
\<associazione >  
\<sicurezza >  
\<trasporto >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<basicHttpBinding>  
    <binding>  
        <security  
        mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
             proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string" >  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|clientCredentialType|-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client mediante l'autenticazione HTTP.  Il valore predefinito è `None`. L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.|  
|proxyCredentialType|-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client all'interno di un dominio tramite un proxy su HTTP. Questo attributo è applicabile solo quando l'attributo `mode` dell'elemento `security` padre è `Transport` o `TransportCredentialsOnly`. L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|realm|Stringa che specifica l'area di autenticazione usata dallo schema di autenticazione HTTP per l'autenticazione digest o di base. Il valore predefinito è una stringa vuota.|  
|policyEnforcement|Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.<br />2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.<br />3.  Always - I criteri vengono sempre applicati. L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.|  
|protectionScenario|Questa enumerazione specifica lo scenario di protezione applicato dai criteri.|  
  
## <a name="clientcredentialtype-attribute"></a>Attributo clientCredentialType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|None|I messaggi non vengono protetti durante il trasferimento.|  
|Di base|Specifica l'autenticazione di base.|  
|Digest|Specifica l'autenticazione digest.|  
|Ntlm|Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.|  
|Windows|Specifica l'autenticazione Windows integrata.|  
  
## <a name="proxycredentialtype-attribute"></a>Attributo proxyCredentialType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Nessuno|-I messaggi non vengono protetti durante il trasferimento.|  
|Basic|Specifica l'autenticazione di base come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.|  
|Digest|Specifica l'autenticazione digest come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.|  
|Ntlm|Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.|  
|Windows|Specifica l'autenticazione Windows integrata.|  
|Certificato|Esegue l'autenticazione client mediante un certificato. Questa opzione funziona solo se l'attributo `Mode` dell'elemento `security` padre è impostato su Transport, mentre non funzionerà se viene impostato su TransportCredentialOnly.|  
  
### <a name="child-elements"></a>Elementi figlio  
 None  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<sicurezza >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|Definisce le funzionalità di sicurezza per il [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è dimostrato l'uso della sicurezza del trasporto SSL con l'associazione di base. Per impostazione predefinita, l'associazione di base supporta la comunicazione HTTP.  
  
```xml  
<system.serviceModel>  
   <services>  
      <service   
          type="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
         <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
   </services>  
    <bindings>  
        <basicHttpBinding>  
        <!-- Configure basicHttpBinding with Transport security -- >  
        <!-- mode and clientCredentialType set to None.-->  
           <binding name="Binding1">  
               <security mode="Transport">  
                   <transport clientCredentialType="None"  
                              proxyCredentialType="None">  
                       <extendedProtectionPolicy  
                          policyEnforcement="WhenSupported"  
                          protectionScenario="TransportSelected">  
                    <customServiceNames></customServiceNames>  
                       </extendedProtectionPolicy>  
               </security>  
           </binding>  
        </basicHttpBinding>  
    </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Uso di associazioni per configurare i client e servizi Windows Communication Foundation](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<associazione >](../../../../../docs/framework/misc/binding.md)
