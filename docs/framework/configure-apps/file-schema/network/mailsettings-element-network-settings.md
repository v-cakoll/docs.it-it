---
title: '&lt;mailSettings&gt; elemento (impostazioni di rete)'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: ce7ec8bea57436ebd184cf0d593870999405f72f
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="47337-102">&lt;mailSettings&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="47337-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="47337-103">Configura opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="47337-103">Configures mail sending options.</span></span>  

<span data-ttu-id="47337-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="47337-104">\<configuration></span></span>  
<span data-ttu-id="47337-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="47337-105">\<system.net></span></span>  
<span data-ttu-id="47337-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="47337-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47337-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47337-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47337-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="47337-108">Attributes and Elements</span></span>  
 <span data-ttu-id="47337-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="47337-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47337-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="47337-110">Attributes</span></span>  
 <span data-ttu-id="47337-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="47337-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="47337-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="47337-112">Child Elements</span></span>  
  
|<span data-ttu-id="47337-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="47337-113">Attribute</span></span>|<span data-ttu-id="47337-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47337-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="47337-115">\<SMTP > elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="47337-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="47337-116">Configura opzioni Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="47337-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47337-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="47337-117">Parent Elements</span></span>  
  
|<span data-ttu-id="47337-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="47337-118">**Element**</span></span>|<span data-ttu-id="47337-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="47337-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="47337-120">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="47337-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="47337-121">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47337-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="47337-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="47337-122">Example</span></span>  
 <span data-ttu-id="47337-123">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="47337-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47337-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47337-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="47337-125">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="47337-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
