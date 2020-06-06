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
ms.openlocfilehash: e3abd1b4c76ebda885703ccf961d58657b582f19
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087504"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="be9e5-102">Elemento \<clear> per authenticationModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="be9e5-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="be9e5-103">Cancella tutti i moduli di autenticazione dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="be9e5-103">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="be9e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be9e5-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be9e5-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="be9e5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="be9e5-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="be9e5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be9e5-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="be9e5-107">Attributes</span></span>  
 <span data-ttu-id="be9e5-108">No.</span><span class="sxs-lookup"><span data-stu-id="be9e5-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="be9e5-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="be9e5-109">Child Elements</span></span>  
 <span data-ttu-id="be9e5-110">No.</span><span class="sxs-lookup"><span data-stu-id="be9e5-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be9e5-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="be9e5-111">Parent Elements</span></span>  
  
|<span data-ttu-id="be9e5-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="be9e5-112">**Element**</span></span>|<span data-ttu-id="be9e5-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="be9e5-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="be9e5-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="be9e5-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="be9e5-115">Specifica i moduli usati per autenticare le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="be9e5-115">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be9e5-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="be9e5-116">Remarks</span></span>  
 <span data-ttu-id="be9e5-117">L' `clear` elemento rimuove tutti i moduli di autenticazione definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="be9e5-117">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="be9e5-118">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="be9e5-118">Configuration Files</span></span>  
 <span data-ttu-id="be9e5-119">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="be9e5-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be9e5-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="be9e5-120">Example</span></span>  
 <span data-ttu-id="be9e5-121">Nell'esempio seguente vengono rimossi tutti i moduli di autenticazione configurati.</span><span class="sxs-lookup"><span data-stu-id="be9e5-121">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="be9e5-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="be9e5-122">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="be9e5-123">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="be9e5-123">Network Settings Schema</span></span>](index.md)
