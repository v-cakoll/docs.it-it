---
title: Elemento <mailSettings> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: 54fb68ab0bf8aa2665d70391350c626131ccb4bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674506"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="52584-102">\<mailSettings > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="52584-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="52584-103">Consente di configurare le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="52584-103">Configures mail sending options.</span></span>  

<span data-ttu-id="52584-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="52584-104">\<configuration></span></span>  
<span data-ttu-id="52584-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="52584-105">\<system.net></span></span>  
<span data-ttu-id="52584-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="52584-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52584-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52584-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52584-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="52584-108">Attributes and Elements</span></span>  
 <span data-ttu-id="52584-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="52584-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52584-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="52584-110">Attributes</span></span>  
 <span data-ttu-id="52584-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="52584-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="52584-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="52584-112">Child Elements</span></span>  
  
|<span data-ttu-id="52584-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="52584-113">Attribute</span></span>|<span data-ttu-id="52584-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52584-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="52584-115">\<SMTP > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="52584-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="52584-116">Configura le opzioni Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="52584-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52584-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="52584-117">Parent Elements</span></span>  
  
|<span data-ttu-id="52584-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="52584-118">**Element**</span></span>|<span data-ttu-id="52584-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="52584-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="52584-120">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="52584-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="52584-121">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52584-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="52584-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="52584-122">Example</span></span>  
 <span data-ttu-id="52584-123">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica usando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="52584-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="52584-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52584-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="52584-125">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="52584-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
