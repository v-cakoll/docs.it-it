---
title: '&lt;aggiungere&gt; elemento per authenticationModules (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 471e36bb584164b851e7a06c0e682ba9872f7910
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="65ce9-102">&lt;aggiungere&gt; elemento per authenticationModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="65ce9-102">&lt;add&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="65ce9-103">Aggiunge un modulo di autenticazione all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="65ce9-103">Adds an authentication module to the application.</span></span>  
  
 <span data-ttu-id="65ce9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="65ce9-104">\<configuration></span></span>  
<span data-ttu-id="65ce9-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="65ce9-105">\<system.net></span></span>  
<span data-ttu-id="65ce9-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="65ce9-106">\<authenticationModules></span></span>  
<span data-ttu-id="65ce9-107">\<add></span><span class="sxs-lookup"><span data-stu-id="65ce9-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65ce9-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65ce9-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65ce9-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="65ce9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="65ce9-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="65ce9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65ce9-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="65ce9-111">Attributes</span></span>  
  
|<span data-ttu-id="65ce9-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="65ce9-112">**Attribute**</span></span>|<span data-ttu-id="65ce9-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="65ce9-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="65ce9-114">Il nome completo del tipo (indicato dal <xref:System.Type.FullName%2A> proprietà) e il nome dell'assembly (indicato dal <xref:System.Reflection.Assembly.FullName%2A> proprietà), separati da una virgola.</span><span class="sxs-lookup"><span data-stu-id="65ce9-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65ce9-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="65ce9-115">Child Elements</span></span>  
 <span data-ttu-id="65ce9-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="65ce9-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65ce9-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="65ce9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="65ce9-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="65ce9-118">**Element**</span></span>|<span data-ttu-id="65ce9-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="65ce9-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="65ce9-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="65ce9-120">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="65ce9-121">Specifica i moduli utilizzati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="65ce9-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65ce9-122">Note</span><span class="sxs-lookup"><span data-stu-id="65ce9-122">Remarks</span></span>  
 <span data-ttu-id="65ce9-123">Con l'elemento `add` viene aggiunto un modulo di autenticazione alla fine dell'elenco dei moduli di autenticazione registrati.</span><span class="sxs-lookup"><span data-stu-id="65ce9-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="65ce9-124">Moduli di autenticazione vengono chiamati nell'ordine in cui sono stati aggiunti all'elenco.</span><span class="sxs-lookup"><span data-stu-id="65ce9-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="65ce9-125">Il valore per il `type` attributo deve essere un nome di tipo valido e un nome di assembly corrispondente, separati da una virgola.</span><span class="sxs-lookup"><span data-stu-id="65ce9-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="65ce9-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="65ce9-126">Configuration Files</span></span>  
 <span data-ttu-id="65ce9-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="65ce9-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ce9-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="65ce9-128">Example</span></span>  
 <span data-ttu-id="65ce9-129">L'esempio seguente Abilita i moduli di autenticazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="65ce9-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="65ce9-130">È necessario sostituire i valori per la versione e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="65ce9-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="65ce9-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65ce9-131">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="65ce9-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="65ce9-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
