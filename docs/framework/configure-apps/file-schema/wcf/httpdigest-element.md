---
title: Elemento &lt;httpDigest&gt;
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 2211c593090d697ae07350fcf7ac491b9d23e2d0
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150141"
---
# <a name="lthttpdigestgt-element"></a><span data-ttu-id="a7150-102">Elemento &lt;httpDigest&gt;</span><span class="sxs-lookup"><span data-stu-id="a7150-102">&lt;httpDigest&gt; Element</span></span>
<span data-ttu-id="a7150-103">Specifica una credenziale di tipo digest usata per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="a7150-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="a7150-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a7150-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a7150-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="a7150-105">\<behaviors></span></span>  
<span data-ttu-id="a7150-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a7150-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a7150-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="a7150-107">\<behavior></span></span>  
<span data-ttu-id="a7150-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a7150-108">\<clientCredentials></span></span>  
<span data-ttu-id="a7150-109">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="a7150-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7150-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7150-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7150-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a7150-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a7150-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a7150-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7150-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="a7150-113">Attributes</span></span>  
  
|<span data-ttu-id="a7150-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="a7150-114">Attribute</span></span>|<span data-ttu-id="a7150-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7150-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="a7150-116">Imposta la preferenza di rappresentazione che il client comunica al server.</span><span class="sxs-lookup"><span data-stu-id="a7150-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="a7150-117">La modalità di rappresentazione selezionata dal client non viene imposta sul server.</span><span class="sxs-lookup"><span data-stu-id="a7150-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="a7150-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="a7150-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a7150-119">-Identificazione: Il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="a7150-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="a7150-120">-Rappresentazione: Il server può rappresentare il contesto di sicurezza del client nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="a7150-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="a7150-121">-Delega: Il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="a7150-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="a7150-122">-Anonimo: Il server non può rappresentare o identificare il client.</span><span class="sxs-lookup"><span data-stu-id="a7150-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="a7150-123">-None: Non è assegnato un livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="a7150-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="a7150-124">L'impostazione predefinita è Identification.</span><span class="sxs-lookup"><span data-stu-id="a7150-124">The default is Identification.</span></span> <span data-ttu-id="a7150-125">L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="a7150-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7150-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a7150-126">Child Elements</span></span>  
 <span data-ttu-id="a7150-127">nessuno</span><span class="sxs-lookup"><span data-stu-id="a7150-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7150-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a7150-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a7150-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7150-129">Element</span></span>|<span data-ttu-id="a7150-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7150-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7150-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a7150-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="a7150-132">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="a7150-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7150-133">Note</span><span class="sxs-lookup"><span data-stu-id="a7150-133">Remarks</span></span>  
 <span data-ttu-id="a7150-134">Un digest è un hash determinato mediante un algoritmo e un insieme di input.</span><span class="sxs-lookup"><span data-stu-id="a7150-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="a7150-135">L'autenticatore e l'autenticato concordano un algoritmo e scambiamo i dati usati come input.</span><span class="sxs-lookup"><span data-stu-id="a7150-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="a7150-136">Il client può calcolare l'hash e inviarlo al servizio.</span><span class="sxs-lookup"><span data-stu-id="a7150-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="a7150-137">Il servizio calcola anche l'hash e confronta i valori.</span><span class="sxs-lookup"><span data-stu-id="a7150-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="a7150-138">Una corrispondenza convalida il client.</span><span class="sxs-lookup"><span data-stu-id="a7150-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="a7150-139">Questa funzionalità deve essere abilitata con Active Directory in Windows e Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="a7150-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="a7150-140">Per altre informazioni, vedere [l'autenticazione del Digest in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="a7150-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7150-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7150-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>  
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>  
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>  
 [<span data-ttu-id="a7150-142">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a7150-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="a7150-143">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="a7150-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="a7150-144">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="a7150-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="a7150-145">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="a7150-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
