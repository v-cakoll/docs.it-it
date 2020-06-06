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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089123"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="3313e-102">Elemento \<servicePointManager> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="3313e-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="3313e-103">Configura le connessioni alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="3313e-103">Configures connections to network resources.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a><span data-ttu-id="3313e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3313e-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3313e-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3313e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3313e-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3313e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3313e-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="3313e-107">Attributes</span></span>  
  
|<span data-ttu-id="3313e-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="3313e-108">**Attribute**</span></span>|<span data-ttu-id="3313e-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3313e-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="3313e-110">Specifica se il sistema deve verificare che il nome del certificato corrisponda al nome host del server prima di utilizzare il certificato.</span><span class="sxs-lookup"><span data-stu-id="3313e-110">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="3313e-111">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="3313e-111">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="3313e-112">Specifica se il sistema deve controllare se il certificato è stato revocato prima di utilizzare il certificato.</span><span class="sxs-lookup"><span data-stu-id="3313e-112">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="3313e-113">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="3313e-113">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="3313e-114">Specifica la durata della memorizzazione nella cache delle risoluzioni di Domain Name Service (DNS) in combinazione con l'opzione del round robin DNS, in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="3313e-114">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="3313e-115">Il valore predefinito è 120.000 millisecondi (due minuti).</span><span class="sxs-lookup"><span data-stu-id="3313e-115">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="3313e-116">Specifica se le risoluzioni DNS dei nomi host con più indirizzi IP (Internet Protocol) restituiscono tutti gli indirizzi oppure solo la prima.</span><span class="sxs-lookup"><span data-stu-id="3313e-116">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="3313e-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="3313e-117">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="3313e-118">Specifica i criteri di crittografia applicati a una sessione SSL/TLS in un' <xref:System.Net.ServicePointManager> istanza di.</span><span class="sxs-lookup"><span data-stu-id="3313e-118">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="3313e-119">I valori possibili sono equivalenti ai valori per l' <xref:System.Net.Security.EncryptionPolicy> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3313e-119">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="3313e-120">L'utilizzo di <xref:System.Security.Authentication.CipherAlgorithmType.Null> è obbligatorio quando il criterio di crittografia è impostato su `NoEncryption` .</span><span class="sxs-lookup"><span data-stu-id="3313e-120">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="3313e-121">Il valore predefinito è `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="3313e-121">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="3313e-122">Specifica se i metodi POST devono prevedere la ricezione di una `100-continue` risposta dal server.</span><span class="sxs-lookup"><span data-stu-id="3313e-122">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="3313e-123">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="3313e-123">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="3313e-124">Specifica se le connessioni controllate da Gestione punti di servizio utilizzano l'algoritmo Nagle.</span><span class="sxs-lookup"><span data-stu-id="3313e-124">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="3313e-125">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="3313e-125">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3313e-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3313e-126">Child Elements</span></span>  
 <span data-ttu-id="3313e-127">No.</span><span class="sxs-lookup"><span data-stu-id="3313e-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3313e-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3313e-128">Parent Elements</span></span>  
  
|<span data-ttu-id="3313e-129">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="3313e-129">**Element**</span></span>|<span data-ttu-id="3313e-130">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3313e-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3313e-131">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="3313e-131">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="3313e-132">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="3313e-132">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3313e-133">Commenti</span><span class="sxs-lookup"><span data-stu-id="3313e-133">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3313e-134">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="3313e-134">Configuration Files</span></span>  
 <span data-ttu-id="3313e-135">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3313e-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3313e-136">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="3313e-136">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="3313e-137">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="3313e-137">Network Settings Schema</span></span>](index.md)
