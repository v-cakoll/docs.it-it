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
ms.openlocfilehash: 3c018c7d474286f7a9cde2d070e4b54d164b5b40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674610"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="c6d71-102">\<Cancella > (elemento) per authenticationModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="c6d71-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="c6d71-103">Cancella tutti i moduli di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c6d71-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="c6d71-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c6d71-104">\<configuration></span></span>  
<span data-ttu-id="c6d71-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="c6d71-105">\<system.net></span></span>  
<span data-ttu-id="c6d71-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="c6d71-106">\<authenticationModules></span></span>  
<span data-ttu-id="c6d71-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="c6d71-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d71-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6d71-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6d71-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c6d71-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c6d71-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c6d71-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6d71-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c6d71-111">Attributes</span></span>  
 <span data-ttu-id="c6d71-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c6d71-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c6d71-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c6d71-113">Child Elements</span></span>  
 <span data-ttu-id="c6d71-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c6d71-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6d71-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c6d71-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c6d71-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="c6d71-116">**Element**</span></span>|<span data-ttu-id="c6d71-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c6d71-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c6d71-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="c6d71-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="c6d71-119">Specifica i moduli usati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="c6d71-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6d71-120">Note</span><span class="sxs-lookup"><span data-stu-id="c6d71-120">Remarks</span></span>  
 <span data-ttu-id="c6d71-121">Il `clear` elemento rimuove tutti i moduli di autenticazione che sono stati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c6d71-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c6d71-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c6d71-122">Configuration Files</span></span>  
 <span data-ttu-id="c6d71-123">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c6d71-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6d71-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="c6d71-124">Example</span></span>  
 <span data-ttu-id="c6d71-125">L'esempio seguente rimuove tutti i moduli di autenticazione configurato.</span><span class="sxs-lookup"><span data-stu-id="c6d71-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6d71-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6d71-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="c6d71-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="c6d71-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
