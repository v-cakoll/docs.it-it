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
ms.openlocfilehash: a2aa56f8b2a92f906293adfae9d23ed8959336fb
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664287"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="e0ca1-102">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="e0ca1-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="e0ca1-103">Lo schema delle impostazioni di crittografia contiene gli elementi che specificano come eseguire il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="e0ca1-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="e0ca1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-104">**\<configuration>**</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="e0ca1-105"> **\<mscorlib>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-105">**\<mscorlib>**</span></span>](mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="e0ca1-106"> **\<cryptographySettings>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-106">**\<cryptographySettings>**</span></span>](cryptographysettings-element.md)  
  
 [<span data-ttu-id="e0ca1-107"> **\<cryptoNameMapping>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-107">**\<cryptoNameMapping>**</span></span>](cryptonamemapping-element.md)  
  
 [<span data-ttu-id="e0ca1-108"> **\<cryptoClasses>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-108">**\<cryptoClasses>**</span></span>](cryptoclasses-element.md)  
  
 [<span data-ttu-id="e0ca1-109"> **\<cryptoClass>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-109">**\<cryptoClass>**</span></span>](cryptoclass-element.md)  
  
 [<span data-ttu-id="e0ca1-110"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-110">**\<nameEntry>**</span></span>](nameentry-element.md)  
  
 [<span data-ttu-id="e0ca1-111"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-111">**\<oidMap>**</span></span>](oidmap-element.md)  
  
 [<span data-ttu-id="e0ca1-112"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-112">**\<oidEntry>**</span></span>](oidentry-element.md)  
  
|<span data-ttu-id="e0ca1-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e0ca1-113">Element</span></span>|<span data-ttu-id="e0ca1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0ca1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0ca1-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="e0ca1-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="e0ca1-116">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="e0ca1-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="e0ca1-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="e0ca1-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="e0ca1-118">Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="e0ca1-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="e0ca1-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="e0ca1-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="e0ca1-120">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="e0ca1-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="e0ca1-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="e0ca1-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="e0ca1-122">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="e0ca1-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="e0ca1-123">**Elemento \<mscorlib>** per le impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="e0ca1-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="e0ca1-124">Contiene l'elemento **\<cryptographySettings>** .</span><span class="sxs-lookup"><span data-stu-id="e0ca1-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="e0ca1-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="e0ca1-126">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="e0ca1-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="e0ca1-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="e0ca1-128">Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="e0ca1-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="e0ca1-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="e0ca1-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="e0ca1-130">Contiene i mapping di OID ASN.1 e classi.</span><span class="sxs-lookup"><span data-stu-id="e0ca1-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0ca1-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0ca1-131">See also</span></span>

- [<span data-ttu-id="e0ca1-132">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e0ca1-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e0ca1-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e0ca1-133">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
