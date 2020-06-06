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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087452"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="468f9-102">Elemento \<httpWebRequest> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="468f9-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="468f9-103">Personalizza i parametri della richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="468f9-103">Customizes Web request parameters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a><span data-ttu-id="468f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="468f9-104">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="468f9-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="468f9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="468f9-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="468f9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="468f9-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="468f9-107">Attributes</span></span>  
  
|<span data-ttu-id="468f9-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="468f9-108">**Attribute**</span></span>|<span data-ttu-id="468f9-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="468f9-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="468f9-110">Specifica la lunghezza massima di un'intestazione di risposta, espressa in kilobyte.</span><span class="sxs-lookup"><span data-stu-id="468f9-110">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="468f9-111">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="468f9-111">The default is 64.</span></span> <span data-ttu-id="468f9-112">Il valore-1 indica che non verrà imposto alcun limite di dimensioni per le intestazioni della risposta.</span><span class="sxs-lookup"><span data-stu-id="468f9-112">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="468f9-113">Specifica la lunghezza massima di una risposta di errore, espressa in kilobyte.</span><span class="sxs-lookup"><span data-stu-id="468f9-113">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="468f9-114">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="468f9-114">The default is 64.</span></span> <span data-ttu-id="468f9-115">Il valore-1 indica che non verrà imposto alcun limite di dimensioni per la risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="468f9-115">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="468f9-116">Specifica la lunghezza massima di un caricamento in risposta a un codice di errore non autorizzato, in byte.</span><span class="sxs-lookup"><span data-stu-id="468f9-116">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="468f9-117">Il valore predefinito è -1.</span><span class="sxs-lookup"><span data-stu-id="468f9-117">The default is -1.</span></span> <span data-ttu-id="468f9-118">Un valore di -1 indica che non verrà imposto alcun limite di dimensione all'upload.</span><span class="sxs-lookup"><span data-stu-id="468f9-118">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="468f9-119">Specifica se è abilitata l'analisi dell'intestazione unsafe.</span><span class="sxs-lookup"><span data-stu-id="468f9-119">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="468f9-120">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="468f9-120">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="468f9-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="468f9-121">Child Elements</span></span>  
 <span data-ttu-id="468f9-122">No.</span><span class="sxs-lookup"><span data-stu-id="468f9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="468f9-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="468f9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="468f9-124">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="468f9-124">**Element**</span></span>|<span data-ttu-id="468f9-125">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="468f9-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="468f9-126">impostazioni</span><span class="sxs-lookup"><span data-stu-id="468f9-126">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="468f9-127">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="468f9-127">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="468f9-128">Commenti</span><span class="sxs-lookup"><span data-stu-id="468f9-128">Remarks</span></span>  
 <span data-ttu-id="468f9-129">Per impostazione predefinita, il .NET Framework impone rigorosamente RFC 2616 per l'analisi dell'URI.</span><span class="sxs-lookup"><span data-stu-id="468f9-129">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="468f9-130">Alcune risposte al server possono includere caratteri di controllo in campi non consentiti, che determinano la <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> generazione di un oggetto da parte del metodo <xref:System.Net.WebException> .</span><span class="sxs-lookup"><span data-stu-id="468f9-130">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="468f9-131">Se **UseUnsafeHeaderParsing** è impostato su **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> in questo caso non verrà generata un'operazione. Tuttavia, l'applicazione sarà vulnerabile a diverse forme di attacchi di analisi URI.</span><span class="sxs-lookup"><span data-stu-id="468f9-131">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="468f9-132">La soluzione migliore consiste nel modificare il server in modo che la risposta non includa i caratteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="468f9-132">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="468f9-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="468f9-133">Configuration Files</span></span>  
 <span data-ttu-id="468f9-134">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="468f9-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="468f9-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="468f9-135">Example</span></span>  
 <span data-ttu-id="468f9-136">Nell'esempio seguente viene illustrato come specificare una lunghezza massima di intestazione maggiore di quella normale.</span><span class="sxs-lookup"><span data-stu-id="468f9-136">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="468f9-137">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="468f9-137">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="468f9-138">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="468f9-138">Network Settings Schema</span></span>](index.md)
