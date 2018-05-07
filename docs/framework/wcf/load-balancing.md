---
title: Bilanciamento del carico
ms.date: 03/30/2017
helpviewer_keywords:
- load balancing [WCF]
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
ms.openlocfilehash: 9ad9c9c569137534addfa3b91f412fb0c0a4b808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="load-balancing"></a>Bilanciamento del carico
Un modo per aumentare la capacità delle applicazioni di Windows Communication Foundation (WCF) consiste nella scalabilità orizzontale distribuendole in una farm di server con bilanciamento del carico. Nelle applicazioni [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] il bilanciamento del carico può essere realizzato utilizzando tecniche standard, tra cui servizi di bilanciamento del carico come Bilanciamento carico di rete di Windows, nonché appositi dispositivi basati su hardware.  
  
 Nelle sezioni seguenti vengono illustrate alcune considerazioni sul bilanciamento del carico delle applicazioni [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] create utilizzando varie associazioni fornite dal sistema.  
  
## <a name="load-balancing-with-the-basic-http-binding"></a>Bilanciamento del carico con l'associazione HTTP di base  
 Dal punto di vista del bilanciamento del carico, le applicazioni [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] che comunicano utilizzando <xref:System.ServiceModel.BasicHttpBinding> non sono diverse da altri tipi comuni di traffico di rete HTTP (contenuto HTML statico, pagine ASP.NET o servizi Web ASMX). I canali [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] che utilizzano questa associazione sono intrinsecamente senza stato e terminano le connessioni quando vengono chiusi. Di conseguenza, <xref:System.ServiceModel.BasicHttpBinding> funziona correttamente con le tecniche esistenti di bilanciamento del carico HTTP.  
  
 Per impostazione predefinita, <xref:System.ServiceModel.BasicHttpBinding> invia nei messaggi un'intestazione HTTP Connection con un valore `Keep-Alive` che consente ai client di stabilire connessioni permanenti ai servizi che le supportano. Questa configurazione offre un miglioramento della velocità effettiva poiché le connessioni stabilite in precedenza possono essere riutilizzate per l'invio di messaggi successivi allo stesso server. Il riutilizzo delle connessioni può tuttavia causare una forte associazione dei client a un server specifico all'interno della farm con carico bilanciato, riducendo in questo modo l'efficacia del bilanciamento del carico di tipo round robin. Se questo comportamento è inaccettabile, è possibile disattivare il `Keep-Alive` HTTP nel server utilizzando la proprietà <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> con una classe <xref:System.ServiceModel.Channels.CustomBinding> o una classe <xref:System.ServiceModel.Channels.Binding> definita dall'utente. Nell'esempio seguente viene illustrato come eseguire questa operazione utilizzando la configurazione.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
 <system.serviceModel>  
  <services>  
   <service   
     name="Microsoft.ServiceModel.Samples.CalculatorService"  
     behaviorConfiguration="CalculatorServiceBehavior">  
     <host>  
      <baseAddresses>  
       <add baseAddress="http://localhost:8000/servicemodelsamples/service"/>  
      </baseAddresses>  
     </host>  
    <!-- configure http endpoint, use base address provided by host  
         And the customBinding -->  
     <endpoint address=""  
           binding="customBinding"  
           bindingConfiguration="HttpBinding"   
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
   </service>  
  </services>  
  
  <bindings>  
    <customBinding>  
  
    <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
      <binding name="HttpBinding" keepAliveEnabled="False"/>  
  
    </customBinding>  
  </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 Utilizzando la configurazione semplificata introdotta in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], lo stesso comportamento può essere ottenuto utilizzando la configurazione semplificata seguente.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
 <system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="customBinding" />  
    </protocolMapping>  
    <bindings>  
      <customBinding>  
  
      <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
        <binding keepAliveEnabled="False"/>  
  
      </customBinding>  
    </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 Per ulteriori informazioni sull'endpoint predefiniti, associazioni e comportamenti, vedere [configurazione semplificata](../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="load-balancing-with-the-wshttp-binding-and-the-wsdualhttp-binding"></a>Bilanciamento del carico con l'associazione WSHttp e WSDualHttp  
 Entrambe le classi <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.WSDualHttpBinding> possono essere sottoposte a bilanciamento del carico utilizzando tecniche di bilanciamento del carico HTTP, purché vengano apportate alcune modifiche alla configurazione dell'associazione predefinita.  
  
-   Disattivare la definizione del contesto di sicurezza. A tale scopo, impostare la proprietà <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> della classe <xref:System.ServiceModel.WSHttpBinding> su `false`. In alternativa, se le sessioni di sicurezza sono necessari, è possibile utilizzare le sessioni di sicurezza con stato, come descritto nel [alle sessioni protette](../../../docs/framework/wcf/feature-details/secure-sessions.md) argomento. Le sessioni di sicurezza con stato consentono al servizio di rimanere senza stato, poiché lo stato per la sessione di sicurezza viene trasmesso con ogni richiesta come parte del token di sicurezza. Si noti che per abilitare una sessione di sicurezza con stato, è necessario utilizzare una classe <xref:System.ServiceModel.Channels.CustomBinding> o una classe <xref:System.ServiceModel.Channels.Binding> definita dall'utente, poiché le impostazioni di configurazione necessarie non vengono esposte sulle classi <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.WSDualHttpBinding> fornite dal sistema.  
  
-   Non utilizzare sessioni affidabili. Questa funzionalità è disattivata per impostazione predefinita.  
  
## <a name="load-balancing-the-nettcp-binding"></a>Bilanciamento del carico dell'associazione Net.TCP  
 La classe <xref:System.ServiceModel.NetTcpBinding> può essere sottoposta a bilanciamento del carico utilizzando tecniche di bilanciamento del carico a livello IP. Tuttavia, per impostazione predefinita, <xref:System.ServiceModel.NetTcpBinding> combina in pool le connessioni TCP per ridurre la latenza delle connessioni. Si tratta di un'ottimizzazione che interferisce con il meccanismo di base del bilanciamento del carico. Il valore di configurazione principale per ottimizzare <xref:System.ServiceModel.NetTcpBinding> è il timeout di lease, che fa parte delle impostazioni del pool di connessioni. Il pool di connessioni fa in modo che le connessioni client siano associate a server specifici all'interno della farm. Con l'aumento della durata di tali connessioni (un fattore controllato dall'impostazione del timeout di lease), la distribuzione del carico nei vari server della farm diventa sbilanciata. Di conseguenza, la durata media delle chiamate aumenta. Quando si utilizza <xref:System.ServiceModel.NetTcpBinding> in scenari con carico bilanciato, considerare una riduzione del timeout di lease predefinito utilizzato dall'associazione. Un timeout di lease di 30 secondi è un punto di partenza ragionevole per scenari con carico bilanciato, sebbene il valore ottimale dipenda dall'applicazione. Per ulteriori informazioni sui timeout lease del canale e di altre quote di trasporto, vedere [delle quote del trasporto](../../../docs/framework/wcf/feature-details/transport-quotas.md).  
  
 Per migliorare le prestazioni in scenari con carico bilanciato, considerare l'utilizzo di <xref:System.ServiceModel.NetTcpSecurity> (<xref:System.ServiceModel.SecurityMode.Transport> o <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedure consigliate per l'hosting in Internet Information Services (IIS)](../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
