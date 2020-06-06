---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251742"
---
# \<userNameSecurityTokenHandlerRequirement>
<span data-ttu-id="2ebb2-101">Fornisce la configurazione per la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="2ebb2-101">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="2ebb2-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ebb2-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ebb2-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2ebb2-103">Attributes and Elements</span></span>  
 <span data-ttu-id="2ebb2-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2ebb2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ebb2-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="2ebb2-105">Attributes</span></span>  
  
|<span data-ttu-id="2ebb2-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="2ebb2-106">Attribute</span></span>|<span data-ttu-id="2ebb2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ebb2-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ebb2-108">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="2ebb2-108">membershipProviderName</span></span>|<span data-ttu-id="2ebb2-109">Specifica l'oggetto <xref:System.Web.Security.MembershipProvider> che deve essere utilizzato dal gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2ebb2-109">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ebb2-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2ebb2-110">Child Elements</span></span>  
 <span data-ttu-id="2ebb2-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="2ebb2-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ebb2-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2ebb2-112">Parent Elements</span></span>  
  
|<span data-ttu-id="2ebb2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ebb2-113">Element</span></span>|<span data-ttu-id="2ebb2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ebb2-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="2ebb2-115">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="2ebb2-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ebb2-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="2ebb2-116">Remarks</span></span>  
 <span data-ttu-id="2ebb2-117">L' `<userNameSecurityTokenHandlerRequirement>` elemento imposta la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> proprietà quando un <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="2ebb2-117">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ebb2-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ebb2-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
