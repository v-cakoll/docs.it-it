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
ms.openlocfilehash: a7964d01905be4e3dd6e8149e5533e9a2cfd9a71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927624"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="7dc31-102">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="7dc31-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="7dc31-103">Lo schema delle impostazioni di crittografia contiene gli elementi che specificano come eseguire il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="7dc31-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="7dc31-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-104">**\<configuration>**</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="7dc31-105"> **\<mscorlib>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-105">**\<mscorlib>**</span></span>](mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="7dc31-106"> **\<cryptographySettings>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-106">**\<cryptographySettings>**</span></span>](cryptographysettings-element.md)  
  
 [<span data-ttu-id="7dc31-107"> **\<cryptoNameMapping>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-107">**\<cryptoNameMapping>**</span></span>](cryptonamemapping-element.md)  
  
 [<span data-ttu-id="7dc31-108"> **\<cryptoClasses>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-108">**\<cryptoClasses>**</span></span>](cryptoclasses-element.md)  
  
 [<span data-ttu-id="7dc31-109"> **\<cryptoClass>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-109">**\<cryptoClass>**</span></span>](cryptoclass-element.md)  
  
 [<span data-ttu-id="7dc31-110"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-110">**\<nameEntry>**</span></span>](nameentry-element.md)  
  
 [<span data-ttu-id="7dc31-111"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-111">**\<oidMap>**</span></span>](oidmap-element.md)  
  
 [<span data-ttu-id="7dc31-112"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-112">**\<oidEntry>**</span></span>](oidentry-element.md)  
  
|<span data-ttu-id="7dc31-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="7dc31-113">Element</span></span>|<span data-ttu-id="7dc31-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7dc31-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dc31-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="7dc31-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="7dc31-116">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="7dc31-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="7dc31-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="7dc31-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="7dc31-118">Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="7dc31-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="7dc31-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="7dc31-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="7dc31-120">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="7dc31-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="7dc31-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="7dc31-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="7dc31-122">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="7dc31-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="7dc31-123">**Elemento \<mscorlib>** per le impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="7dc31-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="7dc31-124">Contiene l'elemento **\<cryptographySettings>** .</span><span class="sxs-lookup"><span data-stu-id="7dc31-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="7dc31-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="7dc31-126">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="7dc31-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="7dc31-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="7dc31-128">Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="7dc31-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="7dc31-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="7dc31-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="7dc31-130">Contiene i mapping di OID ASN.1 e classi.</span><span class="sxs-lookup"><span data-stu-id="7dc31-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7dc31-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dc31-131">See also</span></span>

- [<span data-ttu-id="7dc31-132">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7dc31-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7dc31-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="7dc31-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
