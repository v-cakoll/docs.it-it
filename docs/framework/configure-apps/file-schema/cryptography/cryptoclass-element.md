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
ms.openlocfilehash: 4872fbd6fa043902e8c69f158bee5d0c915ec83a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088652"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="025f8-102">\<elemento > cryptoClass</span><span class="sxs-lookup"><span data-stu-id="025f8-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="025f8-103">Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="025f8-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

<span data-ttu-id="025f8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="025f8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="025f8-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="025f8-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="025f8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings**](cryptographysettings-element.md) ></span><span class="sxs-lookup"><span data-stu-id="025f8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="025f8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**cryptoNameMapping**](cryptonamemapping-element.md) ></span><span class="sxs-lookup"><span data-stu-id="025f8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="025f8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClasses**](cryptoclasses-element.md) ></span><span class="sxs-lookup"><span data-stu-id="025f8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>\
<span data-ttu-id="025f8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptoClass >**</span><span class="sxs-lookup"><span data-stu-id="025f8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**</span></span>

## <a name="syntax"></a><span data-ttu-id="025f8-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="025f8-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="025f8-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="025f8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="025f8-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="025f8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="025f8-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="025f8-113">Attributes</span></span>  
  
|<span data-ttu-id="025f8-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="025f8-114">Attribute</span></span>|<span data-ttu-id="025f8-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="025f8-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="025f8-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="025f8-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="025f8-117">Contiene le informazioni per la classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="025f8-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="025f8-118">Utilizzare questo attributo per fornire un nome breve per la classe.</span><span class="sxs-lookup"><span data-stu-id="025f8-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="025f8-119">È necessario specificare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="025f8-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="025f8-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="025f8-120">Child Elements</span></span>  
 <span data-ttu-id="025f8-121">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="025f8-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="025f8-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="025f8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="025f8-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="025f8-123">Element</span></span>|<span data-ttu-id="025f8-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="025f8-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="025f8-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="025f8-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="025f8-126">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="025f8-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="025f8-127">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="025f8-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="025f8-128">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="025f8-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="025f8-129">Contiene l'elemento [\<cryptographySettings>](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="025f8-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="025f8-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="025f8-130">Example</span></span>  
 <span data-ttu-id="025f8-131">Nell'esempio seguente viene illustrato come utilizzare l'elemento **\<cryptoClass >** per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="025f8-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="025f8-132">È quindi possibile passare la stringa "RSA" al metodo <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> e usare il metodo <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> per restituire un oggetto `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="025f8-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="025f8-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="025f8-133">See also</span></span>

- [<span data-ttu-id="025f8-134">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="025f8-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="025f8-135">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="025f8-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="025f8-136">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="025f8-136">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="025f8-137">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="025f8-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
