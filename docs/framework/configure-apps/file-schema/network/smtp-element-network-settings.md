---
title: '&lt;SMTP&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 598fe3dc2a49187e923cd689f863d0a3327e735f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="689f0-102">&lt;SMTP&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="689f0-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="689f0-103">Configura il formato di consegna, il metodo di consegna e l'indirizzo del mittente per l'invio dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="689f0-103">Configures the delivery format, delivery method, and from address for sending e-mails.</span></span>  
  
 <span data-ttu-id="689f0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="689f0-104">\<configuration></span></span>  
<span data-ttu-id="689f0-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="689f0-105">\<system.net></span></span>  
<span data-ttu-id="689f0-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="689f0-106">\<mailSettings></span></span>  
<span data-ttu-id="689f0-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="689f0-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="689f0-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="689f0-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="689f0-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="689f0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="689f0-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="689f0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="689f0-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="689f0-111">Attributes</span></span>  
  
|<span data-ttu-id="689f0-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="689f0-112">Attribute</span></span>|<span data-ttu-id="689f0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="689f0-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="689f0-114">Specifica il formato di consegna dei messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="689f0-114">Specifies the delivery format for outgoing e-mails.</span></span> <span data-ttu-id="689f0-115">I valori accettabili sono SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="689f0-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="689f0-116">Specifica il metodo di recapito dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="689f0-116">Specifies the delivery method for e-mails.</span></span> <span data-ttu-id="689f0-117">Valori accettabili sono rete pickupDirectoryFromIis e specifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="689f0-117">Acceptable values are network, pickupDirectoryFromIis, and specifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="689f0-118">Specifica l'indirizzo del mittente dei messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="689f0-118">Specifies the from address for outgoing e-mails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="689f0-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="689f0-119">Child Elements</span></span>  
  
|<span data-ttu-id="689f0-120">Attributo</span><span class="sxs-lookup"><span data-stu-id="689f0-120">Attribute</span></span>|<span data-ttu-id="689f0-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="689f0-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="689f0-122">Configura la directory locale per un server SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="689f0-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="689f0-123">Consente di configurare le opzioni di rete per un server SMTP esterno.</span><span class="sxs-lookup"><span data-stu-id="689f0-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="689f0-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="689f0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="689f0-125">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="689f0-125">**Element**</span></span>|<span data-ttu-id="689f0-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="689f0-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="689f0-127">Elemento \<mailSettings> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="689f0-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="689f0-128">Configura opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="689f0-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="689f0-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="689f0-129">Example</span></span>  
 <span data-ttu-id="689f0-130">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="689f0-130">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
  
## <a name="see-also"></a><span data-ttu-id="689f0-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="689f0-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="689f0-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="689f0-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
