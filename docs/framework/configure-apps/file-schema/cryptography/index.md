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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087999"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="ab810-102">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="ab810-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="ab810-103">Lo schema delle impostazioni di crittografia contiene gli elementi che specificano come eseguire il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="ab810-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)

|<span data-ttu-id="ab810-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="ab810-104">Element</span></span>|<span data-ttu-id="ab810-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab810-105">Description</span></span>|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](cryptoclasses-element.md)|<span data-ttu-id="ab810-106">Contiene un elenco di classi di crittografia che dispongono di un mapping a un nome descrittivo nell' **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="ab810-106">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptoClass**>](cryptoclass-element.md)|<span data-ttu-id="ab810-107">Contiene una classe di crittografia con un mapping a un nome descrittivo nell' **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="ab810-107">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptographySettings**>](cryptographysettings-element.md)|<span data-ttu-id="ab810-108">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="ab810-108">Contains cryptography settings.</span></span>|  
|[**\<cryptoNameMapping**>](cryptonamemapping-element.md)|<span data-ttu-id="ab810-109">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="ab810-109">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="ab810-110">**\<mscorlib>** elemento per le impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="ab810-110">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="ab810-111">Contiene l' **\<cryptographySettings>** elemento.</span><span class="sxs-lookup"><span data-stu-id="ab810-111">Contains the **\<cryptographySettings>** element.</span></span>|  
|[**\<nameEntry>**](nameentry-element.md)|<span data-ttu-id="ab810-112">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="ab810-112">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[**\<oidEntry>**](oidentry-element.md)|<span data-ttu-id="ab810-113">Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="ab810-113">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[**\<oidMap>**](oidmap-element.md)|<span data-ttu-id="ab810-114">Contiene i mapping di OID ASN.1 e classi.</span><span class="sxs-lookup"><span data-stu-id="ab810-114">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab810-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ab810-115">See also</span></span>

- [<span data-ttu-id="ab810-116">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ab810-116">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ab810-117">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="ab810-117">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
