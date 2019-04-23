---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 2f0040fb7084b9d53adbd1a114f1cfc62d58e5a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110006"
---
# <a name="systemidentitymodel"></a>\<system.identityModel>
Fornisce la configurazione per l'attivazione di opzioni di Windows Identity Foundation (WIF) nelle applicazioni.  
  
 \<system.identityModel>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 nessuno  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`<configuration>`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
  
## <a name="remarks"></a>Note  
 Aggiungere un `<system.identityModel>` sezione al file di configurazione per configurare un servizio o applicazione per l'uso di Windows Identity Foundation (WIF). Il `<system.identityModel>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come aggiungere un `<system.identityModel>` sezione in un file di configurazione. È innanzitutto necessario aggiungere la dichiarazione di sezione e dello spazio dei nomi di configurazione sotto il `<configSections>` elemento. Sarà quindi possibile aggiungere il `<system.IdentityModel>` elemento nel file di configurazione per specificare uno o più configurazioni di identità.  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
