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
ms.openlocfilehash: 462db50a42e55c0c5a9570317ceeeb0ae69215a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927661"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="3b8b2-102">\<Elemento > cryptographySettings</span><span class="sxs-lookup"><span data-stu-id="3b8b2-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="3b8b2-103">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="3b8b2-103">Contains cryptography settings.</span></span>  
  
 <span data-ttu-id="3b8b2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3b8b2-104">\<configuration></span></span>  
<span data-ttu-id="3b8b2-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="3b8b2-105">\<mscorlib></span></span>  
<span data-ttu-id="3b8b2-106">\<> cryptographySettings</span><span class="sxs-lookup"><span data-stu-id="3b8b2-106">\<cryptographySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b8b2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b8b2-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b8b2-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3b8b2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3b8b2-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3b8b2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b8b2-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3b8b2-110">Attributes</span></span>  
 <span data-ttu-id="3b8b2-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3b8b2-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3b8b2-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3b8b2-112">Child Elements</span></span>  
  
|<span data-ttu-id="3b8b2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b8b2-113">Element</span></span>|<span data-ttu-id="3b8b2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b8b2-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b8b2-115">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="3b8b2-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="3b8b2-116">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="3b8b2-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="3b8b2-117">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="3b8b2-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="3b8b2-118">Contiene i mapping degli identificatori di oggetto (OID) ASN. 1 alle classi.</span><span class="sxs-lookup"><span data-stu-id="3b8b2-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b8b2-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3b8b2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3b8b2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b8b2-120">Element</span></span>|<span data-ttu-id="3b8b2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b8b2-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3b8b2-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3b8b2-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="3b8b2-123">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="3b8b2-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3b8b2-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="3b8b2-124">Example</span></span>  
 <span data-ttu-id="3b8b2-125">Nell'esempio seguente viene illustrato come utilizzare l'  **\<elemento > cryptographySettings** per contenere mapping dei nomi di crittografia e mapping OID.</span><span class="sxs-lookup"><span data-stu-id="3b8b2-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="3b8b2-126">Questo esempio configura il runtime in modo che <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> restituisca `MyHashClass` un oggetto e `MyCryptoClass` la classe venga mappata all'identificatore di oggetto 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="3b8b2-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b8b2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b8b2-127">See also</span></span>

- [<span data-ttu-id="3b8b2-128">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="3b8b2-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3b8b2-129">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="3b8b2-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3b8b2-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="3b8b2-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
