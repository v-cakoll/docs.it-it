---
title: Elemento <servicePointManager> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089123"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="f5a82-102">Elemento > di \<servicePointManager (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="f5a82-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="f5a82-103">Configura le connessioni alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="f5a82-103">Configures connections to network resources.</span></span>  

<span data-ttu-id="f5a82-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f5a82-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f5a82-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f5a82-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="f5a82-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Impostazioni**](settings-element-network-settings.md)\<</span><span class="sxs-lookup"><span data-stu-id="f5a82-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\</span></span>
<span data-ttu-id="f5a82-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**ServicePointManager** ></span><span class="sxs-lookup"><span data-stu-id="f5a82-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f5a82-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5a82-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5a82-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f5a82-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f5a82-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f5a82-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5a82-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="f5a82-111">Attributes</span></span>  
  
|<span data-ttu-id="f5a82-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="f5a82-112">**Attribute**</span></span>|<span data-ttu-id="f5a82-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f5a82-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="f5a82-114">Specifica se il sistema deve verificare che il nome del certificato corrisponda al nome host del server prima di utilizzare il certificato.</span><span class="sxs-lookup"><span data-stu-id="f5a82-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="f5a82-115">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="f5a82-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="f5a82-116">Specifica se il sistema deve controllare se il certificato è stato revocato prima di utilizzare il certificato.</span><span class="sxs-lookup"><span data-stu-id="f5a82-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="f5a82-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="f5a82-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="f5a82-118">Specifica la durata della memorizzazione nella cache delle risoluzioni di Domain Name Service (DNS) in combinazione con l'opzione del round robin DNS, in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="f5a82-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="f5a82-119">Il valore predefinito è 120.000 millisecondi (due minuti).</span><span class="sxs-lookup"><span data-stu-id="f5a82-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="f5a82-120">Specifica se le risoluzioni DNS dei nomi host con più indirizzi IP (Internet Protocol) restituiscono tutti gli indirizzi oppure solo la prima.</span><span class="sxs-lookup"><span data-stu-id="f5a82-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="f5a82-121">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="f5a82-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="f5a82-122">Specifica i criteri di crittografia applicati a una sessione SSL/TLS in un'istanza di <xref:System.Net.ServicePointManager>.</span><span class="sxs-lookup"><span data-stu-id="f5a82-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="f5a82-123">I valori possibili sono equivalenti ai valori per l'enumerazione <xref:System.Net.Security.EncryptionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="f5a82-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="f5a82-124">Quando i criteri di crittografia sono impostati su `NoEncryption`, è necessario utilizzare <xref:System.Security.Authentication.CipherAlgorithmType.Null>.</span><span class="sxs-lookup"><span data-stu-id="f5a82-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="f5a82-125">Il valore predefinito è `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="f5a82-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="f5a82-126">Specifica se i metodi POST devono ricevere una risposta `100-continue` dal server.</span><span class="sxs-lookup"><span data-stu-id="f5a82-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="f5a82-127">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="f5a82-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="f5a82-128">Specifica se le connessioni controllate da Gestione punti di servizio utilizzano l'algoritmo Nagle.</span><span class="sxs-lookup"><span data-stu-id="f5a82-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="f5a82-129">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="f5a82-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5a82-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f5a82-130">Child Elements</span></span>  
 <span data-ttu-id="f5a82-131">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="f5a82-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5a82-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f5a82-132">Parent Elements</span></span>  
  
|<span data-ttu-id="f5a82-133">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="f5a82-133">**Element**</span></span>|<span data-ttu-id="f5a82-134">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f5a82-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f5a82-135">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="f5a82-135">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="f5a82-136">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="f5a82-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5a82-137">Note</span><span class="sxs-lookup"><span data-stu-id="f5a82-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f5a82-138">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="f5a82-138">Configuration Files</span></span>  
 <span data-ttu-id="f5a82-139">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f5a82-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a82-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5a82-140">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="f5a82-141">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="f5a82-141">Network Settings Schema</span></span>](index.md)
