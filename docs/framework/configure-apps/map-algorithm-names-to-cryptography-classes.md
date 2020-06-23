---
title: Mapping di nomi di algoritmi a classi di crittografia
description: Eseguire il mapping dei nomi degli algoritmi alle classi di crittografia in .NET. Uno sviluppatore dispone di quattro opzioni per la creazione di un oggetto di crittografia.
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 5a1d7acdd34182dd82f4dce66d136c4ef4de6e95
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105351"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="59494-104">Mapping di nomi di algoritmi a classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="59494-104">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="59494-105">Esistono quattro modi per creare un oggetto di crittografia usando il Windows SDK:</span><span class="sxs-lookup"><span data-stu-id="59494-105">There are four ways a developer can create a cryptography object using the Windows SDK:</span></span>  
  
- <span data-ttu-id="59494-106">Creare un oggetto usando l'operatore **New** .</span><span class="sxs-lookup"><span data-stu-id="59494-106">Create an object by using the **new** operator.</span></span>  
  
- <span data-ttu-id="59494-107">Creare un oggetto che implementa un algoritmo di crittografia particolare chiamando il metodo **create** sulla classe astratta per tale algoritmo.</span><span class="sxs-lookup"><span data-stu-id="59494-107">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
- <span data-ttu-id="59494-108">Creare un oggetto che implementa un algoritmo di crittografia particolare chiamando il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="59494-108">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="59494-109">Creare un oggetto che implementi una classe di algoritmi di crittografia, ad esempio una crittografia a blocchi simmetrica, chiamando il metodo **create** sulla classe astratta per quel tipo di algoritmo (ad esempio <xref:System.Security.Cryptography.SymmetricAlgorithm> ).</span><span class="sxs-lookup"><span data-stu-id="59494-109">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="59494-110">Si supponga, ad esempio, che uno sviluppatore desideri calcolare l'hash SHA1 di un set di byte.</span><span class="sxs-lookup"><span data-stu-id="59494-110">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="59494-111">Lo <xref:System.Security.Cryptography> spazio dei nomi contiene due implementazioni dell'algoritmo SHA1, un'implementazione gestita esclusivamente e una che esegue il wrapping di CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="59494-111">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="59494-112">Lo sviluppatore può scegliere di creare un'istanza di un'implementazione SHA1 specifica, ad esempio, <xref:System.Security.Cryptography.SHA1Managed> chiamando l'operatore **New** .</span><span class="sxs-lookup"><span data-stu-id="59494-112">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="59494-113">Tuttavia, se non è importante la classe caricata da Common Language Runtime a condizione che la classe implementi l'algoritmo hash SHA1, lo sviluppatore può creare un oggetto chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="59494-113">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="59494-114">Questo metodo chiama **System. Security. Cryptography. CryptoConfig. CreateFromName ("System. Security. Cryptography. SHA1")**, che deve restituire un'implementazione dell'algoritmo hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="59494-114">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="59494-115">Lo sviluppatore può anche chiamare **System. Security. Cryptography. CryptoConfig. CreateFromName ("SHA1")** perché, per impostazione predefinita, la configurazione della crittografia include nomi brevi per gli algoritmi forniti nell'.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="59494-115">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="59494-116">Se non è rilevante l'algoritmo hash usato, lo sviluppatore può chiamare il <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> metodo, che restituisce un oggetto che implementa una trasformazione hash.</span><span class="sxs-lookup"><span data-stu-id="59494-116">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="59494-117">Mapping dei nomi degli algoritmi nei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="59494-117">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="59494-118">Per impostazione predefinita, il runtime restituisce un <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> oggetto per tutti e quattro gli scenari.</span><span class="sxs-lookup"><span data-stu-id="59494-118">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="59494-119">Un amministratore del computer può tuttavia modificare il tipo di oggetto restituito dai metodi negli ultimi due scenari.</span><span class="sxs-lookup"><span data-stu-id="59494-119">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="59494-120">A tale scopo, è necessario eseguire il mapping di un nome di algoritmo descrittivo alla classe che si desidera utilizzare nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="59494-120">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="59494-121">Nell'esempio seguente viene illustrato come configurare il runtime in modo che **System. Security. Cryptography. SHA1. Create**, **System. Security. CryptoConfig. CREATEFROMNAME ("SHA1")** e **System. Security. Cryptography. HashAlgorithm. Create** restituiscano un `MySHA1HashClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="59494-121">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="59494-122">È possibile specificare il nome dell'attributo nell' [ \> elemento<CryptoClass](./file-schema/cryptography/cryptoclass-element.md) (l'esempio precedente assegna un nome all'attributo `MySHA1Hash` ).</span><span class="sxs-lookup"><span data-stu-id="59494-122">You can specify the name of the attribute in the [<cryptoClass\> element](./file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="59494-123">Il valore dell'attributo nell' **\<cryptoClass>** elemento è una stringa utilizzata dal Common Language Runtime per trovare la classe.</span><span class="sxs-lookup"><span data-stu-id="59494-123">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="59494-124">È possibile usare qualsiasi stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="59494-124">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="59494-125">Molti nomi di algoritmi possono essere mappati alla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="59494-125">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="59494-126">L' [ \<nameEntry> elemento](./file-schema/cryptography/nameentry-element.md) esegue il mapping di una classe a un nome di algoritmo descrittivo.</span><span class="sxs-lookup"><span data-stu-id="59494-126">The [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="59494-127">L'attributo **Name** può essere una stringa utilizzata quando si chiama il metodo **System. Security. Cryptography. CryptoConfig. CreateFromName** o il nome di una classe di crittografia astratta nello <xref:System.Security.Cryptography> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="59494-127">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="59494-128">Il valore dell'attributo **Class** è il nome dell'attributo nell' **\<cryptoClass>** elemento.</span><span class="sxs-lookup"><span data-stu-id="59494-128">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59494-129">È possibile ottenere un algoritmo SHA1 chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> metodo o il metodo **Security. CryptoConfig. CreateFromName ("SHA1")** .</span><span class="sxs-lookup"><span data-stu-id="59494-129">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="59494-130">Ogni metodo garantisce solo che restituisca un oggetto che implementa l'algoritmo SHA1.</span><span class="sxs-lookup"><span data-stu-id="59494-130">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="59494-131">Non è necessario eseguire il mapping di ogni nome descrittivo di un algoritmo alla stessa classe nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="59494-131">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="59494-132">Per un elenco di nomi predefiniti e le classi a cui eseguono il mapping, vedere <xref:System.Security.Cryptography.CryptoConfig> .</span><span class="sxs-lookup"><span data-stu-id="59494-132">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59494-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59494-133">See also</span></span>

- [<span data-ttu-id="59494-134">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="59494-134">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="59494-135">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="59494-135">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
