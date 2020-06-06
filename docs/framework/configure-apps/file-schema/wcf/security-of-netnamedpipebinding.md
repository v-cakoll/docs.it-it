---
title: <security> di <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 31ea31ce6880a770c966350cd931e487396c4d63
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736443"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="6e053-102">\<security> di \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="6e053-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="6e053-103">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="6e053-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="6e053-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e053-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e053-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6e053-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6e053-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6e053-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e053-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="6e053-107">Attributes</span></span>  
  
|<span data-ttu-id="6e053-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="6e053-108">Attribute</span></span>|<span data-ttu-id="6e053-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e053-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e053-110">mode</span><span class="sxs-lookup"><span data-stu-id="6e053-110">mode</span></span>|<span data-ttu-id="6e053-111">Specifica il tipo di sicurezza applicata a questa associazione.</span><span class="sxs-lookup"><span data-stu-id="6e053-111">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="6e053-112">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e053-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6e053-113">-None: Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6e053-113">-   None: This disables security.</span></span><br /><span data-ttu-id="6e053-114">-Transport: la sicurezza viene fornita utilizzando la sicurezza basata sul trasporto sottostante.</span><span class="sxs-lookup"><span data-stu-id="6e053-114">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="6e053-115">È possibile controllare il livello di protezione con questa modalità.</span><span class="sxs-lookup"><span data-stu-id="6e053-115">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="6e053-116">-Il valore predefinito è Transport.</span><span class="sxs-lookup"><span data-stu-id="6e053-116">-   The default value is Transport.</span></span> <span data-ttu-id="6e053-117">L'attributo è di tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="6e053-117">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e053-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6e053-118">Child Elements</span></span>  
  
|<span data-ttu-id="6e053-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e053-119">Element</span></span>|<span data-ttu-id="6e053-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e053-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e053-121">transport</span><span class="sxs-lookup"><span data-stu-id="6e053-121">transport</span></span>|<span data-ttu-id="6e053-122">Definisce le impostazioni di sicurezza per il trasporto.</span><span class="sxs-lookup"><span data-stu-id="6e053-122">Defines the security settings for the transport.</span></span> <span data-ttu-id="6e053-123">L'elemento è di tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="6e053-123">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e053-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6e053-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6e053-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e053-125">Element</span></span>|<span data-ttu-id="6e053-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e053-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e053-127">binding</span><span class="sxs-lookup"><span data-stu-id="6e053-127">binding</span></span>|<span data-ttu-id="6e053-128">Elemento di associazione di [\<netNamedPipeBinding>](netnamedpipebinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6e053-128">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e053-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6e053-129">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="6e053-130">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="6e053-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6e053-131">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="6e053-131">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="6e053-132">Binding</span><span class="sxs-lookup"><span data-stu-id="6e053-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6e053-133">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="6e053-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6e053-134">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="6e053-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
