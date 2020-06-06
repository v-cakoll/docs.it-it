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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088652"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="f78f9-102">\<cryptoClass> Elemento</span><span class="sxs-lookup"><span data-stu-id="f78f9-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="f78f9-103">Contiene una classe di crittografia con un mapping a un nome descrittivo nell' [\<nameEntry>](nameentry-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f78f9-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**

## <a name="syntax"></a><span data-ttu-id="f78f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f78f9-104">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f78f9-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f78f9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f78f9-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f78f9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f78f9-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f78f9-107">Attributes</span></span>  
  
|<span data-ttu-id="f78f9-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="f78f9-108">Attribute</span></span>|<span data-ttu-id="f78f9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f78f9-109">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="f78f9-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f78f9-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="f78f9-111">Contiene le informazioni per la classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="f78f9-111">Contains the information for the cryptography class.</span></span> <span data-ttu-id="f78f9-112">Utilizzare questo attributo per fornire un nome breve per la classe.</span><span class="sxs-lookup"><span data-stu-id="f78f9-112">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="f78f9-113">È necessario specificare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="f78f9-113">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f78f9-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f78f9-114">Child Elements</span></span>  
 <span data-ttu-id="f78f9-115">No.</span><span class="sxs-lookup"><span data-stu-id="f78f9-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f78f9-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f78f9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f78f9-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="f78f9-117">Element</span></span>|<span data-ttu-id="f78f9-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f78f9-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f78f9-119">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f78f9-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="f78f9-120">Contiene un elenco di classi di crittografia che dispongono di un mapping a un nome descrittivo nell' [\<nameEntry>](nameentry-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f78f9-120">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f78f9-121">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="f78f9-121">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="f78f9-122">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="f78f9-122">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="f78f9-123">Contiene l' [\<cryptographySettings>](cryptographysettings-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f78f9-123">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f78f9-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="f78f9-124">Example</span></span>  
 <span data-ttu-id="f78f9-125">Nell'esempio seguente viene illustrato come utilizzare l' **\<cryptoClass>** elemento per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="f78f9-125">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="f78f9-126">È quindi possibile passare la stringa "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo per restituire un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="f78f9-126">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f78f9-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f78f9-127">See also</span></span>

- [<span data-ttu-id="f78f9-128">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f78f9-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f78f9-129">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="f78f9-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f78f9-130">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="f78f9-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="f78f9-131">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="f78f9-131">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
