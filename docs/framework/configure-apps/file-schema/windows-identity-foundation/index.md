---
title: Schema di configurazione di Windows Identity Foundation
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="e2766-102">Schema di configurazione di Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="e2766-102">Windows Identity Foundation Configuration Schema</span></span>
<span data-ttu-id="e2766-103">Gli argomenti in questa sezione contengono informazioni sullo schema di configurazione di WIF (Windows Identity Foundation).</span><span class="sxs-lookup"><span data-stu-id="e2766-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="e2766-104">È anche possibile configurare un'applicazione per usare WIF tramite classi esposte dal framework.</span><span class="sxs-lookup"><span data-stu-id="e2766-104">You can also configure an application to use WIF through classes exposed by the framework.</span></span> <span data-ttu-id="e2766-105">Queste classi sono segnalate nelle sezioni dedicate agli elementi pertinenti nello schema.</span><span class="sxs-lookup"><span data-stu-id="e2766-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="e2766-106">Di seguito viene illustrata la struttura di tag XML di base esposta dallo schema di configurazione di WIF.</span><span class="sxs-lookup"><span data-stu-id="e2766-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="e2766-107">Gli attributi sono omessi.</span><span class="sxs-lookup"><span data-stu-id="e2766-107">Attributes are omitted.</span></span> <span data-ttu-id="e2766-108">I commenti evidenziati indicano i principali componenti dello schema.</span><span class="sxs-lookup"><span data-stu-id="e2766-108">Highlighted comments indicate major components of the schema.</span></span>  
  
```xml  
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
```  
  
## <a name="in-this-section"></a><span data-ttu-id="e2766-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="e2766-109">In This Section</span></span>  
 <span data-ttu-id="e2766-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Configurazione per abilitare le opzioni WIF nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e2766-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
 <span data-ttu-id="e2766-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) Configurazione per la federazione passiva con WIF.</span><span class="sxs-lookup"><span data-stu-id="e2766-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="e2766-112">Configura il modulo di autenticazione della sessione (SAM) e il modulo di autenticazione federata (WSFAM).</span><span class="sxs-lookup"><span data-stu-id="e2766-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>
