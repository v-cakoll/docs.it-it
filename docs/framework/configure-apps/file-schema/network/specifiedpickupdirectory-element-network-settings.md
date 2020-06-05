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
ms.sourcegitcommit: 0a798a7e9680e2d0a5a81a3eaa203870ea782883
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "79154608"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="ade89-102">Elemento \<specifiedPickupDirectory> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ade89-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="ade89-103">Configura la directory locale per un server SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="ade89-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="ade89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ade89-104">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ade89-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ade89-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ade89-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ade89-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ade89-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="ade89-107">Attributes</span></span>  
  
|<span data-ttu-id="ade89-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ade89-108">Attribute</span></span>|<span data-ttu-id="ade89-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ade89-109">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="ade89-110">Directory in cui le applicazioni salvano i messaggi di posta elettronica per l'elaborazione successiva da parte del server SMTP.</span><span class="sxs-lookup"><span data-stu-id="ade89-110">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ade89-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ade89-111">Child Elements</span></span>  
 <span data-ttu-id="ade89-112">No.</span><span class="sxs-lookup"><span data-stu-id="ade89-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ade89-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ade89-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ade89-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ade89-114">Element</span></span>|<span data-ttu-id="ade89-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ade89-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ade89-116">\<smtp>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ade89-116">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="ade89-117">Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="ade89-117">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ade89-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="ade89-118">Remarks</span></span>  
 <span data-ttu-id="ade89-119">Con l'attributo `specifiedPickupDirectory` viene impostata la directory in cui nelle applicazioni vengono salvati i messaggi di posta elettronica da elaborare mediante il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="ade89-119">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ade89-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="ade89-120">Example</span></span>  
 <span data-ttu-id="ade89-121">Nell'esempio seguente viene specificato c:\maildrop come la directory di prelievo della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ade89-121">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ade89-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ade89-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="ade89-123">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ade89-123">Network Settings Schema</span></span>](index.md)
