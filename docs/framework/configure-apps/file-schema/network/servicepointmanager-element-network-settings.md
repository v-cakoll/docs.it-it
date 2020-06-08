---
title: Elemento <servicePointManager> (impostazioni di rete)
description: L' <servicePointManager> elemento impostazioni di rete configura le connessioni alle opzioni di risorse di rete nel .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: eb27716ec7c2936f32a7e4d4c983d1e175c4d044
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504524"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="26a32-103">Elemento \<servicePointManager> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="26a32-103">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="26a32-104">Configura le connessioni alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="26a32-104">Configures connections to network resources.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a><span data-ttu-id="26a32-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26a32-105">Syntax</span></span>  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26a32-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="26a32-106">Attributes and Elements</span></span>  
 <span data-ttu-id="26a32-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="26a32-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26a32-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="26a32-108">Attributes</span></span>  
  
|<span data-ttu-id="26a32-109">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="26a32-109">**Attribute**</span></span>|<span data-ttu-id="26a32-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="26a32-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="26a32-111">Specifica se il sistema deve verificare che il nome del certificato corrisponda al nome host del server prima di utilizzare il certificato.</span><span class="sxs-lookup"><span data-stu-id="26a32-111">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="26a32-112">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="26a32-112">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="26a32-113">Specifica se il sistema deve controllare se il certificato è stato revocato prima di utilizzare il certificato.</span><span class="sxs-lookup"><span data-stu-id="26a32-113">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="26a32-114">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="26a32-114">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="26a32-115">Specifica la durata della memorizzazione nella cache delle risoluzioni di Domain Name Service (DNS) in combinazione con l'opzione del round robin DNS, in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="26a32-115">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="26a32-116">Il valore predefinito è 120.000 millisecondi (due minuti).</span><span class="sxs-lookup"><span data-stu-id="26a32-116">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="26a32-117">Specifica se le risoluzioni DNS dei nomi host con più indirizzi IP (Internet Protocol) restituiscono tutti gli indirizzi oppure solo la prima.</span><span class="sxs-lookup"><span data-stu-id="26a32-117">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="26a32-118">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="26a32-118">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="26a32-119">Specifica i criteri di crittografia applicati a una sessione SSL/TLS in un' <xref:System.Net.ServicePointManager> istanza di.</span><span class="sxs-lookup"><span data-stu-id="26a32-119">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="26a32-120">I valori possibili sono equivalenti ai valori per l' <xref:System.Net.Security.EncryptionPolicy> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="26a32-120">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="26a32-121">L'utilizzo di <xref:System.Security.Authentication.CipherAlgorithmType.Null> è obbligatorio quando il criterio di crittografia è impostato su `NoEncryption` .</span><span class="sxs-lookup"><span data-stu-id="26a32-121">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="26a32-122">Il valore predefinito è `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="26a32-122">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="26a32-123">Specifica se i metodi POST devono prevedere la ricezione di una `100-continue` risposta dal server.</span><span class="sxs-lookup"><span data-stu-id="26a32-123">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="26a32-124">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="26a32-124">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="26a32-125">Specifica se le connessioni controllate da Gestione punti di servizio utilizzano l'algoritmo Nagle.</span><span class="sxs-lookup"><span data-stu-id="26a32-125">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="26a32-126">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="26a32-126">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26a32-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="26a32-127">Child Elements</span></span>  
 <span data-ttu-id="26a32-128">No.</span><span class="sxs-lookup"><span data-stu-id="26a32-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26a32-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="26a32-129">Parent Elements</span></span>  
  
|<span data-ttu-id="26a32-130">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="26a32-130">**Element**</span></span>|<span data-ttu-id="26a32-131">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="26a32-131">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="26a32-132">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="26a32-132">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="26a32-133">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="26a32-133">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26a32-134">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="26a32-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="26a32-135">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="26a32-135">Configuration Files</span></span>  
 <span data-ttu-id="26a32-136">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="26a32-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a32-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26a32-137">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="26a32-138">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="26a32-138">Network Settings Schema</span></span>](index.md)
