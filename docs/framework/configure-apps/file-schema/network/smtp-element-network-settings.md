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
ms.openlocfilehash: 17b4050c43354da7e7ba6c3ea13a0c7621faf0a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="ea651-102">&lt;SMTP&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ea651-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="ea651-103">Configura il formato di consegna, il metodo di consegna e l'indirizzo del mittente per l'invio dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ea651-103">Configures the delivery format, delivery method, and from address for sending e-mails.</span></span>  
  
 <span data-ttu-id="ea651-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ea651-104">\<configuration></span></span>  
<span data-ttu-id="ea651-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="ea651-105">\<system.net></span></span>  
<span data-ttu-id="ea651-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="ea651-106">\<mailSettings></span></span>  
<span data-ttu-id="ea651-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="ea651-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea651-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea651-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea651-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ea651-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ea651-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ea651-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea651-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ea651-111">Attributes</span></span>  
  
|<span data-ttu-id="ea651-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="ea651-112">Attribute</span></span>|<span data-ttu-id="ea651-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea651-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="ea651-114">Specifica il formato di consegna dei messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="ea651-114">Specifies the delivery format for outgoing e-mails.</span></span> <span data-ttu-id="ea651-115">I valori accettabili sono SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="ea651-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="ea651-116">Specifica il metodo di recapito dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ea651-116">Specifies the delivery method for e-mails.</span></span> <span data-ttu-id="ea651-117">Valori accettabili sono rete pickupDirectoryFromIis e specifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="ea651-117">Acceptable values are network, pickupDirectoryFromIis, and specifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="ea651-118">Specifica l'indirizzo del mittente dei messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="ea651-118">Specifies the from address for outgoing e-mails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea651-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ea651-119">Child Elements</span></span>  
  
|<span data-ttu-id="ea651-120">Attributo</span><span class="sxs-lookup"><span data-stu-id="ea651-120">Attribute</span></span>|<span data-ttu-id="ea651-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea651-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="ea651-122">Configura la directory locale per un server SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="ea651-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="ea651-123">Consente di configurare le opzioni di rete per un server SMTP esterno.</span><span class="sxs-lookup"><span data-stu-id="ea651-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea651-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ea651-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ea651-125">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ea651-125">**Element**</span></span>|<span data-ttu-id="ea651-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ea651-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ea651-127">Elemento \<mailSettings> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ea651-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="ea651-128">Configura opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ea651-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ea651-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="ea651-129">Example</span></span>  
 <span data-ttu-id="ea651-130">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="ea651-130">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ea651-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea651-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="ea651-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ea651-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
