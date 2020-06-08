---
title: Elemento <mailSettings> (impostazioni di rete)
description: L' <mailSettings> elemento impostazioni di rete configura le opzioni di invio della posta elettronica nel .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: ce7b8564e4ee5ea73d42259612c077420d36645b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504563"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="0ea67-103">Elemento \<mailSettings> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="0ea67-103">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="0ea67-104">Configura le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0ea67-104">Configures mail sending options.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**

## <a name="syntax"></a><span data-ttu-id="0ea67-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ea67-105">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ea67-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0ea67-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0ea67-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0ea67-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ea67-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="0ea67-108">Attributes</span></span>  
 <span data-ttu-id="0ea67-109">No.</span><span class="sxs-lookup"><span data-stu-id="0ea67-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0ea67-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0ea67-110">Child Elements</span></span>  
  
|<span data-ttu-id="0ea67-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="0ea67-111">Attribute</span></span>|<span data-ttu-id="0ea67-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ea67-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="0ea67-113">\<smtp>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="0ea67-113">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="0ea67-114">Configura le opzioni del protocollo di trasporto di posta elettronica semplice.</span><span class="sxs-lookup"><span data-stu-id="0ea67-114">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ea67-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0ea67-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0ea67-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="0ea67-116">**Element**</span></span>|<span data-ttu-id="0ea67-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0ea67-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0ea67-118">\<system.Net>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="0ea67-118">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="0ea67-119">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ea67-119">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0ea67-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ea67-120">Example</span></span>  
 <span data-ttu-id="0ea67-121">Nell'esempio seguente vengono specificati i parametri SMTP appropriati per inviare messaggi di posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="0ea67-121">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0ea67-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ea67-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="0ea67-123">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="0ea67-123">Network Settings Schema</span></span>](index.md)
