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
ms.openlocfilehash: 954755c7576e0ca4dd7946926c77e1e7e18055e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713954"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="b01ae-102">&lt;mailSettings&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="b01ae-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="b01ae-103">Consente di configurare le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b01ae-103">Configures mail sending options.</span></span>  

<span data-ttu-id="b01ae-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b01ae-104">\<configuration></span></span>  
<span data-ttu-id="b01ae-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b01ae-105">\<system.net></span></span>  
<span data-ttu-id="b01ae-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="b01ae-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b01ae-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b01ae-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b01ae-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b01ae-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b01ae-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b01ae-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b01ae-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b01ae-110">Attributes</span></span>  
 <span data-ttu-id="b01ae-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b01ae-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b01ae-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b01ae-112">Child Elements</span></span>  
  
|<span data-ttu-id="b01ae-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b01ae-113">Attribute</span></span>|<span data-ttu-id="b01ae-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b01ae-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b01ae-115">\<SMTP > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="b01ae-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="b01ae-116">Configura le opzioni Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="b01ae-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b01ae-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b01ae-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b01ae-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="b01ae-118">**Element**</span></span>|<span data-ttu-id="b01ae-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b01ae-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b01ae-120">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="b01ae-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="b01ae-121">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b01ae-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b01ae-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="b01ae-122">Example</span></span>  
 <span data-ttu-id="b01ae-123">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica usando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="b01ae-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b01ae-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b01ae-124">See also</span></span>
- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="b01ae-125">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="b01ae-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
