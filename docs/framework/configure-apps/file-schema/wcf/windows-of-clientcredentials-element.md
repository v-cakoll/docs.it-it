---
title: <windows>dell' <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 61ca99213f0b83a5af5df0184a8c1de405366288
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399123"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="873a3-102">\<windows>dell' \<clientCredentials> elemento</span><span class="sxs-lookup"><span data-stu-id="873a3-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="873a3-103">Specifica le impostazioni per una credenziale Windows da usare per rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="873a3-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**  
  
## <a name="syntax"></a><span data-ttu-id="873a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="873a3-104">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="873a3-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="873a3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="873a3-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="873a3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="873a3-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="873a3-107">Attributes</span></span>  
  
|<span data-ttu-id="873a3-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="873a3-108">Attribute</span></span>|<span data-ttu-id="873a3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="873a3-109">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="873a3-110">Imposta la preferenza di rappresentazione che il client comunica al server.</span><span class="sxs-lookup"><span data-stu-id="873a3-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="873a3-111">La modalità di rappresentazione selezionata dal client non viene imposta sul server.</span><span class="sxs-lookup"><span data-stu-id="873a3-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="873a3-112">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="873a3-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="873a3-113">-Identificazione: il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="873a3-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="873a3-114">-Rappresentazione: il server può rappresentare il contesto di sicurezza del client nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="873a3-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="873a3-115">-Delega: il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="873a3-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="873a3-116">-Anonimo: il server non può rappresentare o identificare il client.</span><span class="sxs-lookup"><span data-stu-id="873a3-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="873a3-117">-None: non è stato assegnato un livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="873a3-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="873a3-118">L'impostazione predefinita è Identification.</span><span class="sxs-lookup"><span data-stu-id="873a3-118">The default is Identification.</span></span> <span data-ttu-id="873a3-119">L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="873a3-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="873a3-120">L'impostazione di questa proprietà su `true` consente di usare l'autenticazione NTLM se Kerberos non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="873a3-120">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="873a3-121">L'impostazione di questa proprietà su `false` fa sì che Windows Communication Foundation (WCF) faccia il possibile tentativo di generare un'eccezione se viene utilizzata l'autenticazione NTLM.</span><span class="sxs-lookup"><span data-stu-id="873a3-121">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="873a3-122">Si noti che l'impostazione di questa proprietà su `false` potrebbe non impedire l'invio di credenziali NTLM nella rete.</span><span class="sxs-lookup"><span data-stu-id="873a3-122">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="873a3-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="873a3-123">Child Elements</span></span>  
 <span data-ttu-id="873a3-124">No.</span><span class="sxs-lookup"><span data-stu-id="873a3-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="873a3-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="873a3-125">Parent Elements</span></span>  
  
|<span data-ttu-id="873a3-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="873a3-126">Element</span></span>|<span data-ttu-id="873a3-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="873a3-127">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="873a3-128">Specifica le credenziali usate per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="873a3-128">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="873a3-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="873a3-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="873a3-130">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="873a3-130">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="873a3-131">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="873a3-131">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="873a3-132">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="873a3-132">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
