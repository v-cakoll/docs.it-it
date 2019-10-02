---
title: Elemento <clear> per authenticationModules (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
ms.openlocfilehash: 052f7eef30500d37389585956728250a46b718a3
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698394"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="63cf0-102">Elemento > \<clear per authenticationModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="63cf0-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="63cf0-103">Cancella tutti i moduli di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="63cf0-103">Clears all authentication modules from the application.</span></span>  
  
[<span data-ttu-id="63cf0-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="63cf0-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="63cf0-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="63cf0-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="63cf0-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="63cf0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="63cf0-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="63cf0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63cf0-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63cf0-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63cf0-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="63cf0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="63cf0-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="63cf0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63cf0-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="63cf0-111">Attributes</span></span>  
 <span data-ttu-id="63cf0-112">No.</span><span class="sxs-lookup"><span data-stu-id="63cf0-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="63cf0-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="63cf0-113">Child Elements</span></span>  
 <span data-ttu-id="63cf0-114">No.</span><span class="sxs-lookup"><span data-stu-id="63cf0-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63cf0-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="63cf0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="63cf0-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="63cf0-116">**Element**</span></span>|<span data-ttu-id="63cf0-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="63cf0-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="63cf0-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="63cf0-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="63cf0-119">Specifica i moduli usati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="63cf0-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63cf0-120">Note</span><span class="sxs-lookup"><span data-stu-id="63cf0-120">Remarks</span></span>  
 <span data-ttu-id="63cf0-121">L'elemento `clear` rimuove tutti i moduli di autenticazione definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="63cf0-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="63cf0-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="63cf0-122">Configuration Files</span></span>  
 <span data-ttu-id="63cf0-123">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="63cf0-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63cf0-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="63cf0-124">Example</span></span>  
 <span data-ttu-id="63cf0-125">Nell'esempio seguente vengono rimossi tutti i moduli di autenticazione configurati.</span><span class="sxs-lookup"><span data-stu-id="63cf0-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63cf0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63cf0-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="63cf0-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="63cf0-127">Network Settings Schema</span></span>](index.md)
