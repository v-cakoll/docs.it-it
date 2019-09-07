---
title: <windows>dell' <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 61ca99213f0b83a5af5df0184a8c1de405366288
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399123"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="94956-102">\<> di Windows \<dell'elemento ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="94956-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="94956-103">Specifica le impostazioni per una credenziale Windows da usare per rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="94956-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
<span data-ttu-id="94956-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="94956-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="94956-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="94956-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="94956-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="94956-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="94956-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="94956-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="94956-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="94956-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="94956-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="94956-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="94956-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di Windows**</span><span class="sxs-lookup"><span data-stu-id="94956-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94956-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94956-111">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94956-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="94956-112">Attributes and Elements</span></span>  
 <span data-ttu-id="94956-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="94956-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94956-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="94956-114">Attributes</span></span>  
  
|<span data-ttu-id="94956-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="94956-115">Attribute</span></span>|<span data-ttu-id="94956-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94956-116">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="94956-117">Imposta la preferenza di rappresentazione che il client comunica al server.</span><span class="sxs-lookup"><span data-stu-id="94956-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="94956-118">La modalità di rappresentazione selezionata dal client non viene imposta sul server.</span><span class="sxs-lookup"><span data-stu-id="94956-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="94956-119">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="94956-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="94956-120">Identificazione Il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="94956-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="94956-121">Rappresentazione Il server può rappresentare il contesto di sicurezza del client nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="94956-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="94956-122">Delegazione Il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="94956-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="94956-123">Anonimo Il server non può rappresentare o identificare il client.</span><span class="sxs-lookup"><span data-stu-id="94956-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="94956-124">Nessuno Non è stato assegnato un livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="94956-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="94956-125">L'impostazione predefinita è Identification.</span><span class="sxs-lookup"><span data-stu-id="94956-125">The default is Identification.</span></span> <span data-ttu-id="94956-126">L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="94956-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="94956-127">L'impostazione di questa proprietà su `true` consente di usare l'autenticazione NTLM se Kerberos non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="94956-127">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="94956-128">L'impostazione di questa `false` proprietà su fa sì che Windows Communication Foundation (WCF) faccia il possibile tentativo di generare un'eccezione se viene utilizzata l'autenticazione NTLM.</span><span class="sxs-lookup"><span data-stu-id="94956-128">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="94956-129">Si noti che l'impostazione di questa proprietà su `false` potrebbe non impedire l'invio di credenziali NTLM nella rete.</span><span class="sxs-lookup"><span data-stu-id="94956-129">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94956-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="94956-130">Child Elements</span></span>  
 <span data-ttu-id="94956-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="94956-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94956-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="94956-132">Parent Elements</span></span>  
  
|<span data-ttu-id="94956-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="94956-133">Element</span></span>|<span data-ttu-id="94956-134">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="94956-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94956-135">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="94956-135">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="94956-136">Specifica le credenziali usate per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="94956-136">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94956-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94956-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="94956-138">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="94956-138">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="94956-139">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="94956-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="94956-140">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="94956-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
