---
title: <cryptoNameMapping> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: d31c5cd52ffe0e2a6eb5784735e76436d216444b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155219"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="e5c5a-102">\<Elemento> cryptoNameMapping</span><span class="sxs-lookup"><span data-stu-id="e5c5a-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="e5c5a-103">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="e5c5a-103">Contains mappings of classes to friendly names.</span></span>  

<span data-ttu-id="e5c5a-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5c5a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5c5a-105">&nbsp;&nbsp;[**\<>mscorlib**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e5c5a-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="e5c5a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>cryptographySettings (impostazioni di crittografia)**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5c5a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="e5c5a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>cryptNameMapping**</span><span class="sxs-lookup"><span data-stu-id="e5c5a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e5c5a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5c5a-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5c5a-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e5c5a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e5c5a-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e5c5a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5c5a-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="e5c5a-111">Attributes</span></span>  
 <span data-ttu-id="e5c5a-112">No.</span><span class="sxs-lookup"><span data-stu-id="e5c5a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5c5a-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e5c5a-113">Child Elements</span></span>  
  
|<span data-ttu-id="e5c5a-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5c5a-114">Element</span></span>|<span data-ttu-id="e5c5a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5c5a-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="e5c5a-116">Contiene un elenco di classi di crittografia che dispongono di un mapping a un nome descrittivo nell'elemento \*\* \<>nameEntry.\*\*</span><span class="sxs-lookup"><span data-stu-id="e5c5a-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="e5c5a-117">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="e5c5a-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5c5a-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e5c5a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e5c5a-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5c5a-119">Element</span></span>|<span data-ttu-id="e5c5a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5c5a-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e5c5a-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e5c5a-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="e5c5a-122">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="e5c5a-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="e5c5a-123">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="e5c5a-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="e5c5a-124">Contiene l'elemento \<cryptographySettings>.</span><span class="sxs-lookup"><span data-stu-id="e5c5a-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e5c5a-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5c5a-125">Example</span></span>  
 <span data-ttu-id="e5c5a-126">Nell'esempio seguente viene illustrato come utilizzare l'elemento \*\* \<>cryptoNameMapping\*\* per fare riferimento a una classe di crittografia e configurare il runtime.</span><span class="sxs-lookup"><span data-stu-id="e5c5a-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="e5c5a-127">È quindi possibile passare la stringa <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> "RSA" <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> al metodo `MyCryptoRSAClass` e utilizzare il metodo per restituire un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5c5a-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5c5a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5c5a-128">See also</span></span>

- [<span data-ttu-id="e5c5a-129">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e5c5a-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e5c5a-130">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="e5c5a-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e5c5a-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e5c5a-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="e5c5a-132">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="e5c5a-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
