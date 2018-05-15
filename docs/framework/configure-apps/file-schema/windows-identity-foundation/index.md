---
title: Schema di configurazione di Windows Identity Foundation
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 8e813383f68644315d59aa58f87cea7532a1d4c9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="ee695-102">Schema di configurazione di Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="ee695-102">Windows Identity Foundation Configuration Schema</span></span>
<span data-ttu-id="ee695-103">Gli argomenti in questa sezione contengono informazioni sullo schema di configurazione di WIF (Windows Identity Foundation).</span><span class="sxs-lookup"><span data-stu-id="ee695-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="ee695-104">È anche possibile configurare un'applicazione per usare WIF tramite classi esposte dal framework.</span><span class="sxs-lookup"><span data-stu-id="ee695-104">You can also configure an application to use WIF through classes exposed by the framework,.</span></span> <span data-ttu-id="ee695-105">Queste classi sono segnalate nelle sezioni dedicate agli elementi pertinenti nello schema.</span><span class="sxs-lookup"><span data-stu-id="ee695-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="ee695-106">Di seguito viene illustrata la struttura di tag XML di base esposta dallo schema di configurazione di WIF.</span><span class="sxs-lookup"><span data-stu-id="ee695-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="ee695-107">Gli attributi sono omessi.</span><span class="sxs-lookup"><span data-stu-id="ee695-107">Attributes are omitted.</span></span> <span data-ttu-id="ee695-108">I commenti evidenziati indicano i principali componenti dello schema.</span><span class="sxs-lookup"><span data-stu-id="ee695-108">Highlighted comments indicate major components of the schema.</span></span>  
  
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
  
## <a name="in-this-section"></a><span data-ttu-id="ee695-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ee695-109">In This Section</span></span>  
 <span data-ttu-id="ee695-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Configurazione per abilitare le opzioni WIF nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ee695-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
 <span data-ttu-id="ee695-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) Configurazione per la federazione passiva con WIF.</span><span class="sxs-lookup"><span data-stu-id="ee695-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="ee695-112">Configura il modulo di autenticazione della sessione (SAM) e il modulo di autenticazione federata (WSFAM).</span><span class="sxs-lookup"><span data-stu-id="ee695-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ee695-113">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ee695-113">Related Sections</span></span>  
 <span data-ttu-id="ee695-114">[Configurazione, amministrazione e gestione](http://msdn.microsoft.com/library/1e03c389-de2c-4096-aaff-86b087e1bea0) Viene descritto come configurare e gestire servizi e applicazioni WIF.</span><span class="sxs-lookup"><span data-stu-id="ee695-114">[Configuration, Administration, And Management](http://msdn.microsoft.com/library/1e03c389-de2c-4096-aaff-86b087e1bea0) Describes how to configure and manage WIF applications and services.</span></span>
