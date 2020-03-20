---
title: <oidMap> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: a28eaf68fe1e6ab3f26592eee5ae2d0f2e7a3256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155167"
---
# <a name="oidmap-element"></a><span data-ttu-id="d599c-102">\<elemento> oidMap</span><span class="sxs-lookup"><span data-stu-id="d599c-102">\<oidMap> Element</span></span>
<span data-ttu-id="d599c-103">Contiene i mapping dell'identificatore di oggetto ASN.1 (OID) alle classi.</span><span class="sxs-lookup"><span data-stu-id="d599c-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

<span data-ttu-id="d599c-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d599c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d599c-105">&nbsp;&nbsp;[**\<>mscorlib**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d599c-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="d599c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>cryptographySettings (impostazioni di crittografia)**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="d599c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="d599c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>oidMap**</span><span class="sxs-lookup"><span data-stu-id="d599c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d599c-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d599c-108">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d599c-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d599c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d599c-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d599c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d599c-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="d599c-111">Attributes</span></span>  
 <span data-ttu-id="d599c-112">No.</span><span class="sxs-lookup"><span data-stu-id="d599c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d599c-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d599c-113">Child Elements</span></span>  
  
|<span data-ttu-id="d599c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d599c-114">Element</span></span>|<span data-ttu-id="d599c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d599c-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d599c-116">\<>oidEntry</span><span class="sxs-lookup"><span data-stu-id="d599c-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="d599c-117">Esegue il mapping di un OID ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="d599c-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d599c-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d599c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d599c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d599c-119">Element</span></span>|<span data-ttu-id="d599c-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d599c-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d599c-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d599c-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="d599c-122">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="d599c-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="d599c-123">Contiene `cryptographySettings` l'elemento.</span><span class="sxs-lookup"><span data-stu-id="d599c-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d599c-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="d599c-124">Example</span></span>  
 <span data-ttu-id="d599c-125">Nell'esempio seguente viene illustrato come utilizzare l'elemento \*\* \<oidMap>\*\* per contenere un mapping di un OID per l'algoritmo hash RIPEMD-160 a un'implementazione di tale algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d599c-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d599c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d599c-126">See also</span></span>

- [<span data-ttu-id="d599c-127">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d599c-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d599c-128">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="d599c-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d599c-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="d599c-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="d599c-130">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="d599c-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="d599c-131">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="d599c-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
