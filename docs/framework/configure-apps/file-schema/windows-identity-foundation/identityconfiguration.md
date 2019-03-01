---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 91d64ce0d6a5cdbf32fec4a476fb111afe9a7952
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212495"
---
# <a name="identityconfiguration"></a>\<identityConfiguration>

Specifica le impostazioni di identità a livello di servizio.

 \<system.identityModel>\
\<identityConfiguration>

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
|name|Il nome della sezione di configurazione identità. È possibile usare questo nome per fare riferimento a una sezione di configurazione specifico. Se nessun `name` attributo è specificato, la sezione definisce la configurazione predefinita. Viene sempre utilizzata la configurazione predefinita per gli scenari di federazione passiva. Per altre informazioni, vedere la [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.|
|saveBootstrapContext|Specifica se i token di bootstrap devono essere incluse nel token di sessione. Il valore può anche essere impostato su una raccolta di gestori di token impostando il `saveBootstrapContext` attributo la [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento. Il valore impostato per la raccolta di gestori di token sostituisce il valore impostato nel servizio.|
|maximumClockSkew|Oggetto <xref:System.TimeSpan> che specifica il numero massimo consentito sfasamenti di orario. Controlla il numero massimo consentito sfasamenti di orario durante l'esecuzione di operazioni di tempo, ad esempio convalida la data di scadenza di una sessione di accesso. Il valore predefinito è di 5 minuti "00: 05:00". Per altre informazioni su come specificare <xref:System.TimeSpan> valori, vedere [valori Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). La differenza di orario massimo può essere impostato anche in una raccolta di gestori di token, impostando il `maximumClockSkew` attributo la [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento. Il valore impostato per la raccolta di gestori di token sostituisce il valore impostato nel servizio.|

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<caches>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra le cache usate per il rilevamento riproduzione token e i token di sessione. Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza. Facoltativo.|
|[\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Controllare le impostazioni che utilizzano i gestori di token per convalidare i certificati. Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza. Facoltativo.|
|[\<claimsAuthenticationManager>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso. Facoltativo.|
|[\<claimsAuthorizationManager>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|Registra un gestore di autorizzazione delle attestazioni per le attestazioni in ingresso. Facoltativo.|
|[\<claimTypeRequired>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso. Facoltativo.|
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Specifica una raccolta di gestori di token di sicurezza. È possibile specificare zero o più raccolte di gestori di token di sicurezza. Facoltativo.|
|[\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Abilita rilevamento riproduzione token e specifica l'ora di scadenza per i token. Può essere specificato a livello di servizio o in una raccolta di gestori di token di sicurezza. Facoltativo.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|Fornisce la configurazione per l'attivazione di opzioni di Windows Identity Foundation (WIF) nelle applicazioni.|

## <a name="remarks"></a>Note

Più identità è possibile definire configurazioni, ognuna con un nome univoco. Il comportamento è come segue:

1. Se nessun `<identityConfiguration>` viene specificato alcun elemento. Una configurazione di identità predefinito viene creata in fase di esecuzione e popolata con i valori predefiniti.

2. Se un singolo `<identityConfiguration>` viene specificato alcun elemento. Si tratta della configurazione di identità predefinito. Non è importante se si è definito o meno.

3. Se più `<identityConfiguration>` vengono specificati gli elementi. L'elemento senza nome specifica la configurazione di identità predefinito. È consigliabile che quando si specificano più `<identityConfiguration>` elementi, uno di essi deve essere senza nome.

> [!WARNING]
> Se si specificano più `<identityConfiguration>` elementi, uno di essi deve essere senza nome. L'elemento senza nome sarà la configurazione di identità predefinito.

 Alcune delle impostazioni specificate nel `<identityConfiguration>` elemento può essere sottoposto a override dalle impostazioni in una raccolta di gestori di token di sicurezza o mediante le impostazioni di gestori di token di sicurezza.

> [!IMPORTANT]
> Quando si usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o il <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo di accesso basato sulle attestazioni nel codice, la configurazione di identità che fa riferimento il `<federationConfiguration>` elemento consente di configurare il gestore di autorizzazione delle attestazioni e i criteri utilizzati per rendere decisioni di autorizzazione. Ciò è vero, anche in scenari non Web gli scenari passivi, ad esempio le applicazioni di Windows Communication Foundation (WCF) o un'applicazione che non è basata sul Web. Se l'applicazione non è un'applicazione Web passiva, il [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) elemento (e gli elementi di criteri figlio, se presente) della configurazione dell'identità cui viene fatto riferimento sono le uniche impostazioni applicate. Tutte le altre impostazioni vengono ignorate. Per altre informazioni, vedere la [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.

Il `<identityConfiguration>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> classe. Una sezione di configurazione di identità è rappresentata dal <xref:System.IdentityModel.Configuration.IdentityConfiguration> classe.

> [!IMPORTANT]
> Specificare i seguenti elementi come elementi figlio del `<identityConfiguration>` elemento è stato deprecato, sebbene il comportamento è ancora supportato per la compatibilità con le versioni precedenti. Questi elementi invece dovrebbero, essere specificati sotto il [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento.
>
> - [\<audienceUris>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)
> - [\<issuerNameRegistry>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)
> - [\<issuerTokenResolver>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)
> - [\<serviceTokenResolver>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)

## <a name="example"></a>Esempio

L'esempio seguente crea una configurazione di identità denominata "alternateConfiguration". La configurazione di identità specifica le impostazioni predefinite.

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
