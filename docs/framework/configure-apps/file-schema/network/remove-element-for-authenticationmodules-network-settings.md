---
title: '&lt;rimuovere&gt; (elemento) per authenticationModules (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: 65b5b7f717912ecaee73a5b24e65d22b902a4e44
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180705"
---
# <a name="ltremovegt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="1f0f3-102">&lt;rimuovere&gt; (elemento) per authenticationModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="1f0f3-102">&lt;remove&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="1f0f3-103">Rimuove un modulo di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1f0f3-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="1f0f3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1f0f3-104">\<configuration></span></span>  
<span data-ttu-id="1f0f3-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="1f0f3-105">\<system.net></span></span>  
<span data-ttu-id="1f0f3-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="1f0f3-106">\<authenticationModules></span></span>  
<span data-ttu-id="1f0f3-107">\<rimuovere ></span><span class="sxs-lookup"><span data-stu-id="1f0f3-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f0f3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f0f3-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f0f3-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1f0f3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1f0f3-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1f0f3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f0f3-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="1f0f3-111">Attributes</span></span>  
  
|<span data-ttu-id="1f0f3-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="1f0f3-112">**Attribute**</span></span>|<span data-ttu-id="1f0f3-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1f0f3-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="1f0f3-114">**type**</span><span class="sxs-lookup"><span data-stu-id="1f0f3-114">**type**</span></span>|<span data-ttu-id="1f0f3-115">Il nome del modulo di autenticazione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="1f0f3-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f0f3-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1f0f3-116">Child Elements</span></span>  
 <span data-ttu-id="1f0f3-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1f0f3-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f0f3-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1f0f3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1f0f3-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1f0f3-119">**Element**</span></span>|<span data-ttu-id="1f0f3-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1f0f3-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1f0f3-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="1f0f3-121">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="1f0f3-122">Specifica i moduli usati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="1f0f3-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f0f3-123">Note</span><span class="sxs-lookup"><span data-stu-id="1f0f3-123">Remarks</span></span>  
 <span data-ttu-id="1f0f3-124">Il `remove` elemento rimuove i moduli di autenticazione che sono stati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1f0f3-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="1f0f3-125">Il valore per il `type` attributo deve essere un nome di classe valido.</span><span class="sxs-lookup"><span data-stu-id="1f0f3-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1f0f3-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1f0f3-126">Configuration Files</span></span>  
 <span data-ttu-id="1f0f3-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1f0f3-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f0f3-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f0f3-128">Example</span></span>  
 <span data-ttu-id="1f0f3-129">L'esempio seguente rimuove un modulo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1f0f3-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f0f3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f0f3-130">See Also</span></span>  
- <xref:System.Net.IAuthenticationModule>  
- <xref:System.Net.AuthenticationManager>  
- [<span data-ttu-id="1f0f3-131">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="1f0f3-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
