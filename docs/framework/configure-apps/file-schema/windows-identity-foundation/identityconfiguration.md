---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 0fa8c574fd5663606cf081f1000a24884306edfe
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251988"
---
# \<identityConfiguration>

Specifica le impostazioni di identità a livello di servizio.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<identityConfiguration>**  

## <a name="syntax"></a>Sintassi

```xml
<system.identityModel>
  <identityConfiguration
      name=xs:string
      saveBootstrapContext=xs:boolean>
      maximumClockSkew=TimeSpan >
  </identityConfiguration>
</system.identityModel>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|name|Nome della sezione di configurazione dell'identità. È possibile utilizzare questo nome per fare riferimento a una sezione di configurazione specifica. Se non `name` si specifica alcun attributo, la sezione definisce la configurazione predefinita. La configurazione predefinita viene sempre utilizzata per gli scenari di federazione passiva. Per ulteriori informazioni, vedere l' [\<federationConfiguration>](federationconfiguration.md) elemento.|
|saveBootstrapContext|Specifica se i token di bootstrap devono essere inclusi nel token di sessione. Il valore può essere impostato anche in una raccolta di gestori di token impostando l' `saveBootstrapContext` attributo sull' [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemento. Un valore impostato nella raccolta di gestori di token sostituisce il valore impostato per il servizio.|
|maximumClockSkew|Oggetto <xref:System.TimeSpan> che specifica lo sfasamento massimo consentito del clock. Controlla lo sfasamento massimo consentito di clock quando si eseguono operazioni dipendenti dal tempo, ad esempio la convalida dell'ora di scadenza di una sessione di accesso. Il valore predefinito è 5 minuti, "00:05:00". Per ulteriori informazioni su come specificare <xref:System.TimeSpan> i valori, vedere [valori TimeSpan](../windows-workflow-foundation/index.md). Lo sfasamento di clock massimo può essere impostato anche su una raccolta di gestori di token impostando l' `maximumClockSkew` attributo sull' [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemento. Un valore impostato nella raccolta di gestori di token sostituisce il valore impostato per il servizio.|

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<caches>](caches.md)|Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione dei token. Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza. Facoltativa.|
|[\<certificateValidation>](certificatevalidation.md)|Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati. Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza. Facoltativa.|
|[\<claimsAuthenticationManager>](claimsauthenticationmanager.md)|Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso. Facoltativa.|
|[\<claimsAuthorizationManager>](claimsauthorizationmanager.md)|Registra un gestore autorizzazioni delle attestazioni per le attestazioni in ingresso. Facoltativa.|
|[\<claimTypeRequired>](claimtyperequired.md)|Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso. Facoltativa.|
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Specifica una raccolta di gestori di token di sicurezza. È possibile specificare zero o più raccolte di gestori di token di sicurezza. Facoltativa.|
|[\<tokenReplayDetection>](tokenreplaydetection.md)|Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token. Può essere specificato a livello di servizio o su una raccolta di gestori di token di sicurezza. Facoltativa.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<system.identityModel>](system-identitymodel.md)|Fornisce la configurazione per abilitare le opzioni di Windows Identity Foundation (WIF) nelle applicazioni.|

## <a name="remarks"></a>Commenti

È possibile definire più configurazioni di identità, ognuna con un nome univoco. Il comportamento è il seguente:

1. Se non `<identityConfiguration>` viene specificato alcun elemento. Una configurazione di identità predefinita viene creata in fase di esecuzione e popolata con i valori predefiniti.

2. Se `<identityConfiguration>` viene specificato un singolo elemento. Si tratta della configurazione predefinita dell'identità. Non è importante se è denominato o senza nome.

3. Se `<identityConfiguration>` vengono specificati più elementi. L'elemento senza nome specifica la configurazione predefinita dell'identità. Quando si specificano più elementi, è consigliabile che `<identityConfiguration>` uno di essi sia senza nome.

> [!WARNING]
> Se si specificano più `<identityConfiguration>` elementi, è necessario che uno di essi sia senza nome. L'elemento senza nome sarà la configurazione predefinita dell'identità.

 È possibile eseguire l'override di alcune impostazioni specificate nell' `<identityConfiguration>` elemento da impostazioni in una raccolta di gestori di token di sicurezza o da impostazioni sui singoli gestori del token di sicurezza.

> [!IMPORTANT]
> Quando si usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo degli accessi in base alle attestazioni nel codice, la configurazione dell'identità a cui fa riferimento l' `<federationConfiguration>` elemento configura il gestore delle autorizzazioni delle attestazioni e i criteri usati per prendere decisioni di autorizzazione. Questo vale anche per gli scenari che non sono scenari Web passivi, ad esempio applicazioni Windows Communication Foundation (WCF) o un'applicazione che non è basata sul Web. Se l'applicazione non è un'applicazione Web passiva, l' [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) elemento e i relativi elementi figlio, se presenti, della configurazione di identità a cui si fa riferimento sono le uniche impostazioni applicate. Tutte le altre impostazioni vengono ignorate. Per ulteriori informazioni, vedere l' [\<federationConfiguration>](federationconfiguration.md) elemento.

L' `<identityConfiguration>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> classe. Una sezione di configurazione dell'identità è rappresentata dalla <xref:System.IdentityModel.Configuration.IdentityConfiguration> classe.

> [!IMPORTANT]
> La specifica dei seguenti elementi come elementi figlio dell' `<identityConfiguration>` elemento è stata deprecata, anche se il comportamento è ancora supportato per la compatibilità con le versioni precedenti. Questi elementi devono invece essere specificati nell' [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemento.
>
> - [\<audienceUris>](audienceuris.md)
> - [\<issuerNameRegistry>](issuernameregistry.md)
> - [\<issuerTokenResolver>](issuertokenresolver.md)
> - [\<serviceTokenResolver>](servicetokenresolver.md)

## <a name="example"></a>Esempio

Nell'esempio seguente viene creata una configurazione di identità denominata "alternateConfiguration". La configurazione dell'identità specifica le impostazioni predefinite.

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
