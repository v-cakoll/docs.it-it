---
title: <message> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: c623b7daf1e91c9c1800b9653525cd51b1087506
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58890566"
---
# <a name="message-of-netmsmqbinding"></a>\<messaggio > del \<netMsmqBinding >

Definisce le impostazioni di sicurezza dei messaggi SOAP in questa associazione `netMsmqBinding`.

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

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
|clientCredentialType|Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita per i messaggi inviati sul trasporto MSMQ. Di seguito vengono elencati i valori validi:<br /><br /> -None: None: consente al servizio di interagire con i client anonimi. Né il servizio né il client richiedono una credenziale.<br />-   Windows: In questo modo l'esecuzione di scambi SOAP nel contesto autenticato di una credenziale Windows. In questo caso viene sempre eseguita l'autenticazione basata su Kerberos.<br />-Nome utente: Ciò consente al servizio di richiedere che il client venga autenticato tramite una credenziale UserName. La credenziale in questo caso deve essere specificata tramite il `clientCredentials` comportamento **cautela:**  Windows Communication Foundation (WCF) non supporta l'invio di un digest delle password o la derivazione delle chiavi utilizzano password e l'utilizzo di tali chiavi per la sicurezza dei messaggi. WCF impone quindi che lo scambio sia protetto quando si usano credenziali UserName. Questa modalità richiede che sia specificato il certificato del servizio sul lato client mediante il comportamento `clientCredential` e `serviceCertificate`. <br /><br /> -Certificato: Ciò consente al servizio di richiedere che il client venga autenticato tramite un certificato. La credenziale client in questo caso deve essere specificata tramite il comportamento `clientCredentials`. In questo caso la credenziale del servizio deve essere specificata usando il comportamento `clientCredentials` tramite la specifica di `serviceCertificate`.<br />-CardSpace: In questo modo il servizio di richiedere che il client venga autenticato tramite un CardSpace. Il provisioning del certificato `serviceCertificate` deve essere eseguito nel comportamento `clientCredential`.<br /><br /> Il valore predefinito è `Windows`. L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.|

### <a name="child-elements"></a>Elementi figlio

nessuno

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Definisce le impostazioni di sicurezza per un'associazione.|

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [Code in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
