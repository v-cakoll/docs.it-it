---
title: '&lt;rimuovere&gt; elemento per authenticationModules (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: eb8490241d4ec8a34a76aa6087c1f4d27d5cebb4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="1523d-102">&lt;rimuovere&gt; elemento per authenticationModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="1523d-102">&lt;remove&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="1523d-103">Rimuove un modulo di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1523d-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="1523d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1523d-104">\<configuration></span></span>  
<span data-ttu-id="1523d-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="1523d-105">\<system.net></span></span>  
<span data-ttu-id="1523d-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="1523d-106">\<authenticationModules></span></span>  
<span data-ttu-id="1523d-107">\<rimuovere ></span><span class="sxs-lookup"><span data-stu-id="1523d-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1523d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1523d-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1523d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1523d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1523d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1523d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1523d-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="1523d-111">Attributes</span></span>  
  
|<span data-ttu-id="1523d-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="1523d-112">**Attribute**</span></span>|<span data-ttu-id="1523d-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1523d-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="1523d-114">**type**</span><span class="sxs-lookup"><span data-stu-id="1523d-114">**type**</span></span>|<span data-ttu-id="1523d-115">Il nome del modulo di autenticazione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="1523d-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1523d-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1523d-116">Child Elements</span></span>  
 <span data-ttu-id="1523d-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1523d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1523d-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1523d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1523d-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1523d-119">**Element**</span></span>|<span data-ttu-id="1523d-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1523d-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1523d-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="1523d-121">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="1523d-122">Specifica i moduli utilizzati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="1523d-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1523d-123">Note</span><span class="sxs-lookup"><span data-stu-id="1523d-123">Remarks</span></span>  
 <span data-ttu-id="1523d-124">Il `remove` elemento rimuove i moduli di autenticazione che sono stati definiti nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1523d-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="1523d-125">Il valore per il `type` attributo deve essere un nome di classe valido.</span><span class="sxs-lookup"><span data-stu-id="1523d-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1523d-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1523d-126">Configuration Files</span></span>  
 <span data-ttu-id="1523d-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1523d-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1523d-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="1523d-128">Example</span></span>  
 <span data-ttu-id="1523d-129">Nell'esempio seguente rimuove un modulo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1523d-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1523d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1523d-130">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="1523d-131">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="1523d-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
