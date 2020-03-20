---
title: Elemento <specifiedPickupDirectory> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 4b0cbaf9a7bfe2a9b1610811f4201253d219a6b2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154608"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="efb54-102">\<Elemento> specifiedPickupDirectory (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="efb54-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="efb54-103">Configura la directory locale per un server SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="efb54-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="efb54-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="efb54-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="efb54-105">&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="efb54-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="efb54-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>mailSettings**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="efb54-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="efb54-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>smtp**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="efb54-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="efb54-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>specifiedPickupDirectory**</span><span class="sxs-lookup"><span data-stu-id="efb54-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb54-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efb54-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efb54-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="efb54-110">Attributes and Elements</span></span>  
 <span data-ttu-id="efb54-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="efb54-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efb54-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="efb54-112">Attributes</span></span>  
  
|<span data-ttu-id="efb54-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="efb54-113">Attribute</span></span>|<span data-ttu-id="efb54-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efb54-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="efb54-115">La directory in cui le applicazioni salvano la posta elettronica per elaborazione successiva da parte del server SMTP.</span><span class="sxs-lookup"><span data-stu-id="efb54-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efb54-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="efb54-116">Child Elements</span></span>  
 <span data-ttu-id="efb54-117">No.</span><span class="sxs-lookup"><span data-stu-id="efb54-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="efb54-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="efb54-118">Parent Elements</span></span>  
  
|<span data-ttu-id="efb54-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="efb54-119">Element</span></span>|<span data-ttu-id="efb54-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efb54-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efb54-121">\<Elemento> smtp (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="efb54-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="efb54-122">Configura le opzioni di invio della posta SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="efb54-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efb54-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="efb54-123">Remarks</span></span>  
 <span data-ttu-id="efb54-124">Con l'attributo `specifiedPickupDirectory` viene impostata la directory in cui nelle applicazioni vengono salvati i messaggi di posta elettronica da elaborare mediante il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="efb54-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efb54-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="efb54-125">Example</span></span>  
 <span data-ttu-id="efb54-126">Nell'esempio riportato di seguito viene specificato c:.maildrop come directory di prelievo della posta.</span><span class="sxs-lookup"><span data-stu-id="efb54-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="efb54-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efb54-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="efb54-128">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="efb54-128">Network Settings Schema</span></span>](index.md)
