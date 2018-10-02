---
title: '&lt;SMTP&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 61110413f43e95060aa2cfecb4acdb3ebaae14df
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48027585"
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="8367d-102">&lt;SMTP&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8367d-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="8367d-103">Consente di configurare il formato di consegna, il metodo di recapito e dall'indirizzo per l'invio di messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8367d-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="8367d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8367d-104">\<configuration></span></span>  
<span data-ttu-id="8367d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="8367d-105">\<system.net></span></span>  
<span data-ttu-id="8367d-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="8367d-106">\<mailSettings></span></span>  
<span data-ttu-id="8367d-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="8367d-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8367d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8367d-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8367d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8367d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8367d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8367d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8367d-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8367d-111">Attributes</span></span>  
  
|<span data-ttu-id="8367d-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8367d-112">Attribute</span></span>|<span data-ttu-id="8367d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8367d-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="8367d-114">Specifica il formato di recapito messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="8367d-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="8367d-115">I valori accettabili sono SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="8367d-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="8367d-116">Specifica il metodo di recapito messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8367d-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="8367d-117">I valori accettabili sono SpecifiedPickupDirectory, PickupDirectoryFromIis e rete.</span><span class="sxs-lookup"><span data-stu-id="8367d-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="8367d-118">Specifica l'indirizzo del mittente per messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="8367d-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8367d-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8367d-119">Child Elements</span></span>  
  
|<span data-ttu-id="8367d-120">Attributo</span><span class="sxs-lookup"><span data-stu-id="8367d-120">Attribute</span></span>|<span data-ttu-id="8367d-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8367d-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="8367d-122">Configura la directory locale per un server SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="8367d-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="8367d-123">Consente di configurare le opzioni di rete per un server SMTP esterno.</span><span class="sxs-lookup"><span data-stu-id="8367d-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8367d-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8367d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8367d-125">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="8367d-125">**Element**</span></span>|<span data-ttu-id="8367d-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8367d-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8367d-127">Elemento \<mailSettings> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8367d-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="8367d-128">Consente di configurare le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8367d-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8367d-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="8367d-129">Example</span></span>  
 <span data-ttu-id="8367d-130">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica usando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="8367d-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
  
## <a name="see-also"></a><span data-ttu-id="8367d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8367d-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="8367d-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="8367d-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
