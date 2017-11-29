---
title: '&lt;mailSettings&gt; elemento (impostazioni di rete)'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a42b10574a1f44d310f86fe3fa99490f2f1981c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="74c5d-102">&lt;mailSettings&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="74c5d-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="74c5d-103">Configura opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="74c5d-103">Configures mail sending options.</span></span>  

<span data-ttu-id="74c5d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="74c5d-104">\<configuration></span></span>  
<span data-ttu-id="74c5d-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="74c5d-105">\<system.net></span></span>  
<span data-ttu-id="74c5d-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="74c5d-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74c5d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74c5d-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74c5d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="74c5d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="74c5d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="74c5d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74c5d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="74c5d-110">Attributes</span></span>  
 <span data-ttu-id="74c5d-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="74c5d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="74c5d-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="74c5d-112">Child Elements</span></span>  
  
|<span data-ttu-id="74c5d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="74c5d-113">Attribute</span></span>|<span data-ttu-id="74c5d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74c5d-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="74c5d-115">\<SMTP > elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="74c5d-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="74c5d-116">Configura opzioni Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="74c5d-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74c5d-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="74c5d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="74c5d-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="74c5d-118">**Element**</span></span>|<span data-ttu-id="74c5d-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="74c5d-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="74c5d-120">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="74c5d-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="74c5d-121">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="74c5d-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="74c5d-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="74c5d-122">Example</span></span>  
 <span data-ttu-id="74c5d-123">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="74c5d-123">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74c5d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74c5d-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="74c5d-125">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="74c5d-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
