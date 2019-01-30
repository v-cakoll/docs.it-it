---
title: Elemento <httpWebRequest> (Impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: f19c39922105cebe179dd9f26fdc6beac8ddc0ef
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268275"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="cbac3-102">\<httpWebRequest > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="cbac3-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="cbac3-103">Consente di personalizzare i parametri della richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="cbac3-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="cbac3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cbac3-104">\<configuration></span></span>  
<span data-ttu-id="cbac3-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="cbac3-105">\<system.net></span></span>  
<span data-ttu-id="cbac3-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="cbac3-106">\<settings></span></span>  
<span data-ttu-id="cbac3-107">\<httpWebRequest></span><span class="sxs-lookup"><span data-stu-id="cbac3-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbac3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbac3-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cbac3-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cbac3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cbac3-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cbac3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cbac3-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="cbac3-111">Attributes</span></span>  
  
|<span data-ttu-id="cbac3-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="cbac3-112">**Attribute**</span></span>|<span data-ttu-id="cbac3-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cbac3-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="cbac3-114">Specifica la lunghezza massima di un'intestazione di risposta, espressa in kilobyte.</span><span class="sxs-lookup"><span data-stu-id="cbac3-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="cbac3-115">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="cbac3-115">The default is 64.</span></span> <span data-ttu-id="cbac3-116">Il valore -1 indica che non verrà imposto alcun limite di dimensione sulle intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="cbac3-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="cbac3-117">Specifica la lunghezza massima di una risposta di errore, in kilobyte.</span><span class="sxs-lookup"><span data-stu-id="cbac3-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="cbac3-118">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="cbac3-118">The default is 64.</span></span> <span data-ttu-id="cbac3-119">Il valore -1 indica che non verrà imposto alcun limite di dimensione nella risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="cbac3-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="cbac3-120">Specifica la lunghezza massima di un upload in risposta a un codice di errore non autorizzato, in byte.</span><span class="sxs-lookup"><span data-stu-id="cbac3-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="cbac3-121">Il valore predefinito è -1.</span><span class="sxs-lookup"><span data-stu-id="cbac3-121">The default is -1.</span></span> <span data-ttu-id="cbac3-122">Il valore -1 indica che non verrà imposto alcun limite di dimensione all'upload.</span><span class="sxs-lookup"><span data-stu-id="cbac3-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="cbac3-123">Specifica se l'analisi dell'intestazione di tipo unsafe è abilitato.</span><span class="sxs-lookup"><span data-stu-id="cbac3-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="cbac3-124">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="cbac3-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cbac3-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cbac3-125">Child Elements</span></span>  
 <span data-ttu-id="cbac3-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cbac3-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cbac3-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cbac3-127">Parent Elements</span></span>  
  
|<span data-ttu-id="cbac3-128">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cbac3-128">**Element**</span></span>|<span data-ttu-id="cbac3-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cbac3-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cbac3-130">settings</span><span class="sxs-lookup"><span data-stu-id="cbac3-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="cbac3-131">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="cbac3-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbac3-132">Note</span><span class="sxs-lookup"><span data-stu-id="cbac3-132">Remarks</span></span>  
 <span data-ttu-id="cbac3-133">Per impostazione predefinita, .NET Framework applica rigorosamente RFC 2616 per l'analisi dell'URI.</span><span class="sxs-lookup"><span data-stu-id="cbac3-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="cbac3-134">Alcune risposte server possono includere caratteri di controllo in campi non consentiti, che provoca il <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> metodo consente di generare un <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="cbac3-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="cbac3-135">Se **useUnsafeHeaderParsing** è impostata su **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> non viene generata in questo caso, tuttavia, l'applicazione sarà vulnerabile a diversi strumenti di analisi di attacchi di URI.</span><span class="sxs-lookup"><span data-stu-id="cbac3-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="cbac3-136">La soluzione migliore consiste nel modificare il server in modo che la risposta non include i caratteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="cbac3-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cbac3-137">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="cbac3-137">Configuration Files</span></span>  
 <span data-ttu-id="cbac3-138">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cbac3-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbac3-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbac3-139">Example</span></span>  
 <span data-ttu-id="cbac3-140">Nell'esempio seguente viene illustrato come specificare un maggiore della lunghezza intestazione massima nello stato normale.</span><span class="sxs-lookup"><span data-stu-id="cbac3-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cbac3-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbac3-141">See also</span></span>
- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="cbac3-142">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="cbac3-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
