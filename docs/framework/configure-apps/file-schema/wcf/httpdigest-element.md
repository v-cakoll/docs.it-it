---
title: <httpDigest> Elemento
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 328411a429cd42927a190c6805a1f5e2b3555ea1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77448452"
---
# <a name="httpdigest-element"></a><span data-ttu-id="c3103-102">\<httpDigest> Elemento</span><span class="sxs-lookup"><span data-stu-id="c3103-102">\<httpDigest> Element</span></span>
<span data-ttu-id="c3103-103">Specifica una credenziale di tipo digest usata per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="c3103-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**  
  
## <a name="syntax"></a><span data-ttu-id="c3103-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3103-104">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3103-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c3103-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c3103-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c3103-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3103-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="c3103-107">Attributes</span></span>  
  
|<span data-ttu-id="c3103-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="c3103-108">Attribute</span></span>|<span data-ttu-id="c3103-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3103-109">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="c3103-110">Imposta la preferenza di rappresentazione che il client comunica al server.</span><span class="sxs-lookup"><span data-stu-id="c3103-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="c3103-111">La modalità di rappresentazione selezionata dal client non viene imposta sul server.</span><span class="sxs-lookup"><span data-stu-id="c3103-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="c3103-112">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3103-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c3103-113">-Identificazione: il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="c3103-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="c3103-114">-Rappresentazione: il server può rappresentare il contesto di sicurezza del client nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="c3103-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="c3103-115">-Delega: il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="c3103-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="c3103-116">-Anonimo: il server non può rappresentare o identificare il client.</span><span class="sxs-lookup"><span data-stu-id="c3103-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="c3103-117">-None: non è stato assegnato un livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="c3103-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="c3103-118">L'impostazione predefinita è Identification.</span><span class="sxs-lookup"><span data-stu-id="c3103-118">The default is Identification.</span></span> <span data-ttu-id="c3103-119">L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="c3103-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3103-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c3103-120">Child Elements</span></span>  
 <span data-ttu-id="c3103-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="c3103-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3103-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c3103-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c3103-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3103-123">Element</span></span>|<span data-ttu-id="c3103-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3103-124">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="c3103-125">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="c3103-125">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3103-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="c3103-126">Remarks</span></span>  
 <span data-ttu-id="c3103-127">Un digest è un hash determinato mediante un algoritmo e un insieme di input.</span><span class="sxs-lookup"><span data-stu-id="c3103-127">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="c3103-128">L'autenticatore e l'autenticato concordano un algoritmo e scambiamo i dati usati come input.</span><span class="sxs-lookup"><span data-stu-id="c3103-128">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="c3103-129">Il client può calcolare l'hash e inviarlo al servizio.</span><span class="sxs-lookup"><span data-stu-id="c3103-129">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="c3103-130">Il servizio calcola anche l'hash e confronta i valori.</span><span class="sxs-lookup"><span data-stu-id="c3103-130">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="c3103-131">Una corrispondenza convalida il client.</span><span class="sxs-lookup"><span data-stu-id="c3103-131">A match validates the client.</span></span>  
  
 <span data-ttu-id="c3103-132">Questa funzionalità deve essere abilitata con Active Directory in Windows e Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c3103-132">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="c3103-133">Per ulteriori informazioni, vedere [autenticazione del digest in IIS 6,0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="c3103-133">For more information, see [Digest Authentication in IIS 6.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3103-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c3103-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="c3103-135">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="c3103-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c3103-136">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="c3103-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="c3103-137">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="c3103-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="c3103-138">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="c3103-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
