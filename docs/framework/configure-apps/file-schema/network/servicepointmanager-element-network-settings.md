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
ms.openlocfilehash: 407ed85de109a671030eccff8ddd92af91628014
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704986"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="48912-102">\<servicePointManager > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="48912-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="48912-103">Consente di configurare le connessioni alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="48912-103">Configures connections to network resources.</span></span>  
  
 <span data-ttu-id="48912-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="48912-104">\<configuration></span></span>  
<span data-ttu-id="48912-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="48912-105">\<system.net></span></span>  
<span data-ttu-id="48912-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="48912-106">\<settings></span></span>  
<span data-ttu-id="48912-107">\<servicePointManager></span><span class="sxs-lookup"><span data-stu-id="48912-107">\<servicePointManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48912-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48912-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48912-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="48912-109">Attributes and Elements</span></span>  
 <span data-ttu-id="48912-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="48912-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48912-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="48912-111">Attributes</span></span>  
  
|<span data-ttu-id="48912-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="48912-112">**Attribute**</span></span>|<span data-ttu-id="48912-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="48912-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="48912-114">Specifica se il sistema deve verificare che il nome del certificato corrisponda al nome host del server prima di usare il certificato.</span><span class="sxs-lookup"><span data-stu-id="48912-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="48912-115">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="48912-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="48912-116">Specifica se il sistema deve verificare se è stato revocato il certificato prima di usare il certificato.</span><span class="sxs-lookup"><span data-stu-id="48912-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="48912-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="48912-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="48912-118">Specifica la durata del servizio DNS (Domain Name) vengono memorizzati nella cache le soluzioni in combinazione con l'opzione DNS Round Robin, in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="48912-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="48912-119">Il valore predefinito è 120.000 millisecondi (due minuti).</span><span class="sxs-lookup"><span data-stu-id="48912-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="48912-120">Specifica se le risoluzioni DNS dell'host di nomi con più indirizzi IP (Internet Protocol) restituiti tutti gli indirizzi, o solo il primo.</span><span class="sxs-lookup"><span data-stu-id="48912-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="48912-121">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="48912-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="48912-122">Specifica i criteri di crittografia applicati a una sessione SSL/TLS in un <xref:System.Net.ServicePointManager> istanza.</span><span class="sxs-lookup"><span data-stu-id="48912-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="48912-123">I possibili valori sono equivalenti ai valori per il <xref:System.Net.Security.EncryptionPolicy> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="48912-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="48912-124">L'uso di <xref:System.Security.Authentication.CipherAlgorithmType.Null> è obbligatorio quando il criterio di crittografia è impostato su `NoEncryption`.</span><span class="sxs-lookup"><span data-stu-id="48912-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="48912-125">Il valore predefinito è `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="48912-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="48912-126">Specifica se i metodi POST devono prevedere di ricevere un `100-continue` risposta dal server.</span><span class="sxs-lookup"><span data-stu-id="48912-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="48912-127">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="48912-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="48912-128">Specifica se le connessioni controllate dal punto di Gestione servizi usano l'algoritmo Nagle.</span><span class="sxs-lookup"><span data-stu-id="48912-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="48912-129">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="48912-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48912-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="48912-130">Child Elements</span></span>  
 <span data-ttu-id="48912-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="48912-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48912-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="48912-132">Parent Elements</span></span>  
  
|<span data-ttu-id="48912-133">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="48912-133">**Element**</span></span>|<span data-ttu-id="48912-134">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="48912-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="48912-135">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="48912-135">Settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="48912-136">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="48912-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48912-137">Note</span><span class="sxs-lookup"><span data-stu-id="48912-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="48912-138">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="48912-138">Configuration Files</span></span>  
 <span data-ttu-id="48912-139">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="48912-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48912-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48912-140">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="48912-141">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="48912-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
