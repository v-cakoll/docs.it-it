---
title: Elemento &lt;httpDigest&gt;
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 8ea4597dbfc704f669a514b0d6c5976c80c5c3a6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="lthttpdigestgt-element"></a><span data-ttu-id="45926-102">Elemento &lt;httpDigest&gt;</span><span class="sxs-lookup"><span data-stu-id="45926-102">&lt;httpDigest&gt; Element</span></span>
<span data-ttu-id="45926-103">Specifica una credenziale di tipo digest usata per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="45926-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="45926-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="45926-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="45926-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="45926-105">\<behaviors></span></span>  
<span data-ttu-id="45926-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="45926-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="45926-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="45926-107">\<behavior></span></span>  
<span data-ttu-id="45926-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="45926-108">\<clientCredentials></span></span>  
<span data-ttu-id="45926-109">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="45926-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45926-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45926-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45926-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="45926-111">Attributes and Elements</span></span>  
 <span data-ttu-id="45926-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="45926-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45926-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="45926-113">Attributes</span></span>  
  
|<span data-ttu-id="45926-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="45926-114">Attribute</span></span>|<span data-ttu-id="45926-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45926-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="45926-116">Imposta la preferenza di rappresentazione che il client comunica al server.</span><span class="sxs-lookup"><span data-stu-id="45926-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="45926-117">La modalità di rappresentazione selezionata dal client non viene imposta sul server.</span><span class="sxs-lookup"><span data-stu-id="45926-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="45926-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="45926-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="45926-119">-Identificazione: Il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="45926-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="45926-120">-Rappresentazione: Il server può rappresentare il contesto di sicurezza del client nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="45926-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="45926-121">-Delegation: Il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="45926-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="45926-122">-Anonima: Il server non è possibile rappresentare o identificare il client.</span><span class="sxs-lookup"><span data-stu-id="45926-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="45926-123">-None: Un livello di rappresentazione non è assegnato.</span><span class="sxs-lookup"><span data-stu-id="45926-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="45926-124">L'impostazione predefinita è Identification.</span><span class="sxs-lookup"><span data-stu-id="45926-124">The default is Identification.</span></span> <span data-ttu-id="45926-125">L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="45926-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45926-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="45926-126">Child Elements</span></span>  
 <span data-ttu-id="45926-127">Nessuno</span><span class="sxs-lookup"><span data-stu-id="45926-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45926-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="45926-128">Parent Elements</span></span>  
  
|<span data-ttu-id="45926-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="45926-129">Element</span></span>|<span data-ttu-id="45926-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45926-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45926-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="45926-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="45926-132">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="45926-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45926-133">Note</span><span class="sxs-lookup"><span data-stu-id="45926-133">Remarks</span></span>  
 <span data-ttu-id="45926-134">Un digest è un hash determinato mediante un algoritmo e un insieme di input.</span><span class="sxs-lookup"><span data-stu-id="45926-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="45926-135">L'autenticatore e l'autenticato concordano un algoritmo e scambiamo i dati usati come input.</span><span class="sxs-lookup"><span data-stu-id="45926-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="45926-136">Il client può calcolare l'hash e inviarlo al servizio.</span><span class="sxs-lookup"><span data-stu-id="45926-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="45926-137">Il servizio calcola anche l'hash e confronta i valori.</span><span class="sxs-lookup"><span data-stu-id="45926-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="45926-138">Una corrispondenza convalida il client.</span><span class="sxs-lookup"><span data-stu-id="45926-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="45926-139">Questa funzionalità deve essere abilitata con Active Directory in Windows e Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="45926-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="45926-140">Per altre informazioni, vedere [autenticazione del Digest in IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="45926-140">For more information, see [Digest Authentication in IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45926-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45926-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>  
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>  
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>  
 [<span data-ttu-id="45926-142">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="45926-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="45926-143">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="45926-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="45926-144">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="45926-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="45926-145">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="45926-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
