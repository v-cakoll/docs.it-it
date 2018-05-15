---
title: Mapping di nomi di algoritmi a classi di crittografia
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2dc03c3aa6808ed4ce0c22f4e69fa8c98cb7aebd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="bafde-102">Mapping di nomi di algoritmi a classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="bafde-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="bafde-103">Esistono quattro modi diversi, uno sviluppatore può creare un oggetto di crittografia utilizzando il [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bafde-103">There are four ways a developer can create a cryptography object using the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span></span>  
  
-   <span data-ttu-id="bafde-104">Creare un oggetto utilizzando il **nuova** operatore.</span><span class="sxs-lookup"><span data-stu-id="bafde-104">Create an object by using the **new** operator.</span></span>  
  
-   <span data-ttu-id="bafde-105">Creare un oggetto che implementa un determinato algoritmo di crittografia tramite la chiamata di **crea** metodo sulla classe astratta per l'algoritmo di.</span><span class="sxs-lookup"><span data-stu-id="bafde-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
-   <span data-ttu-id="bafde-106">Creare un oggetto che implementa un determinato algoritmo di crittografia tramite la chiamata di <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="bafde-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="bafde-107">Creare un oggetto che implementa una classe di algoritmi di crittografia (ad esempio una crittografia a blocchi simmetrica) chiamando il **crea** metodo sulla classe astratta per il tipo di algoritmo (ad esempio <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span><span class="sxs-lookup"><span data-stu-id="bafde-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="bafde-108">Si supponga, ad esempio, che uno sviluppatore desidera calcolare l'hash SHA1 di un set di byte.</span><span class="sxs-lookup"><span data-stu-id="bafde-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="bafde-109">Il <xref:System.Security.Cryptography> dello spazio dei nomi contiene due implementazioni dell'algoritmo SHA1, un'implementazione semplicemente gestita e uno che esegue il wrapping di CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="bafde-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="bafde-110">Lo sviluppatore può scegliere di creare un'istanza di una determinata implementazione SHA1 (ad esempio il <xref:System.Security.Cryptography.SHA1Managed>) chiamando il **nuova** operatore.</span><span class="sxs-lookup"><span data-stu-id="bafde-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="bafde-111">Tuttavia, se non è rilevante la classe a cui viene caricato common language runtime, purché la classe implementa l'algoritmo hash SHA1, lo sviluppatore può creare un oggetto chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="bafde-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="bafde-112">Questo metodo chiama **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, che deve restituire un'implementazione dell'algoritmo hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="bafde-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="bafde-113">Lo sviluppatore può anche chiamare **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** perché, per impostazione predefinita, sistema di configurazione include i nomi brevi per gli algoritmi forniti in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bafde-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="bafde-114">Se non è importante algoritmo hash utilizzato, lo sviluppatore può chiamare il <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> metodo, che restituisce un oggetto che implementa una trasformazione di hash.</span><span class="sxs-lookup"><span data-stu-id="bafde-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="bafde-115">Mapping di nomi di algoritmo nei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="bafde-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="bafde-116">Per impostazione predefinita, viene restituito un <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> in tutti e quattro gli scenari.</span><span class="sxs-lookup"><span data-stu-id="bafde-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="bafde-117">Tuttavia, un amministratore del computer è possibile modificare il tipo di oggetto restituite dai metodi negli ultimi due scenari.</span><span class="sxs-lookup"><span data-stu-id="bafde-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="bafde-118">A tale scopo, è necessario mappare un nome descrittivo di algoritmo per la classe a cui che si desidera utilizzare nel file di configurazione del computer (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="bafde-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="bafde-119">Nell'esempio seguente viene illustrato come configurare il runtime in modo che **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, e  **HashAlgorithm** restituiscono un `MySHA1HashClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="bafde-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
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
  
 <span data-ttu-id="bafde-120">È possibile specificare il nome dell'attributo di [< cryptoClass\> elemento](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (nell'esempio precedente i nomi di attributo `MySHA1Hash`).</span><span class="sxs-lookup"><span data-stu-id="bafde-120">You can specify the name of the attribute in the [<cryptoClass\> element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="bafde-121">Il valore dell'attributo di  **\<cryptoClass >** elemento è una stringa che common language runtime utilizza per individuare la classe.</span><span class="sxs-lookup"><span data-stu-id="bafde-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="bafde-122">È possibile utilizzare qualsiasi stringa che soddisfi i requisiti indicati [specifica di nomi di tipo completi](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="bafde-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="bafde-123">Molti nomi di algoritmo possono eseguire il mapping alla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="bafde-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="bafde-124">Il [ \<nameEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) esegue il mapping di una classe a un nome descrittivo di algoritmo.</span><span class="sxs-lookup"><span data-stu-id="bafde-124">The [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="bafde-125">Il **nome** attributo può essere una stringa che viene utilizzata quando si chiama il **CreateFromName** metodo o il nome di una classe astratta di crittografia nel <xref:System.Security.Cryptography> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="bafde-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="bafde-126">Il valore di **classe** attributo è il nome dell'attributo nel  **\<cryptoClass >** elemento.</span><span class="sxs-lookup"><span data-stu-id="bafde-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bafde-127">È possibile ottenere un algoritmo SHA1 chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> o **Security.CryptoConfig.CreateFromName("SHA1")** metodo.</span><span class="sxs-lookup"><span data-stu-id="bafde-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="bafde-128">Ogni metodo assicura solo che restituisce un oggetto che implementa l'algoritmo SHA1.</span><span class="sxs-lookup"><span data-stu-id="bafde-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="bafde-129">Non è necessario eseguire il mapping di ogni nome di un algoritmo alla stessa classe nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bafde-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="bafde-130">Per un elenco dei nomi predefiniti e le classi a cui viene eseguito il mapping, vedere <xref:System.Security.Cryptography.CryptoConfig>.</span><span class="sxs-lookup"><span data-stu-id="bafde-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafde-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bafde-131">See Also</span></span>  
 [<span data-ttu-id="bafde-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="bafde-132">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="bafde-133">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="bafde-133">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
