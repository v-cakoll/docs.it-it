---
title: <cryptoClass> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: db3681ea141bb7e3905f6a470f5c74ce05f6ef4b
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699794"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="e49cb-102">Elemento > \<cryptoClass</span><span class="sxs-lookup"><span data-stu-id="e49cb-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="e49cb-103">Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="e49cb-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="e49cb-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e49cb-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e49cb-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e49cb-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="e49cb-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="e49cb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="e49cb-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="e49cb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="e49cb-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0cryptoClasses >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="e49cb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>  
<span data-ttu-id="e49cb-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1cryptoClass >**</span><span class="sxs-lookup"><span data-stu-id="e49cb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e49cb-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e49cb-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e49cb-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e49cb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e49cb-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e49cb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e49cb-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="e49cb-113">Attributes</span></span>  
  
|<span data-ttu-id="e49cb-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="e49cb-114">Attribute</span></span>|<span data-ttu-id="e49cb-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e49cb-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="e49cb-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e49cb-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e49cb-117">Contiene le informazioni per la classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="e49cb-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="e49cb-118">Utilizzare questo attributo per fornire un nome breve per la classe.</span><span class="sxs-lookup"><span data-stu-id="e49cb-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="e49cb-119">È necessario specificare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e49cb-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e49cb-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e49cb-120">Child Elements</span></span>  
 <span data-ttu-id="e49cb-121">No.</span><span class="sxs-lookup"><span data-stu-id="e49cb-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e49cb-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e49cb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e49cb-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e49cb-123">Element</span></span>|<span data-ttu-id="e49cb-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e49cb-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e49cb-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e49cb-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="e49cb-126">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="e49cb-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="e49cb-127">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="e49cb-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="e49cb-128">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="e49cb-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="e49cb-129">Contiene l'elemento [\<cryptographySettings>](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="e49cb-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e49cb-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="e49cb-130">Example</span></span>  
 <span data-ttu-id="e49cb-131">Nell'esempio seguente viene illustrato come utilizzare l'elemento **> \<cryptoClass** per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="e49cb-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="e49cb-132">È quindi possibile passare la stringa "RSA" al metodo <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> e usare il metodo <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> per restituire un oggetto `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="e49cb-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e49cb-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e49cb-133">See also</span></span>

- [<span data-ttu-id="e49cb-134">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e49cb-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e49cb-135">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="e49cb-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e49cb-136">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e49cb-136">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="e49cb-137">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="e49cb-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
