---
title: <windows> di <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: fb55fb9901e4c08a3c5d7662fdb3bf12a71876bb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275158"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="22b2b-102">\<Windows > di \<clientCredentials > elemento</span><span class="sxs-lookup"><span data-stu-id="22b2b-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="22b2b-103">Specifica le impostazioni per una credenziale Windows da usare per rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="22b2b-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="22b2b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="22b2b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="22b2b-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="22b2b-105">\<behaviors></span></span>  
<span data-ttu-id="22b2b-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="22b2b-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="22b2b-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="22b2b-107">\<behavior></span></span>  
<span data-ttu-id="22b2b-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="22b2b-108">\<clientCredentials></span></span>  
<span data-ttu-id="22b2b-109">\<windows></span><span class="sxs-lookup"><span data-stu-id="22b2b-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22b2b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22b2b-110">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22b2b-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="22b2b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="22b2b-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="22b2b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22b2b-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="22b2b-113">Attributes</span></span>  
  
|<span data-ttu-id="22b2b-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="22b2b-114">Attribute</span></span>|<span data-ttu-id="22b2b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22b2b-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="22b2b-116">Imposta la preferenza di rappresentazione che il client comunica al server.</span><span class="sxs-lookup"><span data-stu-id="22b2b-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="22b2b-117">La modalità di rappresentazione selezionata dal client non viene imposta sul server.</span><span class="sxs-lookup"><span data-stu-id="22b2b-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="22b2b-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="22b2b-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="22b2b-119">-Identificazione: Il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="22b2b-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="22b2b-120">-Rappresentazione: Il server può rappresentare il contesto di sicurezza del client nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="22b2b-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="22b2b-121">-Delega: Il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="22b2b-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="22b2b-122">-Anonimo: Il server non può rappresentare o identificare il client.</span><span class="sxs-lookup"><span data-stu-id="22b2b-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="22b2b-123">-None: Non è assegnato un livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="22b2b-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="22b2b-124">L'impostazione predefinita è Identification.</span><span class="sxs-lookup"><span data-stu-id="22b2b-124">The default is Identification.</span></span> <span data-ttu-id="22b2b-125">L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="22b2b-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="22b2b-126">L'impostazione di questa proprietà su `true` consente di usare l'autenticazione NTLM se Kerberos non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="22b2b-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="22b2b-127">Impostando questa proprietà su `false` fa sì che Windows Communication Foundation (WCF) per rendere un tutti i tentativi possibili per generare un'eccezione se viene usato NTLM.</span><span class="sxs-lookup"><span data-stu-id="22b2b-127">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="22b2b-128">Si noti che l'impostazione di questa proprietà su `false` potrebbe non impedire l'invio di credenziali NTLM nella rete.</span><span class="sxs-lookup"><span data-stu-id="22b2b-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22b2b-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="22b2b-129">Child Elements</span></span>  
 <span data-ttu-id="22b2b-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="22b2b-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22b2b-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="22b2b-131">Parent Elements</span></span>  
  
|<span data-ttu-id="22b2b-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="22b2b-132">Element</span></span>|<span data-ttu-id="22b2b-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22b2b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22b2b-134">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="22b2b-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="22b2b-135">Specifica le credenziali usate per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="22b2b-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22b2b-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22b2b-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="22b2b-137">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="22b2b-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="22b2b-138">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="22b2b-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="22b2b-139">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="22b2b-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
