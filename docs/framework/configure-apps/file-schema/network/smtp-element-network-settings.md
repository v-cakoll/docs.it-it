---
title: Elemento <smtp> (impostazioni di rete)
description: L' <smtp> elemento impostazioni di rete configura il formato di recapito, il metodo di recapito e l'indirizzo mittente per l'invio di opzioni di posta elettronica nel .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: b30b82922a69ea660f4c4abfd808e89fa9945183
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504511"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="7e62d-103">Elemento \<smtp> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="7e62d-103">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="7e62d-104">Configura il formato di recapito, il metodo di recapito e l'indirizzo di posta elettronica per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="7e62d-104">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a><span data-ttu-id="7e62d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e62d-105">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e62d-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7e62d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="7e62d-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7e62d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e62d-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="7e62d-108">Attributes</span></span>  
  
|<span data-ttu-id="7e62d-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="7e62d-109">Attribute</span></span>|<span data-ttu-id="7e62d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e62d-110">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="7e62d-111">Specifica il formato di recapito per i messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="7e62d-111">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="7e62d-112">I valori accettabili sono SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="7e62d-112">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="7e62d-113">Specifica il metodo di recapito dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="7e62d-113">Specifies the delivery method for emails.</span></span> <span data-ttu-id="7e62d-114">I valori accettabili sono Network, PickupDirectoryFromIis e SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="7e62d-114">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="7e62d-115">Specifica l'indirizzo da per i messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="7e62d-115">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e62d-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7e62d-116">Child Elements</span></span>  
  
|<span data-ttu-id="7e62d-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="7e62d-117">Attribute</span></span>|<span data-ttu-id="7e62d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e62d-118">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="7e62d-119">Configura la directory locale per un server SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="7e62d-119">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="7e62d-120">Configura le opzioni di rete per un server SMTP esterno.</span><span class="sxs-lookup"><span data-stu-id="7e62d-120">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e62d-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7e62d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7e62d-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="7e62d-122">**Element**</span></span>|<span data-ttu-id="7e62d-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7e62d-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7e62d-124">\<mailSettings>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="7e62d-124">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="7e62d-125">Configura le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="7e62d-125">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7e62d-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e62d-126">Example</span></span>  
 <span data-ttu-id="7e62d-127">Nell'esempio seguente vengono specificati i parametri SMTP appropriati per inviare messaggi di posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="7e62d-127">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7e62d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e62d-128">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="7e62d-129">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="7e62d-129">Network Settings Schema</span></span>](index.md)
