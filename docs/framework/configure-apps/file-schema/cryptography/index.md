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
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087999"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="2de5f-102">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="2de5f-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="2de5f-103">Lo schema delle impostazioni di crittografia contiene gli elementi che specificano come eseguire il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="2de5f-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
<span data-ttu-id="2de5f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2de5f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2de5f-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2de5f-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="2de5f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings**](cryptographysettings-element.md) ></span><span class="sxs-lookup"><span data-stu-id="2de5f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="2de5f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**cryptoNameMapping**](cryptonamemapping-element.md) ></span><span class="sxs-lookup"><span data-stu-id="2de5f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="2de5f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClasses**](cryptoclasses-element.md) ></span><span class="sxs-lookup"><span data-stu-id="2de5f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>\
<span data-ttu-id="2de5f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CryptoClass**](cryptoclass-element.md) ></span><span class="sxs-lookup"><span data-stu-id="2de5f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)</span></span>\
<span data-ttu-id="2de5f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<nameEntry**](nameentry-element.md) ></span><span class="sxs-lookup"><span data-stu-id="2de5f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)</span></span>\
<span data-ttu-id="2de5f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**oidMap**](oidmap-element.md) ></span><span class="sxs-lookup"><span data-stu-id="2de5f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="2de5f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidEntry** >](oidentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="2de5f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)</span></span>

|<span data-ttu-id="2de5f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2de5f-113">Element</span></span>|<span data-ttu-id="2de5f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2de5f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2de5f-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="2de5f-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="2de5f-116">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="2de5f-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="2de5f-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="2de5f-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="2de5f-118">Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="2de5f-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="2de5f-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="2de5f-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="2de5f-120">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="2de5f-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="2de5f-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="2de5f-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="2de5f-122">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="2de5f-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="2de5f-123">**Elemento \<mscorlib>** per le impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="2de5f-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="2de5f-124">Contiene l'elemento **\<cryptographySettings>** .</span><span class="sxs-lookup"><span data-stu-id="2de5f-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="2de5f-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="2de5f-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="2de5f-126">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="2de5f-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="2de5f-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="2de5f-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="2de5f-128">Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="2de5f-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="2de5f-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="2de5f-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="2de5f-130">Contiene i mapping di OID ASN.1 e classi.</span><span class="sxs-lookup"><span data-stu-id="2de5f-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2de5f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2de5f-131">See also</span></span>

- [<span data-ttu-id="2de5f-132">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2de5f-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2de5f-133">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="2de5f-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
