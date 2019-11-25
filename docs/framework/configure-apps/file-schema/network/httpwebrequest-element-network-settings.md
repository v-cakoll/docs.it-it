---
title: Elemento <httpWebRequest> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: d33dadc14510feb00e05ca557b507b0cf8fa0dd0
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087452"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="14f88-102">Elemento \<httpWebRequest > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="14f88-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="14f88-103">Personalizza i parametri della richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="14f88-103">Customizes Web request parameters.</span></span>  

<span data-ttu-id="14f88-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="14f88-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="14f88-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="14f88-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="14f88-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Impostazioni**](settings-element-network-settings.md)\<</span><span class="sxs-lookup"><span data-stu-id="14f88-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\</span></span>
<span data-ttu-id="14f88-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**HttpWebRequest** ></span><span class="sxs-lookup"><span data-stu-id="14f88-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**</span></span>

## <a name="syntax"></a><span data-ttu-id="14f88-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14f88-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14f88-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="14f88-109">Attributes and Elements</span></span>  
 <span data-ttu-id="14f88-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="14f88-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14f88-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="14f88-111">Attributes</span></span>  
  
|<span data-ttu-id="14f88-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="14f88-112">**Attribute**</span></span>|<span data-ttu-id="14f88-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="14f88-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="14f88-114">Specifica la lunghezza massima di un'intestazione di risposta, espressa in kilobyte.</span><span class="sxs-lookup"><span data-stu-id="14f88-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="14f88-115">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="14f88-115">The default is 64.</span></span> <span data-ttu-id="14f88-116">Il valore-1 indica che non verrà imposto alcun limite di dimensioni per le intestazioni della risposta.</span><span class="sxs-lookup"><span data-stu-id="14f88-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="14f88-117">Specifica la lunghezza massima di una risposta di errore, espressa in kilobyte.</span><span class="sxs-lookup"><span data-stu-id="14f88-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="14f88-118">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="14f88-118">The default is 64.</span></span> <span data-ttu-id="14f88-119">Il valore-1 indica che non verrà imposto alcun limite di dimensioni per la risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="14f88-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="14f88-120">Specifica la lunghezza massima di un caricamento in risposta a un codice di errore non autorizzato, in byte.</span><span class="sxs-lookup"><span data-stu-id="14f88-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="14f88-121">Il valore predefinito è -1.</span><span class="sxs-lookup"><span data-stu-id="14f88-121">The default is -1.</span></span> <span data-ttu-id="14f88-122">Il valore-1 indica che non verrà imposto alcun limite di dimensioni per il caricamento.</span><span class="sxs-lookup"><span data-stu-id="14f88-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="14f88-123">Specifica se è abilitata l'analisi dell'intestazione unsafe.</span><span class="sxs-lookup"><span data-stu-id="14f88-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="14f88-124">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="14f88-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14f88-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="14f88-125">Child Elements</span></span>  
 <span data-ttu-id="14f88-126">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="14f88-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14f88-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="14f88-127">Parent Elements</span></span>  
  
|<span data-ttu-id="14f88-128">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="14f88-128">**Element**</span></span>|<span data-ttu-id="14f88-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="14f88-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="14f88-130">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="14f88-130">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="14f88-131">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="14f88-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14f88-132">Note</span><span class="sxs-lookup"><span data-stu-id="14f88-132">Remarks</span></span>  
 <span data-ttu-id="14f88-133">Per impostazione predefinita, il .NET Framework impone rigorosamente RFC 2616 per l'analisi dell'URI.</span><span class="sxs-lookup"><span data-stu-id="14f88-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="14f88-134">Alcune risposte al server possono includere caratteri di controllo in campi non consentiti, che determinano la generazione di un <xref:System.Net.WebException>da parte del metodo <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="14f88-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="14f88-135">Se **UseUnsafeHeaderParsing** è impostato su **true**, in questo caso <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> non genererà. Tuttavia, l'applicazione sarà vulnerabile a diverse forme di attacchi di analisi URI.</span><span class="sxs-lookup"><span data-stu-id="14f88-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="14f88-136">La soluzione migliore consiste nel modificare il server in modo che la risposta non includa i caratteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="14f88-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="14f88-137">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="14f88-137">Configuration Files</span></span>  
 <span data-ttu-id="14f88-138">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="14f88-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14f88-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="14f88-139">Example</span></span>  
 <span data-ttu-id="14f88-140">Nell'esempio seguente viene illustrato come specificare una lunghezza massima di intestazione maggiore di quella normale.</span><span class="sxs-lookup"><span data-stu-id="14f88-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14f88-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14f88-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="14f88-142">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="14f88-142">Network Settings Schema</span></span>](index.md)
