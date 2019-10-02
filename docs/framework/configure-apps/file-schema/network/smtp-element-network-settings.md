---
title: Elemento <smtp> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 2105a6dd25a7f6e5e4c1ce286be7f60beae1dca0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697605"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="b007b-102">Elemento > \<smtp (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="b007b-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="b007b-103">Configura il formato di recapito, il metodo di recapito e l'indirizzo di posta elettronica per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="b007b-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[<span data-ttu-id="b007b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b007b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b007b-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b007b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="b007b-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b007b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="b007b-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<smtp >**</span><span class="sxs-lookup"><span data-stu-id="b007b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b007b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b007b-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b007b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b007b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b007b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b007b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b007b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="b007b-111">Attributes</span></span>  
  
|<span data-ttu-id="b007b-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="b007b-112">Attribute</span></span>|<span data-ttu-id="b007b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b007b-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="b007b-114">Specifica il formato di recapito per i messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="b007b-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="b007b-115">I valori accettabili sono SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="b007b-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="b007b-116">Specifica il metodo di recapito dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b007b-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="b007b-117">I valori accettabili sono Network, PickupDirectoryFromIis e SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="b007b-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="b007b-118">Specifica l'indirizzo da per i messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="b007b-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b007b-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b007b-119">Child Elements</span></span>  
  
|<span data-ttu-id="b007b-120">Attributo</span><span class="sxs-lookup"><span data-stu-id="b007b-120">Attribute</span></span>|<span data-ttu-id="b007b-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b007b-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="b007b-122">Configura la directory locale per un server SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="b007b-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="b007b-123">Configura le opzioni di rete per un server SMTP esterno.</span><span class="sxs-lookup"><span data-stu-id="b007b-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b007b-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b007b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b007b-125">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="b007b-125">**Element**</span></span>|<span data-ttu-id="b007b-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b007b-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b007b-127">Elemento \<mailSettings> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="b007b-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="b007b-128">Configura le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b007b-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b007b-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="b007b-129">Example</span></span>  
 <span data-ttu-id="b007b-130">Nell'esempio seguente vengono specificati i parametri SMTP appropriati per inviare messaggi di posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="b007b-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b007b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b007b-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="b007b-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="b007b-132">Network Settings Schema</span></span>](index.md)
