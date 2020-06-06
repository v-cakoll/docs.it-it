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
ms.openlocfilehash: 625c3cb82a8659c742b540724e5cf31be65a705e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089106"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="90bf4-102">Elemento \<smtp> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="90bf4-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="90bf4-103">Configura il formato di recapito, il metodo di recapito e l'indirizzo di posta elettronica per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="90bf4-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a><span data-ttu-id="90bf4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90bf4-104">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90bf4-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="90bf4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="90bf4-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="90bf4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90bf4-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="90bf4-107">Attributes</span></span>  
  
|<span data-ttu-id="90bf4-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="90bf4-108">Attribute</span></span>|<span data-ttu-id="90bf4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90bf4-109">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="90bf4-110">Specifica il formato di recapito per i messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="90bf4-110">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="90bf4-111">I valori accettabili sono SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="90bf4-111">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="90bf4-112">Specifica il metodo di recapito dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="90bf4-112">Specifies the delivery method for emails.</span></span> <span data-ttu-id="90bf4-113">I valori accettabili sono Network, PickupDirectoryFromIis e SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="90bf4-113">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="90bf4-114">Specifica l'indirizzo da per i messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="90bf4-114">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90bf4-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="90bf4-115">Child Elements</span></span>  
  
|<span data-ttu-id="90bf4-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="90bf4-116">Attribute</span></span>|<span data-ttu-id="90bf4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90bf4-117">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="90bf4-118">Configura la directory locale per un server SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="90bf4-118">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="90bf4-119">Configura le opzioni di rete per un server SMTP esterno.</span><span class="sxs-lookup"><span data-stu-id="90bf4-119">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90bf4-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="90bf4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="90bf4-121">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="90bf4-121">**Element**</span></span>|<span data-ttu-id="90bf4-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="90bf4-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="90bf4-123">\<mailSettings>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="90bf4-123">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="90bf4-124">Configura le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="90bf4-124">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="90bf4-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="90bf4-125">Example</span></span>  
 <span data-ttu-id="90bf4-126">Nell'esempio seguente vengono specificati i parametri SMTP appropriati per inviare messaggi di posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="90bf4-126">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="90bf4-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="90bf4-127">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="90bf4-128">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="90bf4-128">Network Settings Schema</span></span>](index.md)
