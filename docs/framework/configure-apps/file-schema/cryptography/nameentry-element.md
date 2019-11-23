---
title: <nameEntry> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: a339638587f8b544bbc1b0073553f6232ce09694
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699784"
---
# <a name="nameentry-element"></a><span data-ttu-id="eebf0-102">\<elemento > nameEntry</span><span class="sxs-lookup"><span data-stu-id="eebf0-102">\<nameEntry> Element</span></span>
<span data-ttu-id="eebf0-103">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="eebf0-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
[<span data-ttu-id="eebf0-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="eebf0-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="eebf0-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="eebf0-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="eebf0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="eebf0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="eebf0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping** >](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="eebf0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="eebf0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<nameEntry** ></span><span class="sxs-lookup"><span data-stu-id="eebf0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameEntry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eebf0-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eebf0-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eebf0-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eebf0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eebf0-111">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eebf0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eebf0-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="eebf0-112">Attributes</span></span>  
  
|<span data-ttu-id="eebf0-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="eebf0-113">Attribute</span></span>|<span data-ttu-id="eebf0-114">description</span><span class="sxs-lookup"><span data-stu-id="eebf0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eebf0-115">**name**</span><span class="sxs-lookup"><span data-stu-id="eebf0-115">**name**</span></span>|<span data-ttu-id="eebf0-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eebf0-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="eebf0-117">Specifica il nome descrittivo dell'algoritmo implementato dalla classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="eebf0-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="eebf0-118">**classe**</span><span class="sxs-lookup"><span data-stu-id="eebf0-118">**class**</span></span>|<span data-ttu-id="eebf0-119">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eebf0-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="eebf0-120">Specifica il valore per l'attributo **Name** nell'elemento [\<> CryptoClass](cryptoclass-element.md) .</span><span class="sxs-lookup"><span data-stu-id="eebf0-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eebf0-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eebf0-121">Child Elements</span></span>  
 <span data-ttu-id="eebf0-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="eebf0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eebf0-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eebf0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eebf0-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="eebf0-124">Element</span></span>|<span data-ttu-id="eebf0-125">description</span><span class="sxs-lookup"><span data-stu-id="eebf0-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eebf0-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eebf0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="eebf0-127">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="eebf0-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eebf0-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eebf0-128">Remarks</span></span>  
 <span data-ttu-id="eebf0-129">L'attributo **Name** può essere il nome di una delle classi astratte trovate nello spazio dei nomi <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="eebf0-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="eebf0-130">Quando si chiama il metodo **create** in una classe di crittografia astratta, il nome della classe astratta viene passato al metodo <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>.</span><span class="sxs-lookup"><span data-stu-id="eebf0-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="eebf0-131">**CreateFromName** restituisce un'istanza del tipo indicato dall'attributo **Class** .</span><span class="sxs-lookup"><span data-stu-id="eebf0-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="eebf0-132">Se l'attributo **Name** è un nome breve, ad esempio RSA, è possibile usare tale nome quando si chiama il metodo **CreateFromName** .</span><span class="sxs-lookup"><span data-stu-id="eebf0-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eebf0-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="eebf0-133">Example</span></span>  
 <span data-ttu-id="eebf0-134">Nell'esempio seguente viene illustrato come utilizzare l'elemento **\<nameEntry >** per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="eebf0-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="eebf0-135">È quindi possibile passare la stringa "RSA" al metodo <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> e usare il metodo <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> per restituire un oggetto `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="eebf0-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eebf0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eebf0-136">See also</span></span>

- [<span data-ttu-id="eebf0-137">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="eebf0-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="eebf0-138">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="eebf0-138">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eebf0-139">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="eebf0-139">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="eebf0-140">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="eebf0-140">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
