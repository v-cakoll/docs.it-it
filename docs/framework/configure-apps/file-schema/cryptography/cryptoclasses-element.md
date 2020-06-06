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
ms.openlocfilehash: c93fadf51297d59ab499e25de283700364903049
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155246"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="77544-102">\<cryptoClasses> Elemento</span><span class="sxs-lookup"><span data-stu-id="77544-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="77544-103">Contiene un elenco di classi di crittografia che dispongono di un mapping a un nome descrittivo nell' [\<nameEntry>](nameentry-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="77544-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**  
  
## <a name="syntax"></a><span data-ttu-id="77544-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77544-104">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77544-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="77544-105">Attributes and Elements</span></span>  
 <span data-ttu-id="77544-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="77544-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77544-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="77544-107">Attributes</span></span>  
 <span data-ttu-id="77544-108">No.</span><span class="sxs-lookup"><span data-stu-id="77544-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="77544-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="77544-109">Child Elements</span></span>  
  
|<span data-ttu-id="77544-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="77544-110">Element</span></span>|<span data-ttu-id="77544-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77544-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoClass>](cryptoclass-element.md)|<span data-ttu-id="77544-112">Contiene una classe di crittografia con un mapping a un nome descrittivo nell' **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="77544-112">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77544-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="77544-113">Parent Elements</span></span>  
  
|<span data-ttu-id="77544-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="77544-114">Element</span></span>|<span data-ttu-id="77544-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77544-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="77544-116">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77544-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="77544-117">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="77544-117">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="77544-118">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="77544-118">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="77544-119">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="77544-119">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="77544-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="77544-120">Example</span></span>  
 <span data-ttu-id="77544-121">Nell'esempio seguente viene illustrato come utilizzare l' **\<cryptoClass>** elemento per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="77544-121">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="77544-122">È quindi possibile passare la stringa "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo per restituire un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="77544-122">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="77544-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="77544-123">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="77544-124">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="77544-124">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="77544-125">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="77544-125">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="77544-126">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="77544-126">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="77544-127">System. Security. Cryptography. CryptoConfig. CreateFromName</span><span class="sxs-lookup"><span data-stu-id="77544-127">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="77544-128">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="77544-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
