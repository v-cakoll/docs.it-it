---
title: '&lt;deselezionare&gt; elemento per authenticationModules (impostazioni di rete)'
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 94e0242ca685e8b0118a55ba44fb0569c13f10f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32751987"
---
# <a name="ltcleargt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="e521e-102">&lt;deselezionare&gt; elemento per authenticationModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="e521e-102">&lt;clear&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="e521e-103">Cancella tutti i moduli di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e521e-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="e521e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e521e-104">\<configuration></span></span>  
<span data-ttu-id="e521e-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e521e-105">\<system.net></span></span>  
<span data-ttu-id="e521e-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="e521e-106">\<authenticationModules></span></span>  
<span data-ttu-id="e521e-107">\<cancellare ></span><span class="sxs-lookup"><span data-stu-id="e521e-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e521e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e521e-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e521e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e521e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e521e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e521e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e521e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e521e-111">Attributes</span></span>  
 <span data-ttu-id="e521e-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e521e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e521e-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e521e-113">Child Elements</span></span>  
 <span data-ttu-id="e521e-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e521e-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e521e-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e521e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e521e-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e521e-116">**Element**</span></span>|<span data-ttu-id="e521e-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e521e-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e521e-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="e521e-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="e521e-119">Specifica i moduli utilizzati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="e521e-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e521e-120">Note</span><span class="sxs-lookup"><span data-stu-id="e521e-120">Remarks</span></span>  
 <span data-ttu-id="e521e-121">Il `clear` elemento rimuove tutti i moduli di autenticazione che sono stati definiti nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e521e-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e521e-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e521e-122">Configuration Files</span></span>  
 <span data-ttu-id="e521e-123">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e521e-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e521e-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="e521e-124">Example</span></span>  
 <span data-ttu-id="e521e-125">Nell'esempio seguente rimuove tutti i moduli di autenticazione configurato.</span><span class="sxs-lookup"><span data-stu-id="e521e-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e521e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e521e-126">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="e521e-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="e521e-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
