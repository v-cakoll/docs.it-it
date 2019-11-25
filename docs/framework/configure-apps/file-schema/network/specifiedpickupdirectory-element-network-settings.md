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
ms.openlocfilehash: 1acc724bb14c3610f14d06452c30b3d5dac42e13
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089070"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="a246b-102">\<elemento > specifiedPickupDirectory (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="a246b-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="a246b-103">Configura la directory locale per un server SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="a246b-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="a246b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a246b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a246b-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a246b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="a246b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<mailSettings**](mailsettings-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="a246b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="a246b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**SMTP**](smtp-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="a246b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="a246b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<SpecifiedPickupDirectory** ></span><span class="sxs-lookup"><span data-stu-id="a246b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a246b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a246b-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a246b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a246b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a246b-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a246b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a246b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="a246b-112">Attributes</span></span>  
  
|<span data-ttu-id="a246b-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="a246b-113">Attribute</span></span>|<span data-ttu-id="a246b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a246b-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="a246b-115">Directory in cui le applicazioni salvano i messaggi di posta elettronica per l'elaborazione successiva da parte del server SMTP.</span><span class="sxs-lookup"><span data-stu-id="a246b-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a246b-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a246b-116">Child Elements</span></span>  
 <span data-ttu-id="a246b-117">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="a246b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a246b-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a246b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a246b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="a246b-119">Element</span></span>|<span data-ttu-id="a246b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a246b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a246b-121">\<elemento > SMTP (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="a246b-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="a246b-122">Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="a246b-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a246b-123">Note</span><span class="sxs-lookup"><span data-stu-id="a246b-123">Remarks</span></span>  
 <span data-ttu-id="a246b-124">Con l'attributo `specifiedPickupDirectory` viene impostata la directory in cui nelle applicazioni vengono salvati i messaggi di posta elettronica da elaborare mediante il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="a246b-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a246b-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="a246b-125">Example</span></span>  
 <span data-ttu-id="a246b-126">Nell'esempio seguente viene specificato c:\maildrop come la directory di prelievo della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a246b-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a246b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a246b-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="a246b-128">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="a246b-128">Network Settings Schema</span></span>](index.md)
