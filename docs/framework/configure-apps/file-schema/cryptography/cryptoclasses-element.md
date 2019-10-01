---
title: <cryptoClasses> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 89f1d89ea397794e366b53205ac23b94d7892869
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699750"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="45ec1-102">Elemento > \<cryptoClasses</span><span class="sxs-lookup"><span data-stu-id="45ec1-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="45ec1-103">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="45ec1-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="45ec1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="45ec1-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="45ec1-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="45ec1-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="45ec1-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="45ec1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="45ec1-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="45ec1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="45ec1-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<cryptoClasses >**</span><span class="sxs-lookup"><span data-stu-id="45ec1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45ec1-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45ec1-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45ec1-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="45ec1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="45ec1-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="45ec1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45ec1-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="45ec1-112">Attributes</span></span>  
 <span data-ttu-id="45ec1-113">No.</span><span class="sxs-lookup"><span data-stu-id="45ec1-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="45ec1-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="45ec1-114">Child Elements</span></span>  
  
|<span data-ttu-id="45ec1-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="45ec1-115">Element</span></span>|<span data-ttu-id="45ec1-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45ec1-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45ec1-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="45ec1-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="45ec1-118">Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="45ec1-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="45ec1-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="45ec1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="45ec1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="45ec1-120">Element</span></span>|<span data-ttu-id="45ec1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45ec1-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="45ec1-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="45ec1-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="45ec1-123">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="45ec1-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="45ec1-124">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="45ec1-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="45ec1-125">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="45ec1-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="45ec1-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="45ec1-126">Example</span></span>  
 <span data-ttu-id="45ec1-127">Nell'esempio seguente viene illustrato come utilizzare l'elemento **> \<cryptoClass** per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="45ec1-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="45ec1-128">È quindi possibile passare la stringa "RSA" al metodo <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> e usare il metodo <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> per restituire un oggetto `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="45ec1-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45ec1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45ec1-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="45ec1-130">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="45ec1-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="45ec1-131">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="45ec1-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="45ec1-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="45ec1-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="45ec1-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="45ec1-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="45ec1-134">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="45ec1-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
