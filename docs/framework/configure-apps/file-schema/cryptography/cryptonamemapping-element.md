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
ms.openlocfilehash: 45d2da22a7c3486d4c7a638e92d1f3fce6f9883c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699711"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="eed36-102">Elemento > \<cryptoNameMapping</span><span class="sxs-lookup"><span data-stu-id="eed36-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="eed36-103">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="eed36-103">Contains mappings of classes to friendly names.</span></span>  
  
[<span data-ttu-id="eed36-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="eed36-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="eed36-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="eed36-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="eed36-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="eed36-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="eed36-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<cryptoNameMapping >**</span><span class="sxs-lookup"><span data-stu-id="eed36-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eed36-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eed36-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eed36-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eed36-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eed36-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eed36-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eed36-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="eed36-111">Attributes</span></span>  
 <span data-ttu-id="eed36-112">No.</span><span class="sxs-lookup"><span data-stu-id="eed36-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eed36-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eed36-113">Child Elements</span></span>  
  
|<span data-ttu-id="eed36-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="eed36-114">Element</span></span>|<span data-ttu-id="eed36-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eed36-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="eed36-116">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="eed36-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="eed36-117">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="eed36-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eed36-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eed36-118">Parent Elements</span></span>  
  
|<span data-ttu-id="eed36-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="eed36-119">Element</span></span>|<span data-ttu-id="eed36-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eed36-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eed36-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eed36-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="eed36-122">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="eed36-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="eed36-123">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="eed36-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="eed36-124">Contiene l'elemento > \<cryptographySettings.</span><span class="sxs-lookup"><span data-stu-id="eed36-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eed36-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="eed36-125">Example</span></span>  
 <span data-ttu-id="eed36-126">Nell'esempio seguente viene illustrato come utilizzare l'elemento **> \<cryptoNameMapping** per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="eed36-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="eed36-127">È quindi possibile passare la stringa "RSA" al metodo <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> e usare il metodo <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> per restituire un oggetto `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="eed36-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eed36-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eed36-128">See also</span></span>

- [<span data-ttu-id="eed36-129">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="eed36-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="eed36-130">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="eed36-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eed36-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="eed36-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="eed36-132">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="eed36-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
