---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 017309436660991c69da569e9cc4219e842ecaa3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251867"
---
# \<securityTokenHandlers>
<span data-ttu-id="1ceaf-101">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-101">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**  
  
## <a name="syntax"></a><span data-ttu-id="1ceaf-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ceaf-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ceaf-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1ceaf-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1ceaf-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ceaf-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="1ceaf-105">Attributes</span></span>  
  
|<span data-ttu-id="1ceaf-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="1ceaf-106">Attribute</span></span>|<span data-ttu-id="1ceaf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ceaf-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ceaf-108">name</span><span class="sxs-lookup"><span data-stu-id="1ceaf-108">name</span></span>|<span data-ttu-id="1ceaf-109">Specifica il nome di una raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-109">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="1ceaf-110">Gli unici valori riconosciuti dal Framework sono "ActAs" e "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="1ceaf-110">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="1ceaf-111">Se le raccolte di gestori di token vengono specificate con uno di questi nomi, l'insieme verrà usato per l'elaborazione rispettivamente dei token ActAs o OnBehalfOf.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-111">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ceaf-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1ceaf-112">Child Elements</span></span>  
  
|<span data-ttu-id="1ceaf-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ceaf-113">Element</span></span>|<span data-ttu-id="1ceaf-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ceaf-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="1ceaf-115">Aggiunge un gestore del token di sicurezza alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-115">Adds a security token handler to the token handler collection.</span></span>|  
|[\<clear>](clear.md)|<span data-ttu-id="1ceaf-116">Cancella tutti i gestori dei token di sicurezza dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-116">Clears all security token handlers from the token handler collection.</span></span>|  
|[\<remove>](remove.md)|<span data-ttu-id="1ceaf-117">Rimuove un gestore del token di sicurezza dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-117">Removes a security token handler from the token handler collection.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="1ceaf-118">Fornisce la configurazione per la raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-118">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ceaf-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1ceaf-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1ceaf-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ceaf-120">Element</span></span>|<span data-ttu-id="1ceaf-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ceaf-121">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="1ceaf-122">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ceaf-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="1ceaf-123">Remarks</span></span>  
 <span data-ttu-id="1ceaf-124">È possibile specificare una o più raccolte denominate di gestori di token di sicurezza in una configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-124">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="1ceaf-125">È possibile specificare un nome per una raccolta usando l' `name` attributo.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-125">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="1ceaf-126">Gli unici nomi gestiti dal Framework sono "ActAs" e "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="1ceaf-126">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="1ceaf-127">Se i gestori sono presenti in queste raccolte, vengono utilizzati da un servizio token di sicurezza (STS) invece dei gestori predefiniti durante l'elaborazione `ActAs` e i `OnBehalfOf` token.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-127">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="1ceaf-128">Per impostazione predefinita, la raccolta viene popolata con i tipi di gestore seguenti: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> ,, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> e <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="1ceaf-128">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="1ceaf-129">È possibile modificare la raccolta usando gli `<add>` elementi, `<remove>` e `<clear>` .</span><span class="sxs-lookup"><span data-stu-id="1ceaf-129">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="1ceaf-130">È necessario assicurarsi che nella raccolta sia presente solo un singolo gestore di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-130">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="1ceaf-131">Se, ad esempio, si deriva un gestore dalla <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe, il gestore o l'oggetto <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> può essere configurato in una singola raccolta, ma non in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-131">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="1ceaf-132">Utilizzare l' `<securityTokenHandlerConfiguration>` elemento per specificare le impostazioni di configurazione per i gestori nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-132">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="1ceaf-133">Le impostazioni specificate tramite questo elemento eseguono l'override di quelle specificate nel servizio tramite l' [\<identityConfiguration>](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-133">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="1ceaf-134">Alcuni gestori (inclusi diversi tipi di gestori incorporati) possono supportare una configurazione aggiuntiva tramite un elemento figlio dell' `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-134">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="1ceaf-135">Le impostazioni specificate in un gestore eseguono l'override delle impostazioni equivalenti specificate nella raccolta o nel servizio.</span><span class="sxs-lookup"><span data-stu-id="1ceaf-135">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
