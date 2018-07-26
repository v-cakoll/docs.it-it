---
title: '&lt;mailSettings&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a9afd992a12392ae0ad1c27eea305cb7e367686d
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874416"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="af093-102">&lt;mailSettings&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="af093-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="af093-103">Consente di configurare le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="af093-103">Configures mail sending options.</span></span>  

<span data-ttu-id="af093-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="af093-104">\<configuration></span></span>  
<span data-ttu-id="af093-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="af093-105">\<system.net></span></span>  
<span data-ttu-id="af093-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="af093-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af093-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af093-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af093-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="af093-108">Attributes and Elements</span></span>  
 <span data-ttu-id="af093-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="af093-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af093-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="af093-110">Attributes</span></span>  
 <span data-ttu-id="af093-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="af093-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af093-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="af093-112">Child Elements</span></span>  
  
|<span data-ttu-id="af093-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="af093-113">Attribute</span></span>|<span data-ttu-id="af093-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af093-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="af093-115">\<SMTP > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="af093-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="af093-116">Configura le opzioni Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="af093-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af093-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="af093-117">Parent Elements</span></span>  
  
|<span data-ttu-id="af093-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="af093-118">**Element**</span></span>|<span data-ttu-id="af093-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="af093-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="af093-120">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="af093-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="af093-121">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af093-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="af093-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="af093-122">Example</span></span>  
 <span data-ttu-id="af093-123">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica usando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="af093-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="af093-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af093-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="af093-125">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="af093-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
