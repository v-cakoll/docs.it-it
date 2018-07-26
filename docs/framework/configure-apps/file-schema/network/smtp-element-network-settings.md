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
manager: markl
ms.openlocfilehash: 9b6e01906c31316cfa8f148ed96944f309517f95
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874923"
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="10ddc-102">&lt;SMTP&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="10ddc-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="10ddc-103">Consente di configurare il formato di consegna, il metodo di recapito e dall'indirizzo per l'invio di messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="10ddc-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="10ddc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="10ddc-104">\<configuration></span></span>  
<span data-ttu-id="10ddc-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="10ddc-105">\<system.net></span></span>  
<span data-ttu-id="10ddc-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="10ddc-106">\<mailSettings></span></span>  
<span data-ttu-id="10ddc-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="10ddc-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ddc-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10ddc-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10ddc-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="10ddc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="10ddc-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="10ddc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10ddc-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="10ddc-111">Attributes</span></span>  
  
|<span data-ttu-id="10ddc-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="10ddc-112">Attribute</span></span>|<span data-ttu-id="10ddc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10ddc-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="10ddc-114">Specifica il formato di recapito messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="10ddc-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="10ddc-115">I valori accettabili sono SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="10ddc-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="10ddc-116">Specifica il metodo di recapito messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="10ddc-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="10ddc-117">I valori accettabili sono SpecifiedPickupDirectory, PickupDirectoryFromIis e rete.</span><span class="sxs-lookup"><span data-stu-id="10ddc-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="10ddc-118">Specifica l'indirizzo del mittente per messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="10ddc-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10ddc-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="10ddc-119">Child Elements</span></span>  
  
|<span data-ttu-id="10ddc-120">Attributo</span><span class="sxs-lookup"><span data-stu-id="10ddc-120">Attribute</span></span>|<span data-ttu-id="10ddc-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10ddc-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="10ddc-122">Configura la directory locale per un server SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="10ddc-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="10ddc-123">Consente di configurare le opzioni di rete per un server SMTP esterno.</span><span class="sxs-lookup"><span data-stu-id="10ddc-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10ddc-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="10ddc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="10ddc-125">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="10ddc-125">**Element**</span></span>|<span data-ttu-id="10ddc-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="10ddc-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="10ddc-127">Elemento \<mailSettings> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="10ddc-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="10ddc-128">Consente di configurare le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="10ddc-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10ddc-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="10ddc-129">Example</span></span>  
 <span data-ttu-id="10ddc-130">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica usando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="10ddc-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="10ddc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10ddc-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="10ddc-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="10ddc-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
