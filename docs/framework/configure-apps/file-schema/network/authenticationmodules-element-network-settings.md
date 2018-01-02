---
title: '&lt;authenticationModules&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: e7fcaee557884d0c24b7bb15f2424a9e0a413439
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltauthenticationmodulesgt-element-network-settings"></a><span data-ttu-id="e364a-102">&lt;authenticationModules&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="e364a-102">&lt;authenticationModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="e364a-103">Specifica i moduli utilizzati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="e364a-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="e364a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e364a-104">\<configuration></span></span>  
<span data-ttu-id="e364a-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="e364a-105">\<system.net></span></span>  
<span data-ttu-id="e364a-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="e364a-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e364a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e364a-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e364a-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e364a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e364a-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e364a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e364a-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e364a-110">Attributes</span></span>  
 <span data-ttu-id="e364a-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e364a-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e364a-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e364a-112">Child Elements</span></span>  
  
|<span data-ttu-id="e364a-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e364a-113">**Element**</span></span>|<span data-ttu-id="e364a-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e364a-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e364a-115">add</span><span class="sxs-lookup"><span data-stu-id="e364a-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="e364a-116">Aggiunge un modulo di autenticazione all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e364a-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="e364a-117">clear</span><span class="sxs-lookup"><span data-stu-id="e364a-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="e364a-118">Cancella tutti i moduli di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e364a-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="e364a-119">remove</span><span class="sxs-lookup"><span data-stu-id="e364a-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="e364a-120">Rimuove un modulo di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e364a-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e364a-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e364a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e364a-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e364a-122">**Element**</span></span>|<span data-ttu-id="e364a-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e364a-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e364a-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="e364a-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="e364a-125">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e364a-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e364a-126">Note</span><span class="sxs-lookup"><span data-stu-id="e364a-126">Remarks</span></span>  
 <span data-ttu-id="e364a-127">Il `authenticationModule` elemento specifica i moduli di autenticazione che dirigono il processo di autenticazione con un server.</span><span class="sxs-lookup"><span data-stu-id="e364a-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="e364a-128">Un modulo di autenticazione deve implementare il <xref:System.Net.IAuthenticationModule> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e364a-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e364a-129">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e364a-129">Configuration Files</span></span>  
 <span data-ttu-id="e364a-130">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e364a-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e364a-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="e364a-131">Example</span></span>  
 <span data-ttu-id="e364a-132">L'esempio seguente Abilita un modulo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="e364a-132">The following example enables an authentication module.</span></span> <span data-ttu-id="e364a-133">È necessario sostituire i valori per la versione e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="e364a-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e364a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e364a-134">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="e364a-135">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="e364a-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
