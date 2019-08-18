---
title: Mapping di nomi di algoritmi a classi di crittografia
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 49f4b5b4b3634df5e648b5208448d644168e9d19
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566731"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="80503-102">Mapping di nomi di algoritmi a classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="80503-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="80503-103">Esistono quattro modi per creare un oggetto di crittografia usando il Windows SDK:</span><span class="sxs-lookup"><span data-stu-id="80503-103">There are four ways a developer can create a cryptography object using the Windows SDK:</span></span>  
  
- <span data-ttu-id="80503-104">Creare un oggetto usando l'operatore **New** .</span><span class="sxs-lookup"><span data-stu-id="80503-104">Create an object by using the **new** operator.</span></span>  
  
- <span data-ttu-id="80503-105">Creare un oggetto che implementa un algoritmo di crittografia particolare chiamando il metodo **create** sulla classe astratta per tale algoritmo.</span><span class="sxs-lookup"><span data-stu-id="80503-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
- <span data-ttu-id="80503-106">Creare un oggetto che implementa un algoritmo di crittografia particolare chiamando il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="80503-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="80503-107">Creare un oggetto che implementi una classe di algoritmi di crittografia, ad esempio una crittografia a blocchi simmetrica, chiamando il metodo **create** sulla classe astratta per quel tipo di algoritmo (ad esempio <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span><span class="sxs-lookup"><span data-stu-id="80503-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="80503-108">Si supponga, ad esempio, che uno sviluppatore desideri calcolare l'hash SHA1 di un set di byte.</span><span class="sxs-lookup"><span data-stu-id="80503-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="80503-109">Lo <xref:System.Security.Cryptography> spazio dei nomi contiene due implementazioni dell'algoritmo SHA1, un'implementazione gestita esclusivamente e una che esegue il wrapping di CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="80503-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="80503-110">Lo sviluppatore può scegliere di creare un'istanza di un'implementazione SHA1 specifica, ad <xref:System.Security.Cryptography.SHA1Managed>esempio, chiamando l'operatore **New** .</span><span class="sxs-lookup"><span data-stu-id="80503-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="80503-111">Tuttavia, se non è importante la classe caricata da Common Language Runtime a condizione che la classe implementi l'algoritmo hash SHA1, lo sviluppatore può creare un oggetto chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="80503-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="80503-112">Questo metodo chiama **System. Security. Cryptography. CryptoConfig. CreateFromName ("System. Security. Cryptography. SHA1")** , che deve restituire un'implementazione dell'algoritmo hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="80503-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="80503-113">Lo sviluppatore può anche chiamare **System. Security. Cryptography. CryptoConfig. CreateFromName ("SHA1")** perché, per impostazione predefinita, la configurazione della crittografia include nomi brevi per gli algoritmi forniti nell'.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="80503-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="80503-114">Se non è rilevante l'algoritmo hash usato, lo sviluppatore può chiamare il <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> metodo, che restituisce un oggetto che implementa una trasformazione hash.</span><span class="sxs-lookup"><span data-stu-id="80503-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="80503-115">Mapping dei nomi degli algoritmi nei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="80503-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="80503-116">Per impostazione predefinita, il runtime restituisce <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> un oggetto per tutti e quattro gli scenari.</span><span class="sxs-lookup"><span data-stu-id="80503-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="80503-117">Un amministratore del computer può tuttavia modificare il tipo di oggetto restituito dai metodi negli ultimi due scenari.</span><span class="sxs-lookup"><span data-stu-id="80503-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="80503-118">A tale scopo, è necessario eseguire il mapping di un nome di algoritmo descrittivo alla classe che si desidera utilizzare nel file di configurazione del computer (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="80503-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="80503-119">Nell'esempio seguente viene illustrato come configurare il runtime in modo che **System. Security. Cryptography. SHA1. Create**, **System. Security. CryptoConfig. CREATEFROMNAME ("SHA1")** e **System. Security. Cryptography. HashAlgorithm. Create** restituisce un `MySHA1HashClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="80503-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
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
  
 <span data-ttu-id="80503-120">È possibile specificare il nome dell'attributo nell' [elemento < CryptoClass\> ](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (l'esempio precedente assegna un nome all'attributo `MySHA1Hash`).</span><span class="sxs-lookup"><span data-stu-id="80503-120">You can specify the name of the attribute in the [<cryptoClass\> element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="80503-121">Il valore dell'attributo nell'  **\<elemento > CryptoClass** è una stringa utilizzata dal Common Language Runtime per trovare la classe.</span><span class="sxs-lookup"><span data-stu-id="80503-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="80503-122">È possibile usare qualsiasi stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="80503-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="80503-123">Molti nomi di algoritmi possono essere mappati alla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="80503-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="80503-124">L' [ \<elemento > nameEntry](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) esegue il mapping di una classe a un nome di algoritmo descrittivo.</span><span class="sxs-lookup"><span data-stu-id="80503-124">The [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="80503-125">L'attributo **Name** può essere una stringa utilizzata quando si chiama il metodo **System. Security. Cryptography. CryptoConfig. CreateFromName** o il nome di una <xref:System.Security.Cryptography> classe di crittografia astratta nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="80503-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="80503-126">Il valore dell'attributo **Class** è il nome dell'attributo nell'  **\<elemento > CryptoClass** .</span><span class="sxs-lookup"><span data-stu-id="80503-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80503-127">È possibile ottenere un algoritmo SHA1 chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> metodo o il metodo **Security. CryptoConfig. CreateFromName ("SHA1")** .</span><span class="sxs-lookup"><span data-stu-id="80503-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="80503-128">Ogni metodo garantisce solo che restituisca un oggetto che implementa l'algoritmo SHA1.</span><span class="sxs-lookup"><span data-stu-id="80503-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="80503-129">Non è necessario eseguire il mapping di ogni nome descrittivo di un algoritmo alla stessa classe nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="80503-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="80503-130">Per un elenco di nomi predefiniti e le classi a cui eseguono il mapping <xref:System.Security.Cryptography.CryptoConfig>, vedere.</span><span class="sxs-lookup"><span data-stu-id="80503-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80503-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80503-131">See also</span></span>

- [<span data-ttu-id="80503-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="80503-132">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="80503-133">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="80503-133">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
