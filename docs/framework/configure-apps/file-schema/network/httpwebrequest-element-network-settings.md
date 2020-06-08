---
title: Elemento <httpWebRequest> (impostazioni di rete)
description: L' <httpWebRequest> elemento impostazioni di rete Personalizza i parametri delle richieste Web nel .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 59ab425dcef8ac5283035910a9d78a89a16be8b1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504589"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="e6e96-103">Elemento \<httpWebRequest> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="e6e96-103">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="e6e96-104">Personalizza i parametri della richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="e6e96-104">Customizes Web request parameters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a><span data-ttu-id="e6e96-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6e96-105">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6e96-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e6e96-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e6e96-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e6e96-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6e96-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="e6e96-108">Attributes</span></span>  
  
|<span data-ttu-id="e6e96-109">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="e6e96-109">**Attribute**</span></span>|<span data-ttu-id="e6e96-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e6e96-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="e6e96-111">Specifica la lunghezza massima di un'intestazione di risposta, espressa in kilobyte.</span><span class="sxs-lookup"><span data-stu-id="e6e96-111">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="e6e96-112">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="e6e96-112">The default is 64.</span></span> <span data-ttu-id="e6e96-113">Il valore-1 indica che non verrà imposto alcun limite di dimensioni per le intestazioni della risposta.</span><span class="sxs-lookup"><span data-stu-id="e6e96-113">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="e6e96-114">Specifica la lunghezza massima di una risposta di errore, espressa in kilobyte.</span><span class="sxs-lookup"><span data-stu-id="e6e96-114">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="e6e96-115">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="e6e96-115">The default is 64.</span></span> <span data-ttu-id="e6e96-116">Il valore-1 indica che non verrà imposto alcun limite di dimensioni per la risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="e6e96-116">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="e6e96-117">Specifica la lunghezza massima di un caricamento in risposta a un codice di errore non autorizzato, in byte.</span><span class="sxs-lookup"><span data-stu-id="e6e96-117">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="e6e96-118">Il valore predefinito è -1.</span><span class="sxs-lookup"><span data-stu-id="e6e96-118">The default is -1.</span></span> <span data-ttu-id="e6e96-119">Un valore di -1 indica che non verrà imposto alcun limite di dimensione all'upload.</span><span class="sxs-lookup"><span data-stu-id="e6e96-119">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="e6e96-120">Specifica se è abilitata l'analisi dell'intestazione unsafe.</span><span class="sxs-lookup"><span data-stu-id="e6e96-120">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="e6e96-121">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="e6e96-121">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6e96-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e6e96-122">Child Elements</span></span>  
 <span data-ttu-id="e6e96-123">No.</span><span class="sxs-lookup"><span data-stu-id="e6e96-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6e96-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e6e96-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e6e96-125">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e6e96-125">**Element**</span></span>|<span data-ttu-id="e6e96-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e6e96-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e6e96-127">impostazioni</span><span class="sxs-lookup"><span data-stu-id="e6e96-127">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="e6e96-128">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="e6e96-128">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6e96-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e6e96-129">Remarks</span></span>  
 <span data-ttu-id="e6e96-130">Per impostazione predefinita, il .NET Framework impone rigorosamente RFC 2616 per l'analisi dell'URI.</span><span class="sxs-lookup"><span data-stu-id="e6e96-130">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="e6e96-131">Alcune risposte al server possono includere caratteri di controllo in campi non consentiti, che determinano la <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> generazione di un oggetto da parte del metodo <xref:System.Net.WebException> .</span><span class="sxs-lookup"><span data-stu-id="e6e96-131">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="e6e96-132">Se **UseUnsafeHeaderParsing** è impostato su **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> in questo caso non verrà generata un'operazione. Tuttavia, l'applicazione sarà vulnerabile a diverse forme di attacchi di analisi URI.</span><span class="sxs-lookup"><span data-stu-id="e6e96-132">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="e6e96-133">La soluzione migliore consiste nel modificare il server in modo che la risposta non includa i caratteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="e6e96-133">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e6e96-134">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e6e96-134">Configuration Files</span></span>  
 <span data-ttu-id="e6e96-135">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e6e96-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6e96-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6e96-136">Example</span></span>  
 <span data-ttu-id="e6e96-137">Nell'esempio seguente viene illustrato come specificare una lunghezza massima di intestazione maggiore di quella normale.</span><span class="sxs-lookup"><span data-stu-id="e6e96-137">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6e96-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6e96-138">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="e6e96-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="e6e96-139">Network Settings Schema</span></span>](index.md)
