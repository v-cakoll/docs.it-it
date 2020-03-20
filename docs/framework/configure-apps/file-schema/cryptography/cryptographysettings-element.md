---
title: <cryptographySettings> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: fe6de09213c6f980e8eb205a318aae50033b2a84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155232"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="e28fb-102">\<Elemento> cryptographySettings</span><span class="sxs-lookup"><span data-stu-id="e28fb-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="e28fb-103">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="e28fb-103">Contains cryptography settings.</span></span>  

<span data-ttu-id="e28fb-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e28fb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e28fb-105">&nbsp;&nbsp;[**\<>mscorlib**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e28fb-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="e28fb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>cryptographySettings (impostazioni di crittografia)**</span><span class="sxs-lookup"><span data-stu-id="e28fb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e28fb-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e28fb-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e28fb-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e28fb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e28fb-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e28fb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e28fb-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="e28fb-110">Attributes</span></span>  
 <span data-ttu-id="e28fb-111">No.</span><span class="sxs-lookup"><span data-stu-id="e28fb-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e28fb-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e28fb-112">Child Elements</span></span>  
  
|<span data-ttu-id="e28fb-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e28fb-113">Element</span></span>|<span data-ttu-id="e28fb-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e28fb-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e28fb-115">\<>cryptNameMapping</span><span class="sxs-lookup"><span data-stu-id="e28fb-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="e28fb-116">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="e28fb-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="e28fb-117">\<>oidMap</span><span class="sxs-lookup"><span data-stu-id="e28fb-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="e28fb-118">Contiene i mapping dell'identificatore di oggetto ASN.1 (OID) alle classi.</span><span class="sxs-lookup"><span data-stu-id="e28fb-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e28fb-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e28fb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e28fb-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e28fb-120">Element</span></span>|<span data-ttu-id="e28fb-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e28fb-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e28fb-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e28fb-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="e28fb-123">Contiene `cryptographySettings` l'elemento.</span><span class="sxs-lookup"><span data-stu-id="e28fb-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e28fb-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="e28fb-124">Example</span></span>  
 <span data-ttu-id="e28fb-125">Nell'esempio seguente viene illustrato come utilizzare l'elemento \*\* \<cryptographySettings>\*\* per contenere i mapping dei nomi di crittografia e i mapping OID.</span><span class="sxs-lookup"><span data-stu-id="e28fb-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="e28fb-126">In questo esempio viene <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> configurato `MyHashClass` il runtime `MyCryptoClass` in modo che restituisca un oggetto e che la classe esetra il mapping all'identificatore di oggetto 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="e28fb-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e28fb-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e28fb-127">See also</span></span>

- [<span data-ttu-id="e28fb-128">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e28fb-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e28fb-129">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="e28fb-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e28fb-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e28fb-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
