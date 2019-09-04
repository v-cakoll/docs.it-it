---
title: Schema di configurazione di Windows Identity Foundation
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
ms.openlocfilehash: 8dc58f3dc68ee226228056e457914c9dfa53cca5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251982"
---
# <a name="windows-identity-foundation-configuration-schema"></a>Schema di configurazione di Windows Identity Foundation

Gli argomenti in questa sezione contengono informazioni sullo schema di configurazione di WIF (Windows Identity Foundation). È anche possibile configurare un'applicazione per l'uso di WIF tramite le classi esposte dal Framework. Queste classi sono segnalate nelle sezioni dedicate agli elementi pertinenti nello schema. Di seguito viene illustrata la struttura di tag XML di base esposta dallo schema di configurazione di WIF. Gli attributi sono omessi. I commenti evidenziati indicano i principali componenti dello schema.  
  
```xml  
<configuration>  
    <system.identityModel>  
        <!-- Service Configuration -->  
        <identityConfiguration>  
            <caches>  
                <sessionSecurityTokenCache />  
                <tokenReplayCache />  
            </caches>  
      
            <certificateValidation>  
                <certificateValidator />   
            </certificateValidation>  
      
            <claimsAuthenticationManager />  
      
            <claimsAuthorizationManager>  
                <optionalConfigurationElement>  
            </claimsAuthorizationManager>  
      
            <claimTypeRequired>  
                <claimType />   
            </claimTypeRequired>  
      
            <tokenReplayDetection />  
      
            <!-- Security Token Handler Collection Configuration -->  
            <securityTokenHandlers>  
                <add>  
                    <!-- Can take an optional configuration element which can be one of  
                         the following or a custom element -->  
                    <samlSecurityTokenHandlerRequirement>  
                        <nameClaimType>  
                        <roleClaimType>   
                    </samlSecurityTokenHandlerRequirement>  
      
                    <sessionSecurityTokenHandlerRequirement />  
                    <x509SecurityTokenHandlerRequirement />  
                    <userNameSecurityTokenHandlerRequirement />  
                </add>  
                <clear />  
                <remove />  
                <securityTokenHandlerConfiguration>  
                    <audienceUris>  
                        <add>  
                        <clear>  
                        <remove>  
                    </audienceUris>  
      
                    <caches>  
                        <sessionSecurityTokenCache />  
                        <tokenReplayCache />  
                    </caches>  
      
                    <certificateValidation>  
                        <certificateValidator>   
                    </certificateValidation>  
      
                    <issuerNameRegistry>  
                        <!-- Can take an optional configuration element which can be   
                             the <trustedIssuers> element to configure a configuration-based  
                             issuer name registry or can be a custom element -->  
                        <trustedIssuers>  
                            <add>  
                            <clear>  
                            <remove>  
                        </trustedIssuers>  
                    </issuerNameRegistry>  
      
                    <issuerTokenResolver />  
                    <serviceTokenResolver />  
                    <tokenReplayDetection />  
                </securityTokenHandlerConfiguration>  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
      
    <system.identityModel.services>  
        <!-- Federation Authentication Configuration -->  
        <federatedAuthentication>  
            <cookieHandler>  
                <chunkedCookieHandler />  
                <customCookieHandler />  
            </cookieHandler>  
      
            <serviceCertificate>  
                <certificateReference>  
            </serviceCertificate>  
      
            <wsFederation />  
        </federatedAuthentication>  
    </system.identityModel.services>  
</configuration>  
```  
  
## <a name="in-this-section"></a>In questa sezione  

[\<system.identityModel>](system-identitymodel.md) Configurazione per abilitare le opzioni WIF nelle applicazioni.  
  
[\<system.identityModel.services>](system-identitymodel-services.md) Configurazione per la federazione passiva con WIF. Configura il modulo di autenticazione della sessione (SAM) e il modulo di autenticazione federata (WSFAM).
