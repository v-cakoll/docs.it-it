---
title: Schema delle impostazioni di crittografia
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: 2958ab01cb92872026437e31d2225d12d8606e97
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083379"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="220c2-102">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="220c2-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="220c2-103">Lo schema delle impostazioni di crittografia contiene gli elementi che specificano come eseguire il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="220c2-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="220c2-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="220c2-104">**\<configuration>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="220c2-105">**\<mscorlib>**</span><span class="sxs-lookup"><span data-stu-id="220c2-105">**\<mscorlib>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="220c2-106">**\<cryptographySettings>**</span><span class="sxs-lookup"><span data-stu-id="220c2-106">**\<cryptographySettings>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [<span data-ttu-id="220c2-107">**\<cryptoNameMapping>**</span><span class="sxs-lookup"><span data-stu-id="220c2-107">**\<cryptoNameMapping>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [<span data-ttu-id="220c2-108">**\<cryptoClasses>**</span><span class="sxs-lookup"><span data-stu-id="220c2-108">**\<cryptoClasses>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [<span data-ttu-id="220c2-109">**\<cryptoClass>**</span><span class="sxs-lookup"><span data-stu-id="220c2-109">**\<cryptoClass>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [<span data-ttu-id="220c2-110">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="220c2-110">**\<nameEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [<span data-ttu-id="220c2-111">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="220c2-111">**\<oidMap>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [<span data-ttu-id="220c2-112">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="220c2-112">**\<oidEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|<span data-ttu-id="220c2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="220c2-113">Element</span></span>|<span data-ttu-id="220c2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="220c2-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="220c2-115">**\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="220c2-115">**\<cryptoClasses**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|<span data-ttu-id="220c2-116">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="220c2-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="220c2-117">**\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="220c2-117">**\<cryptoClass**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="220c2-118">Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="220c2-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="220c2-119">**\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="220c2-119">**\<cryptographySettings**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|<span data-ttu-id="220c2-120">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="220c2-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="220c2-121">**\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="220c2-121">**\<cryptoNameMapping**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="220c2-122">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="220c2-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="220c2-123">**Elemento \<mscorlib>** per le impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="220c2-123">**\<mscorlib>** element for cryptography settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="220c2-124">Contiene l'elemento **\<cryptographySettings>**.</span><span class="sxs-lookup"><span data-stu-id="220c2-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="220c2-125">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="220c2-125">**\<nameEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|<span data-ttu-id="220c2-126">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="220c2-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="220c2-127">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="220c2-127">**\<oidEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="220c2-128">Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="220c2-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="220c2-129">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="220c2-129">**\<oidMap>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="220c2-130">Contiene i mapping di OID ASN.1 e classi.</span><span class="sxs-lookup"><span data-stu-id="220c2-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="220c2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="220c2-131">See also</span></span>
- [<span data-ttu-id="220c2-132">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="220c2-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="220c2-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="220c2-133">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
