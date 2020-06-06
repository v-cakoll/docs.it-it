---
title: <oidEntry> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: 4564cf59e3b6cfbdcd9dca06cd0f966d524834de
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088543"
---
# <a name="oidentry-element"></a><span data-ttu-id="344a5-102">\<oidEntry> Elemento</span><span class="sxs-lookup"><span data-stu-id="344a5-102">\<oidEntry> Element</span></span>
<span data-ttu-id="344a5-103">Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="344a5-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**

## <a name="syntax"></a><span data-ttu-id="344a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="344a5-104">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="344a5-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="344a5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="344a5-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="344a5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="344a5-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="344a5-107">Attributes</span></span>  
  
|<span data-ttu-id="344a5-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="344a5-108">Attribute</span></span>|<span data-ttu-id="344a5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="344a5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="344a5-110">**OID**</span><span class="sxs-lookup"><span data-stu-id="344a5-110">**OID**</span></span>|<span data-ttu-id="344a5-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="344a5-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="344a5-112">Specifica l'OID ASN. 1 corrispondente all'algoritmo implementato dalla classe.</span><span class="sxs-lookup"><span data-stu-id="344a5-112">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="344a5-113">**nome**</span><span class="sxs-lookup"><span data-stu-id="344a5-113">**name**</span></span>|<span data-ttu-id="344a5-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="344a5-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="344a5-115">Specifica il valore per l'attributo **Name** nel [\<nameEntry>](nameentry-element.md) tag.</span><span class="sxs-lookup"><span data-stu-id="344a5-115">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="344a5-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="344a5-116">Child Elements</span></span>  
 <span data-ttu-id="344a5-117">No.</span><span class="sxs-lookup"><span data-stu-id="344a5-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="344a5-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="344a5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="344a5-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="344a5-119">Element</span></span>|<span data-ttu-id="344a5-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="344a5-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="344a5-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="344a5-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="344a5-122">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="344a5-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="344a5-123">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="344a5-123">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="344a5-124">Contiene i mapping degli identificatori di oggetto (OID) ASN. 1 alle classi.</span><span class="sxs-lookup"><span data-stu-id="344a5-124">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="344a5-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="344a5-125">Remarks</span></span>  
 <span data-ttu-id="344a5-126">Gli identificatori di oggetto ASN. 1 identificano gli algoritmi in alcuni formati crittografici.</span><span class="sxs-lookup"><span data-stu-id="344a5-126">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="344a5-127">Eseguire il mapping degli identificatori di oggetto ai nomi descrittivi per gli algoritmi che si desidera identificare.</span><span class="sxs-lookup"><span data-stu-id="344a5-127">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="344a5-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="344a5-128">Example</span></span>  
 <span data-ttu-id="344a5-129">Nell'esempio seguente viene illustrato come utilizzare l' **\<oidEntry>** elemento per eseguire il mapping di un identificatore di oggetto per l'algoritmo hash RIPEMD-160 a un'implementazione di tale algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="344a5-129">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="344a5-130">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="344a5-130">See also</span></span>

- [<span data-ttu-id="344a5-131">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="344a5-131">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="344a5-132">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="344a5-132">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="344a5-133">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="344a5-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="344a5-134">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="344a5-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="344a5-135">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="344a5-135">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
