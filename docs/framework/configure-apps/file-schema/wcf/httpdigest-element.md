---
title: <httpDigest> Elemento
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 914711e4d6c3dbb1ccc741af1b3abd6b8de716a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165321"
---
# <a name="httpdigest-element"></a><span data-ttu-id="b6348-102">\<httpDigest > elemento</span><span class="sxs-lookup"><span data-stu-id="b6348-102">\<httpDigest> Element</span></span>
<span data-ttu-id="b6348-103">Specifica una credenziale di tipo digest usata per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="b6348-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="b6348-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b6348-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b6348-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b6348-105">\<behaviors></span></span>  
<span data-ttu-id="b6348-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="b6348-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="b6348-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b6348-107">\<behavior></span></span>  
<span data-ttu-id="b6348-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b6348-108">\<clientCredentials></span></span>  
<span data-ttu-id="b6348-109">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="b6348-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6348-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6348-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6348-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6348-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b6348-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6348-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6348-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6348-113">Attributes</span></span>  
  
|<span data-ttu-id="b6348-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="b6348-114">Attribute</span></span>|<span data-ttu-id="b6348-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6348-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="b6348-116">Imposta la preferenza di rappresentazione che il client comunica al server.</span><span class="sxs-lookup"><span data-stu-id="b6348-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="b6348-117">La modalità di rappresentazione selezionata dal client non viene imposta sul server.</span><span class="sxs-lookup"><span data-stu-id="b6348-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="b6348-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="b6348-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b6348-119">-Identificazione: Il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="b6348-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="b6348-120">-Rappresentazione: Il server può rappresentare il contesto di sicurezza del client nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="b6348-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="b6348-121">-Delega: Il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="b6348-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="b6348-122">-Anonimo: Il server non può rappresentare o identificare il client.</span><span class="sxs-lookup"><span data-stu-id="b6348-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="b6348-123">-None: Non è assegnato un livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="b6348-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="b6348-124">L'impostazione predefinita è Identification.</span><span class="sxs-lookup"><span data-stu-id="b6348-124">The default is Identification.</span></span> <span data-ttu-id="b6348-125">L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="b6348-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6348-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6348-126">Child Elements</span></span>  
 <span data-ttu-id="b6348-127">nessuno</span><span class="sxs-lookup"><span data-stu-id="b6348-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6348-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6348-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b6348-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6348-129">Element</span></span>|<span data-ttu-id="b6348-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6348-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6348-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b6348-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="b6348-132">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="b6348-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6348-133">Note</span><span class="sxs-lookup"><span data-stu-id="b6348-133">Remarks</span></span>  
 <span data-ttu-id="b6348-134">Un digest è un hash determinato mediante un algoritmo e un insieme di input.</span><span class="sxs-lookup"><span data-stu-id="b6348-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="b6348-135">L'autenticatore e l'autenticato concordano un algoritmo e scambiamo i dati usati come input.</span><span class="sxs-lookup"><span data-stu-id="b6348-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="b6348-136">Il client può calcolare l'hash e inviarlo al servizio.</span><span class="sxs-lookup"><span data-stu-id="b6348-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="b6348-137">Il servizio calcola anche l'hash e confronta i valori.</span><span class="sxs-lookup"><span data-stu-id="b6348-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="b6348-138">Una corrispondenza convalida il client.</span><span class="sxs-lookup"><span data-stu-id="b6348-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="b6348-139">Questa funzionalità deve essere abilitata con Active Directory in Windows e Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b6348-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="b6348-140">Per altre informazioni, vedere [l'autenticazione del Digest in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="b6348-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6348-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6348-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="b6348-142">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b6348-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b6348-143">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="b6348-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="b6348-144">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="b6348-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="b6348-145">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="b6348-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
