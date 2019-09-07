---
title: <httpDigest> Elemento
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: f392ebf4eeb6a008952fd4d5ef4e301e57f6eb31
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397998"
---
# <a name="httpdigest-element"></a><span data-ttu-id="d94e1-102">\<Elemento > httpDigest</span><span class="sxs-lookup"><span data-stu-id="d94e1-102">\<httpDigest> Element</span></span>
<span data-ttu-id="d94e1-103">Specifica una credenziale di tipo digest usata per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="d94e1-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
<span data-ttu-id="d94e1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d94e1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d94e1-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d94e1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d94e1-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d94e1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d94e1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d94e1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="d94e1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d94e1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="d94e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="d94e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="d94e1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> httpDigest**</span><span class="sxs-lookup"><span data-stu-id="d94e1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d94e1-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d94e1-111">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d94e1-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d94e1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d94e1-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d94e1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d94e1-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="d94e1-114">Attributes</span></span>  
  
|<span data-ttu-id="d94e1-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="d94e1-115">Attribute</span></span>|<span data-ttu-id="d94e1-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d94e1-116">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="d94e1-117">Imposta la preferenza di rappresentazione che il client comunica al server.</span><span class="sxs-lookup"><span data-stu-id="d94e1-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="d94e1-118">La modalità di rappresentazione selezionata dal client non viene imposta sul server.</span><span class="sxs-lookup"><span data-stu-id="d94e1-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="d94e1-119">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="d94e1-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d94e1-120">Identificazione Il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="d94e1-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="d94e1-121">Rappresentazione Il server può rappresentare il contesto di sicurezza del client nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="d94e1-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="d94e1-122">Delegazione Il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="d94e1-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="d94e1-123">Anonimo Il server non può rappresentare o identificare il client.</span><span class="sxs-lookup"><span data-stu-id="d94e1-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="d94e1-124">Nessuno Non è stato assegnato un livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="d94e1-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="d94e1-125">L'impostazione predefinita è Identification.</span><span class="sxs-lookup"><span data-stu-id="d94e1-125">The default is Identification.</span></span> <span data-ttu-id="d94e1-126">L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="d94e1-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d94e1-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d94e1-127">Child Elements</span></span>  
 <span data-ttu-id="d94e1-128">Nessuna</span><span class="sxs-lookup"><span data-stu-id="d94e1-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d94e1-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d94e1-129">Parent Elements</span></span>  
  
|<span data-ttu-id="d94e1-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="d94e1-130">Element</span></span>|<span data-ttu-id="d94e1-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d94e1-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d94e1-132">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="d94e1-132">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="d94e1-133">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="d94e1-133">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d94e1-134">Note</span><span class="sxs-lookup"><span data-stu-id="d94e1-134">Remarks</span></span>  
 <span data-ttu-id="d94e1-135">Un digest è un hash determinato mediante un algoritmo e un insieme di input.</span><span class="sxs-lookup"><span data-stu-id="d94e1-135">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="d94e1-136">L'autenticatore e l'autenticato concordano un algoritmo e scambiamo i dati usati come input.</span><span class="sxs-lookup"><span data-stu-id="d94e1-136">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="d94e1-137">Il client può calcolare l'hash e inviarlo al servizio.</span><span class="sxs-lookup"><span data-stu-id="d94e1-137">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="d94e1-138">Il servizio calcola anche l'hash e confronta i valori.</span><span class="sxs-lookup"><span data-stu-id="d94e1-138">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="d94e1-139">Una corrispondenza convalida il client.</span><span class="sxs-lookup"><span data-stu-id="d94e1-139">A match validates the client.</span></span>  
  
 <span data-ttu-id="d94e1-140">Questa funzionalità deve essere abilitata con Active Directory in Windows e Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d94e1-140">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="d94e1-141">Per ulteriori informazioni, vedere [autenticazione del digest in IIS 6,0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="d94e1-141">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d94e1-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d94e1-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="d94e1-143">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d94e1-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d94e1-144">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="d94e1-144">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="d94e1-145">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="d94e1-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="d94e1-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="d94e1-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
