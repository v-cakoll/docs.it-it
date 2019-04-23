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
ms.openlocfilehash: a459fee557285935c383dcfaf512c8a8a9aea570
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099274"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="2d97e-102">\<specifiedPickupDirectory > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2d97e-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="2d97e-103">Configura la directory locale per un server SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="2d97e-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="2d97e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2d97e-104">\<configuration></span></span>  
<span data-ttu-id="2d97e-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="2d97e-105">\<system.net></span></span>  
<span data-ttu-id="2d97e-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="2d97e-106">\<mailSettings></span></span>  
<span data-ttu-id="2d97e-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="2d97e-107">\<smtp></span></span>  
<span data-ttu-id="2d97e-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="2d97e-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d97e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d97e-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d97e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2d97e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2d97e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2d97e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d97e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2d97e-112">Attributes</span></span>  
  
|<span data-ttu-id="2d97e-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="2d97e-113">Attribute</span></span>|<span data-ttu-id="2d97e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d97e-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="2d97e-115">La directory in cui le applicazioni salvano i messaggio di posta elettronica per l'elaborazione successiva con il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="2d97e-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d97e-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2d97e-116">Child Elements</span></span>  
 <span data-ttu-id="2d97e-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2d97e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d97e-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2d97e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2d97e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d97e-119">Element</span></span>|<span data-ttu-id="2d97e-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d97e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d97e-121">\<SMTP > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2d97e-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="2d97e-122">Consente di configurare le opzioni di invio della posta elettronica SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="2d97e-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d97e-123">Note</span><span class="sxs-lookup"><span data-stu-id="2d97e-123">Remarks</span></span>  
 <span data-ttu-id="2d97e-124">Con l'attributo `specifiedPickupDirectory` viene impostata la directory in cui nelle applicazioni vengono salvati i messaggi di posta elettronica da elaborare mediante il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="2d97e-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d97e-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="2d97e-125">Example</span></span>  
 <span data-ttu-id="2d97e-126">Nell'esempio seguente specifica c:\maildrop come la directory di prelievo della posta.</span><span class="sxs-lookup"><span data-stu-id="2d97e-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2d97e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d97e-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="2d97e-128">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="2d97e-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
