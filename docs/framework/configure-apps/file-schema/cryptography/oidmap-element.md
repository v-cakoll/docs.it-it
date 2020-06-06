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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155167"
---
# <a name="oidmap-element"></a><span data-ttu-id="e10ca-102">\<oidMap> Elemento</span><span class="sxs-lookup"><span data-stu-id="e10ca-102">\<oidMap> Element</span></span>
<span data-ttu-id="e10ca-103">Contiene i mapping degli identificatori di oggetto (OID) ASN. 1 alle classi.</span><span class="sxs-lookup"><span data-stu-id="e10ca-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**

## <a name="syntax"></a><span data-ttu-id="e10ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e10ca-104">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e10ca-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e10ca-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e10ca-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e10ca-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e10ca-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="e10ca-107">Attributes</span></span>  
 <span data-ttu-id="e10ca-108">No.</span><span class="sxs-lookup"><span data-stu-id="e10ca-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e10ca-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e10ca-109">Child Elements</span></span>  
  
|<span data-ttu-id="e10ca-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="e10ca-110">Element</span></span>|<span data-ttu-id="e10ca-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e10ca-111">Description</span></span>|  
|-------------|-----------------|  
|[\<oidEntry>](oidentry-element.md)|<span data-ttu-id="e10ca-112">Esegue il mapping di un OID ASN. 1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="e10ca-112">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e10ca-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e10ca-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e10ca-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="e10ca-114">Element</span></span>|<span data-ttu-id="e10ca-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e10ca-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e10ca-116">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e10ca-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="e10ca-117">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="e10ca-117">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="e10ca-118">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="e10ca-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e10ca-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="e10ca-119">Example</span></span>  
 <span data-ttu-id="e10ca-120">Nell'esempio seguente viene illustrato come utilizzare l' **\<oidMap>** elemento per contenere un mapping di un OID per l'algoritmo hash RIPEMD-160 a un'implementazione di tale algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="e10ca-120">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e10ca-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e10ca-121">See also</span></span>

- [<span data-ttu-id="e10ca-122">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e10ca-122">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e10ca-123">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="e10ca-123">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e10ca-124">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="e10ca-124">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="e10ca-125">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="e10ca-125">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="e10ca-126">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="e10ca-126">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
