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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154972"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="a5adc-102">Elemento \<authenticationModules> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="a5adc-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="a5adc-103">Specifica i moduli usati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="a5adc-103">Specifies modules used to authenticate network requests.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a><span data-ttu-id="a5adc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5adc-104">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5adc-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a5adc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a5adc-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a5adc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5adc-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="a5adc-107">Attributes</span></span>  
 <span data-ttu-id="a5adc-108">No.</span><span class="sxs-lookup"><span data-stu-id="a5adc-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a5adc-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a5adc-109">Child Elements</span></span>  
  
|<span data-ttu-id="a5adc-110">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="a5adc-110">**Element**</span></span>|<span data-ttu-id="a5adc-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a5adc-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a5adc-112">add</span><span class="sxs-lookup"><span data-stu-id="a5adc-112">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a5adc-113">Aggiunge un modulo di autenticazione all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a5adc-113">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="a5adc-114">deselezionare</span><span class="sxs-lookup"><span data-stu-id="a5adc-114">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a5adc-115">Cancella tutti i moduli di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a5adc-115">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="a5adc-116">remove</span><span class="sxs-lookup"><span data-stu-id="a5adc-116">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="a5adc-117">Rimuove un modulo di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a5adc-117">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5adc-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a5adc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a5adc-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="a5adc-119">**Element**</span></span>|<span data-ttu-id="a5adc-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a5adc-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a5adc-121">system.net</span><span class="sxs-lookup"><span data-stu-id="a5adc-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a5adc-122">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5adc-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5adc-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="a5adc-123">Remarks</span></span>  
 <span data-ttu-id="a5adc-124">L' `authenticationModule` elemento specifica i moduli di autenticazione che eseguono il processo di autenticazione con un server.</span><span class="sxs-lookup"><span data-stu-id="a5adc-124">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="a5adc-125">Un modulo di autenticazione deve implementare l' <xref:System.Net.IAuthenticationModule> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a5adc-125">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a5adc-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="a5adc-126">Configuration Files</span></span>  
 <span data-ttu-id="a5adc-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a5adc-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5adc-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5adc-128">Example</span></span>  
 <span data-ttu-id="a5adc-129">Nell'esempio seguente viene abilitato un modulo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="a5adc-129">The following example enables an authentication module.</span></span> <span data-ttu-id="a5adc-130">È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="a5adc-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5adc-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a5adc-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="a5adc-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="a5adc-132">Network Settings Schema</span></span>](index.md)
