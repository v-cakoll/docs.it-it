---
title: Elemento <remove> per authenticationModules (impostazioni di rete)
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
ms.openlocfilehash: 9b73c0dc1fe161616c08ef0501241d55e9fea9bc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697935"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="064ed-102">Elemento > \<remove per authenticationModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="064ed-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="064ed-103">Rimuove un modulo di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="064ed-103">Removes an authentication module from the application.</span></span>  
  
[<span data-ttu-id="064ed-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="064ed-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="064ed-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="064ed-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="064ed-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="064ed-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="064ed-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="064ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="064ed-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="064ed-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="064ed-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="064ed-109">Attributes and Elements</span></span>  
 <span data-ttu-id="064ed-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="064ed-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="064ed-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="064ed-111">Attributes</span></span>  
  
|<span data-ttu-id="064ed-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="064ed-112">**Attribute**</span></span>|<span data-ttu-id="064ed-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="064ed-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="064ed-114">**type**</span><span class="sxs-lookup"><span data-stu-id="064ed-114">**type**</span></span>|<span data-ttu-id="064ed-115">Nome del modulo di autenticazione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="064ed-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="064ed-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="064ed-116">Child Elements</span></span>  
 <span data-ttu-id="064ed-117">No.</span><span class="sxs-lookup"><span data-stu-id="064ed-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="064ed-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="064ed-118">Parent Elements</span></span>  
  
|<span data-ttu-id="064ed-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="064ed-119">**Element**</span></span>|<span data-ttu-id="064ed-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="064ed-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="064ed-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="064ed-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="064ed-122">Specifica i moduli usati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="064ed-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="064ed-123">Note</span><span class="sxs-lookup"><span data-stu-id="064ed-123">Remarks</span></span>  
 <span data-ttu-id="064ed-124">L'elemento `remove` rimuove i moduli di autenticazione definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="064ed-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="064ed-125">Il valore dell'attributo `type` deve essere un nome di classe valido.</span><span class="sxs-lookup"><span data-stu-id="064ed-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="064ed-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="064ed-126">Configuration Files</span></span>  
 <span data-ttu-id="064ed-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="064ed-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="064ed-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="064ed-128">Example</span></span>  
 <span data-ttu-id="064ed-129">Nell'esempio seguente viene rimosso un modulo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="064ed-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="064ed-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="064ed-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="064ed-131">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="064ed-131">Network Settings Schema</span></span>](index.md)
