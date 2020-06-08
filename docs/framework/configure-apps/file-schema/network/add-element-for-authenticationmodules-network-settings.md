---
title: Elemento <add> per authenticationModules (impostazioni di rete)
description: L' <add> elemento impostazioni di rete per connectionManagement aggiunge un indirizzo IP o un nome DNS all'elenco di gestione connessione nella .NET Framework.
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
ms.openlocfilehash: 1a6d0f79f076a69cec33ac14f0e0f33f7c3c6577
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504641"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="d8797-103">Elemento \<add> per authenticationModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d8797-103">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="d8797-104">Aggiunge un modulo di autenticazione all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8797-104">Adds an authentication module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="d8797-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8797-105">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8797-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d8797-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d8797-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d8797-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8797-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="d8797-108">Attributes</span></span>  
  
|<span data-ttu-id="d8797-109">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="d8797-109">**Attribute**</span></span>|<span data-ttu-id="d8797-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d8797-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="d8797-111">Il nome completo del tipo (indicato dalla <xref:System.Type.FullName%2A> proprietà) e il nome dell'assembly (indicato dalla <xref:System.Reflection.Assembly.FullName%2A> proprietà), separati da una virgola.</span><span class="sxs-lookup"><span data-stu-id="d8797-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8797-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d8797-112">Child Elements</span></span>  
 <span data-ttu-id="d8797-113">No.</span><span class="sxs-lookup"><span data-stu-id="d8797-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8797-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d8797-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d8797-115">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d8797-115">**Element**</span></span>|<span data-ttu-id="d8797-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d8797-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d8797-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="d8797-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="d8797-118">Specifica i moduli usati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="d8797-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8797-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d8797-119">Remarks</span></span>  
 <span data-ttu-id="d8797-120">Con l'elemento `add` viene aggiunto un modulo di autenticazione alla fine dell'elenco dei moduli di autenticazione registrati.</span><span class="sxs-lookup"><span data-stu-id="d8797-120">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="d8797-121">I moduli di autenticazione vengono chiamati nell'ordine in cui sono stati aggiunti all'elenco.</span><span class="sxs-lookup"><span data-stu-id="d8797-121">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="d8797-122">Il valore dell' `type` attributo deve essere un nome di tipo valido e un nome di assembly corrispondente, separati da una virgola.</span><span class="sxs-lookup"><span data-stu-id="d8797-122">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d8797-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d8797-123">Configuration Files</span></span>  
 <span data-ttu-id="d8797-124">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d8797-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8797-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8797-125">Example</span></span>  
 <span data-ttu-id="d8797-126">Nell'esempio seguente vengono abilitati i moduli di autenticazione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d8797-126">The following example enables the default authentication modules.</span></span> <span data-ttu-id="d8797-127">È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="d8797-127">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d8797-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8797-128">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="d8797-129">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="d8797-129">Network Settings Schema</span></span>](index.md)
