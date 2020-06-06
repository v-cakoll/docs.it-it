---
title: <message> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736753"
---
# <a name="message-of-netmsmqbinding"></a>\<message> di \<netMsmqBinding>

Definisce le impostazioni di sicurezza dei messaggi SOAP in questa associazione `netMsmqBinding`.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  

## <a name="syntax"></a>Sintassi

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|algorithmSuite|Imposta la crittografia del messaggio e gli algoritmi di incapsulamento della chiave usati per ottenere la sicurezza basata su messaggi per i messaggi inviati sul trasporto MSMQ.<br /><br /> Il valore predefinito è `Aes256`. L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|
|clientCredentialType|Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita per i messaggi inviati sul trasporto MSMQ. I valori validi sono i seguenti:<br /><br /> -None: consente al servizio di interagire con client anonimi. Né il servizio né il client richiedono una credenziale.<br />-Windows: consente di eseguire gli scambi SOAP nel contesto autenticato di una credenziale di Windows. In questo caso viene sempre eseguita l'autenticazione basata su Kerberos.<br />-UserName: consente al servizio di richiedere che il client venga autenticato utilizzando una credenziale UserName. In questo caso, le credenziali devono essere specificate utilizzando il `clientCredentials` comportamento **attenzione:** Windows Communication Foundation (WCF) non supporta l'invio di un digest della password o la derivazione di chiavi tramite password e l'utilizzo di tali chiavi per la sicurezza dei messaggi. Quando si utilizzano credenziali di tipo NomeUtente WCF impone quindi che lo scambio venga protetto. Questa modalità richiede che sia specificato il certificato del servizio sul lato client mediante il comportamento `clientCredential` e `serviceCertificate`. <br /><br /> -Certificate: consente al servizio di richiedere che il client venga autenticato tramite un certificato. La credenziale client in questo caso deve essere specificata tramite il comportamento `clientCredentials`. In questo caso la credenziale del servizio deve essere specificata usando il comportamento `clientCredentials` tramite la specifica di `serviceCertificate`.<br />-CardSpace: consente al servizio di richiedere che il client venga autenticato tramite CardSpace. Il provisioning del certificato `serviceCertificate` deve essere eseguito nel comportamento `clientCredential`.<br /><br /> Il valore predefinito è `Windows`. L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.|

### <a name="child-elements"></a>Elementi figlio

nessuno

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<security>](security-of-netmsmqbinding.md)|Definisce le impostazioni di sicurezza per un'associazione.|

## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [Code in WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Binding](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
