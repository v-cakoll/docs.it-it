---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: f295fe48e194611c80b78c0c23ab3e66ea1c0b64
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400506"
---
# \<clientCredentials>
<span data-ttu-id="6f9bb-101">Specifica le credenziali usate per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-101">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="6f9bb-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f9bb-102">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f9bb-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6f9bb-103">Attributes and Elements</span></span>  
 <span data-ttu-id="6f9bb-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f9bb-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="6f9bb-105">Attributes</span></span>  
  
|<span data-ttu-id="6f9bb-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="6f9bb-106">Attribute</span></span>|<span data-ttu-id="6f9bb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f9bb-107">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="6f9bb-108">Valore booleano che specifica se un utente interattivo può essere coinvolto nella selezione di una credenziale client in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-108">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="6f9bb-109">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-109">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="6f9bb-110">Stringa che specifica il tipo di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-110">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f9bb-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6f9bb-111">Child Elements</span></span>  
  
|<span data-ttu-id="6f9bb-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f9bb-112">Element</span></span>|<span data-ttu-id="6f9bb-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f9bb-113">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="6f9bb-114">Specifica il certificato usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-114">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="6f9bb-115">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-115">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[\<httpDigest>](httpdigest-element.md)|<span data-ttu-id="6f9bb-116">Specifica un digest usato per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-116">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="6f9bb-117">L'elemento è di tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-117">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="6f9bb-118">Specifica un tipo di token personalizzato usato per autenticare il client presso un servizio token di sicurezza (STS, Secure Token Service).</span><span class="sxs-lookup"><span data-stu-id="6f9bb-118">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="6f9bb-119">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-119">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="6f9bb-120">Specifica una credenziale peer corrente.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-120">Specifies a current peer credential.</span></span> <span data-ttu-id="6f9bb-121">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-121">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="6f9bb-122">Specifica il certificato usato per autenticare il servizio presso il client e fornisce una struttura per l'impostazione delle opzioni del certificato.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-122">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="6f9bb-123">Questo certificato deve essere fornito fuori banda dal servizio al client.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-123">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="6f9bb-124">L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-124">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[\<windows>](windows-of-clientcredentials-element.md)|<span data-ttu-id="6f9bb-125">Specifica una credenziale Windows.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-125">Specifies a Windows credential.</span></span> <span data-ttu-id="6f9bb-126">Il valore predefinito è la credenziale del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-126">The default is the credential of the current thread.</span></span> <span data-ttu-id="6f9bb-127">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-127">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6f9bb-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6f9bb-128">Parent Elements</span></span>  
  
|<span data-ttu-id="6f9bb-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f9bb-129">Element</span></span>|<span data-ttu-id="6f9bb-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f9bb-130">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="6f9bb-131">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-131">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f9bb-132">Commenti</span><span class="sxs-lookup"><span data-stu-id="6f9bb-132">Remarks</span></span>  
 <span data-ttu-id="6f9bb-133">Le credenziali client sono usate per autenticare i client presso i servizi nei casi in cui non è richiesta l'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-133">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="6f9bb-134">È inoltre possibile usare questa sezione di configurazione per specificare i certificati di servizio negli scenari in cui il client deve usare il certificato di un servizio per proteggere i messaggi inviati a un servizio.</span><span class="sxs-lookup"><span data-stu-id="6f9bb-134">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f9bb-135">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6f9bb-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="6f9bb-136">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="6f9bb-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6f9bb-137">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="6f9bb-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
