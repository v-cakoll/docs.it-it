---
title: '&lt;authenticationModules&gt; elemento (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6d7f811a5746fa07264a192efdc4c5c02323e1f4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743329"
---
# <a name="ltauthenticationmodulesgt-element-network-settings"></a><span data-ttu-id="fea9e-102">&lt;authenticationModules&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="fea9e-102">&lt;authenticationModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="fea9e-103">Specifica i moduli utilizzati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="fea9e-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="fea9e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fea9e-104">\<configuration></span></span>  
<span data-ttu-id="fea9e-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="fea9e-105">\<system.net></span></span>  
<span data-ttu-id="fea9e-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="fea9e-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea9e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fea9e-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fea9e-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fea9e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fea9e-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fea9e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fea9e-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="fea9e-110">Attributes</span></span>  
 <span data-ttu-id="fea9e-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fea9e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fea9e-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fea9e-112">Child Elements</span></span>  
  
|<span data-ttu-id="fea9e-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="fea9e-113">**Element**</span></span>|<span data-ttu-id="fea9e-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fea9e-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fea9e-115">add</span><span class="sxs-lookup"><span data-stu-id="fea9e-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="fea9e-116">Aggiunge un modulo di autenticazione all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fea9e-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="fea9e-117">clear</span><span class="sxs-lookup"><span data-stu-id="fea9e-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="fea9e-118">Cancella tutti i moduli di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fea9e-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="fea9e-119">remove</span><span class="sxs-lookup"><span data-stu-id="fea9e-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="fea9e-120">Rimuove un modulo di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fea9e-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fea9e-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fea9e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fea9e-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="fea9e-122">**Element**</span></span>|<span data-ttu-id="fea9e-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fea9e-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fea9e-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="fea9e-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="fea9e-125">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fea9e-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fea9e-126">Note</span><span class="sxs-lookup"><span data-stu-id="fea9e-126">Remarks</span></span>  
 <span data-ttu-id="fea9e-127">Il `authenticationModule` elemento specifica i moduli di autenticazione che dirigono il processo di autenticazione con un server.</span><span class="sxs-lookup"><span data-stu-id="fea9e-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="fea9e-128">Un modulo di autenticazione deve implementare il <xref:System.Net.IAuthenticationModule> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="fea9e-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fea9e-129">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="fea9e-129">Configuration Files</span></span>  
 <span data-ttu-id="fea9e-130">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="fea9e-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fea9e-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="fea9e-131">Example</span></span>  
 <span data-ttu-id="fea9e-132">L'esempio seguente Abilita un modulo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="fea9e-132">The following example enables an authentication module.</span></span> <span data-ttu-id="fea9e-133">È necessario sostituire i valori per la versione e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="fea9e-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fea9e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fea9e-134">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="fea9e-135">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="fea9e-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
