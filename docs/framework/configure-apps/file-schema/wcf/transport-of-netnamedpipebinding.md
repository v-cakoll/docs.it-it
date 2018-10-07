---
title: '&lt;transport&gt; di &lt;netNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: c42132f774257589b9020248188ee8d972eb92ba
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837050"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="e51e9-102">&lt;transport&gt; di &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e51e9-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="e51e9-103">Definisce le impostazioni di sicurezza del trasporto per una named pipe.</span><span class="sxs-lookup"><span data-stu-id="e51e9-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="e51e9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e51e9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e51e9-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="e51e9-105">\<bindings></span></span>  
<span data-ttu-id="e51e9-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="e51e9-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="e51e9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="e51e9-107">\<binding></span></span>  
<span data-ttu-id="e51e9-108">\<security></span><span class="sxs-lookup"><span data-stu-id="e51e9-108">\<security></span></span>  
<span data-ttu-id="e51e9-109">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="e51e9-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e51e9-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e51e9-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e51e9-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e51e9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e51e9-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e51e9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e51e9-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="e51e9-113">Attributes</span></span>  
  
|<span data-ttu-id="e51e9-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="e51e9-114">Attribute</span></span>|<span data-ttu-id="e51e9-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e51e9-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e51e9-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="e51e9-116">protectionLevel</span></span>|<span data-ttu-id="e51e9-117">Definisce il livello di protezione della named pipe.</span><span class="sxs-lookup"><span data-stu-id="e51e9-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="e51e9-118">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="e51e9-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="e51e9-119">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="e51e9-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="e51e9-120">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="e51e9-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e51e9-121">-None: Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="e51e9-121">-   None: No protection.</span></span><br /><span data-ttu-id="e51e9-122">-Sign: I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="e51e9-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e51e9-123">-EncryptAndSign: I messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="e51e9-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="e51e9-124">Il valore predefinito è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="e51e9-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e51e9-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e51e9-125">Child Elements</span></span>  
 <span data-ttu-id="e51e9-126">nessuno</span><span class="sxs-lookup"><span data-stu-id="e51e9-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e51e9-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e51e9-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e51e9-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="e51e9-128">Element</span></span>|<span data-ttu-id="e51e9-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e51e9-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e51e9-130">\<security></span><span class="sxs-lookup"><span data-stu-id="e51e9-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="e51e9-131">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="e51e9-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e51e9-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e51e9-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="e51e9-133">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="e51e9-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e51e9-134">Associazioni</span><span class="sxs-lookup"><span data-stu-id="e51e9-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e51e9-135">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="e51e9-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e51e9-136">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="e51e9-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="e51e9-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="e51e9-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
