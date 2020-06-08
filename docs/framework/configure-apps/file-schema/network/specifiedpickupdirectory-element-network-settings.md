---
title: Elemento <specifiedPickupDirectory> (impostazioni di rete)
description: L' <specifiedPickupDirectory> elemento impostazioni di rete configura la directory locale per le opzioni del server SMTP nell'.NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: f0c4c1845e9542d0f3b836ff03f16bdf2979ebd8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504498"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="35bda-103">Elemento \<specifiedPickupDirectory> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="35bda-103">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="35bda-104">Configura la directory locale per un server SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="35bda-104">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="35bda-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35bda-105">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35bda-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="35bda-106">Attributes and Elements</span></span>  
 <span data-ttu-id="35bda-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="35bda-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35bda-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="35bda-108">Attributes</span></span>  
  
|<span data-ttu-id="35bda-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="35bda-109">Attribute</span></span>|<span data-ttu-id="35bda-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35bda-110">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="35bda-111">Directory in cui le applicazioni salvano i messaggi di posta elettronica per l'elaborazione successiva da parte del server SMTP.</span><span class="sxs-lookup"><span data-stu-id="35bda-111">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35bda-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="35bda-112">Child Elements</span></span>  
 <span data-ttu-id="35bda-113">No.</span><span class="sxs-lookup"><span data-stu-id="35bda-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35bda-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="35bda-114">Parent Elements</span></span>  
  
|<span data-ttu-id="35bda-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="35bda-115">Element</span></span>|<span data-ttu-id="35bda-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35bda-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35bda-117">\<smtp>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="35bda-117">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="35bda-118">Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="35bda-118">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35bda-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="35bda-119">Remarks</span></span>  
 <span data-ttu-id="35bda-120">Con l'attributo `specifiedPickupDirectory` viene impostata la directory in cui nelle applicazioni vengono salvati i messaggi di posta elettronica da elaborare mediante il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="35bda-120">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35bda-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="35bda-121">Example</span></span>  
 <span data-ttu-id="35bda-122">Nell'esempio seguente viene specificato c:\maildrop come la directory di prelievo della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="35bda-122">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35bda-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35bda-123">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="35bda-124">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="35bda-124">Network Settings Schema</span></span>](index.md)
