---
title: Elemento <authenticationModules> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: b502cc4a0958f074018d4b0ce6b3fb118b811c2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154972"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="a95c8-102">\<Elemento authenticationModules> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="a95c8-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="a95c8-103">Specifica i moduli utilizzati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="a95c8-103">Specifies modules used to authenticate network requests.</span></span>  

<span data-ttu-id="a95c8-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a95c8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a95c8-105">&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a95c8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="a95c8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModuli>**</span><span class="sxs-lookup"><span data-stu-id="a95c8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a95c8-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a95c8-107">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a95c8-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a95c8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a95c8-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a95c8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a95c8-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="a95c8-110">Attributes</span></span>  
 <span data-ttu-id="a95c8-111">No.</span><span class="sxs-lookup"><span data-stu-id="a95c8-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a95c8-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a95c8-112">Child Elements</span></span>  
  
|<span data-ttu-id="a95c8-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="a95c8-113">**Element**</span></span>|<span data-ttu-id="a95c8-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a95c8-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a95c8-115">aggiungi</span><span class="sxs-lookup"><span data-stu-id="a95c8-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a95c8-116">Aggiunge un modulo di autenticazione all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a95c8-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="a95c8-117">Chiaro</span><span class="sxs-lookup"><span data-stu-id="a95c8-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a95c8-118">Cancella tutti i moduli di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a95c8-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="a95c8-119">rimozione</span><span class="sxs-lookup"><span data-stu-id="a95c8-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a95c8-120">Rimuove un modulo di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a95c8-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a95c8-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a95c8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a95c8-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="a95c8-122">**Element**</span></span>|<span data-ttu-id="a95c8-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a95c8-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a95c8-124">system.net</span><span class="sxs-lookup"><span data-stu-id="a95c8-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a95c8-125">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a95c8-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a95c8-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a95c8-126">Remarks</span></span>  
 <span data-ttu-id="a95c8-127">L'elemento `authenticationModule` specifica i moduli di autenticazione che eseguono il processo di autenticazione con un server.</span><span class="sxs-lookup"><span data-stu-id="a95c8-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="a95c8-128">Un modulo di <xref:System.Net.IAuthenticationModule> autenticazione deve implementare l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a95c8-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a95c8-129">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="a95c8-129">Configuration Files</span></span>  
 <span data-ttu-id="a95c8-130">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a95c8-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a95c8-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="a95c8-131">Example</span></span>  
 <span data-ttu-id="a95c8-132">Nell'esempio seguente viene abilitato un modulo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="a95c8-132">The following example enables an authentication module.</span></span> <span data-ttu-id="a95c8-133">È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="a95c8-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a95c8-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a95c8-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="a95c8-135">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="a95c8-135">Network Settings Schema</span></span>](index.md)
