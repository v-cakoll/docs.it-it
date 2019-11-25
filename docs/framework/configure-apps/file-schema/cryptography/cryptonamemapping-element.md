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
ms.openlocfilehash: 4b3495d17e07ca611a384bf958ee06e928eb2506
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088010"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="4b2e7-102">\<elemento > cryptoNameMapping</span><span class="sxs-lookup"><span data-stu-id="4b2e7-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="4b2e7-103">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-103">Contains mappings of classes to friendly names.</span></span>  

<span data-ttu-id="4b2e7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4b2e7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4b2e7-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4b2e7-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="4b2e7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings**](cryptographysettings-element.md) ></span><span class="sxs-lookup"><span data-stu-id="4b2e7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="4b2e7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptoNameMapping** ></span><span class="sxs-lookup"><span data-stu-id="4b2e7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4b2e7-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b2e7-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b2e7-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4b2e7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4b2e7-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b2e7-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4b2e7-111">Attributes</span></span>  
 <span data-ttu-id="4b2e7-112">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4b2e7-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4b2e7-113">Child Elements</span></span>  
  
|<span data-ttu-id="4b2e7-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b2e7-114">Element</span></span>|<span data-ttu-id="4b2e7-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b2e7-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="4b2e7-116">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="4b2e7-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="4b2e7-117">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b2e7-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4b2e7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4b2e7-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b2e7-119">Element</span></span>|<span data-ttu-id="4b2e7-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b2e7-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4b2e7-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="4b2e7-122">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="4b2e7-123">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="4b2e7-124">Contiene l'elemento \<> cryptographySettings.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4b2e7-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b2e7-125">Example</span></span>  
 <span data-ttu-id="4b2e7-126">Nell'esempio seguente viene illustrato come utilizzare l'elemento **\<cryptoNameMapping >** per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="4b2e7-127">È quindi possibile passare la stringa "RSA" al metodo <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> e usare il metodo <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> per restituire un oggetto `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4b2e7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b2e7-128">See also</span></span>

- [<span data-ttu-id="4b2e7-129">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="4b2e7-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4b2e7-130">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="4b2e7-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4b2e7-131">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="4b2e7-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="4b2e7-132">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="4b2e7-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
