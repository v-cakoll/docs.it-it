---
title: Elemento <add> per authenticationModules (impostazioni di rete)
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
ms.openlocfilehash: 4181a045079bdb455a63ebda722dd6b0daf33c4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155115"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="3fa7d-102">\<add> elemento per authenticationModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="3fa7d-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="3fa7d-103">Aggiunge un modulo di autenticazione all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3fa7d-103">Adds an authentication module to the application.</span></span>  

<span data-ttu-id="3fa7d-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3fa7d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3fa7d-105">&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3fa7d-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="3fa7d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModuli>**](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3fa7d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="3fa7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**</span><span class="sxs-lookup"><span data-stu-id="3fa7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3fa7d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fa7d-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fa7d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3fa7d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3fa7d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3fa7d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fa7d-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="3fa7d-111">Attributes</span></span>  
  
|<span data-ttu-id="3fa7d-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="3fa7d-112">**Attribute**</span></span>|<span data-ttu-id="3fa7d-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3fa7d-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="3fa7d-114">Il nome completo del <xref:System.Type.FullName%2A> tipo (indicato dalla proprietà) e il <xref:System.Reflection.Assembly.FullName%2A> nome dell'assembly (indicato dalla proprietà), separati da una virgola.</span><span class="sxs-lookup"><span data-stu-id="3fa7d-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3fa7d-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3fa7d-115">Child Elements</span></span>  
 <span data-ttu-id="3fa7d-116">No.</span><span class="sxs-lookup"><span data-stu-id="3fa7d-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fa7d-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3fa7d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3fa7d-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="3fa7d-118">**Element**</span></span>|<span data-ttu-id="3fa7d-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3fa7d-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3fa7d-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="3fa7d-120">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="3fa7d-121">Specifica i moduli utilizzati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="3fa7d-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fa7d-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3fa7d-122">Remarks</span></span>  
 <span data-ttu-id="3fa7d-123">Con l'elemento `add` viene aggiunto un modulo di autenticazione alla fine dell'elenco dei moduli di autenticazione registrati.</span><span class="sxs-lookup"><span data-stu-id="3fa7d-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="3fa7d-124">I moduli di autenticazione vengono chiamati nell'ordine in cui sono stati aggiunti all'elenco.</span><span class="sxs-lookup"><span data-stu-id="3fa7d-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="3fa7d-125">Il valore `type` dell'attributo deve essere un nome di tipo valido e il nome dell'assembly corrispondente, separati da una virgola.</span><span class="sxs-lookup"><span data-stu-id="3fa7d-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3fa7d-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="3fa7d-126">Configuration Files</span></span>  
 <span data-ttu-id="3fa7d-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3fa7d-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fa7d-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="3fa7d-128">Example</span></span>  
 <span data-ttu-id="3fa7d-129">Nell'esempio seguente vengono abilitati i moduli di autenticazione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3fa7d-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="3fa7d-130">È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="3fa7d-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3fa7d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fa7d-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="3fa7d-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="3fa7d-132">Network Settings Schema</span></span>](index.md)
