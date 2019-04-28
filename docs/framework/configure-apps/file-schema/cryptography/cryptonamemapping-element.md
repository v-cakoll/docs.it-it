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
ms.openlocfilehash: bcf7894dba66736fcc1a30af9b5557549ef25e7d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674766"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="d92df-102">\<cryptoNameMapping > elemento</span><span class="sxs-lookup"><span data-stu-id="d92df-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="d92df-103">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="d92df-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="d92df-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d92df-104">\<configuration></span></span>  
<span data-ttu-id="d92df-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="d92df-105">\<mscorlib></span></span>  
<span data-ttu-id="d92df-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="d92df-106">\<cryptographySettings></span></span>  
<span data-ttu-id="d92df-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="d92df-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d92df-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d92df-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d92df-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d92df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d92df-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d92df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d92df-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d92df-111">Attributes</span></span>  
 <span data-ttu-id="d92df-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d92df-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d92df-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d92df-113">Child Elements</span></span>  
  
|<span data-ttu-id="d92df-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d92df-114">Element</span></span>|<span data-ttu-id="d92df-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d92df-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="d92df-116">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="d92df-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="d92df-117">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="d92df-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d92df-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d92df-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d92df-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d92df-119">Element</span></span>|<span data-ttu-id="d92df-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d92df-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d92df-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d92df-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="d92df-122">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="d92df-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="d92df-123">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="d92df-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="d92df-124">Contiene il \<cryptographySettings > elemento.</span><span class="sxs-lookup"><span data-stu-id="d92df-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d92df-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="d92df-125">Example</span></span>  
 <span data-ttu-id="d92df-126">Nell'esempio seguente viene illustrato come utilizzare il  **\<cryptoNameMapping >** elemento a cui fare riferimento a una classe di crittografia e configurare il runtime.</span><span class="sxs-lookup"><span data-stu-id="d92df-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="d92df-127">È quindi possibile passare la stringa "RSA" per il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo restituisca un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="d92df-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d92df-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d92df-128">See also</span></span>

- [<span data-ttu-id="d92df-129">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d92df-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d92df-130">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="d92df-130">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="d92df-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="d92df-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="d92df-132">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="d92df-132">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
