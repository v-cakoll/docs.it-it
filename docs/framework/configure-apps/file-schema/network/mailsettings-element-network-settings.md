---
title: '&lt;mailSettings&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: e23b9e1fdf8a348d0d38575db8112b37c8dd9b69
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50048762"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="96c85-102">&lt;mailSettings&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="96c85-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="96c85-103">Consente di configurare le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="96c85-103">Configures mail sending options.</span></span>  

<span data-ttu-id="96c85-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="96c85-104">\<configuration></span></span>  
<span data-ttu-id="96c85-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="96c85-105">\<system.net></span></span>  
<span data-ttu-id="96c85-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="96c85-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c85-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96c85-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96c85-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="96c85-108">Attributes and Elements</span></span>  
 <span data-ttu-id="96c85-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="96c85-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96c85-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="96c85-110">Attributes</span></span>  
 <span data-ttu-id="96c85-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="96c85-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="96c85-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="96c85-112">Child Elements</span></span>  
  
|<span data-ttu-id="96c85-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="96c85-113">Attribute</span></span>|<span data-ttu-id="96c85-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96c85-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="96c85-115">\<SMTP > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="96c85-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="96c85-116">Configura le opzioni Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="96c85-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="96c85-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="96c85-117">Parent Elements</span></span>  
  
|<span data-ttu-id="96c85-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="96c85-118">**Element**</span></span>|<span data-ttu-id="96c85-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="96c85-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="96c85-120">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="96c85-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="96c85-121">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="96c85-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="96c85-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="96c85-122">Example</span></span>  
 <span data-ttu-id="96c85-123">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica usando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="96c85-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="96c85-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96c85-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="96c85-125">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="96c85-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
