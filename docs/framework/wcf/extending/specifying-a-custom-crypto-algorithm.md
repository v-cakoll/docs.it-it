---
title: Specifica di un algoritmo di crittografia personalizzato
ms.date: 03/30/2017
ms.assetid: d662a305-8e09-451d-9a59-b0f12b012f1d
ms.openlocfilehash: 673d177a665e265d77f0221e0a00f4b814c8795c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186485"
---
# <a name="specifying-a-custom-crypto-algorithm"></a><span data-ttu-id="06188-102">Specifica di un algoritmo di crittografia personalizzato</span><span class="sxs-lookup"><span data-stu-id="06188-102">Specifying a Custom Crypto Algorithm</span></span>
<span data-ttu-id="06188-103">WCF consente di specificare un algoritmo di crittografia personalizzato da usare per crittografare i dati o calcolare le firme digitali.</span><span class="sxs-lookup"><span data-stu-id="06188-103">WCF allows you to specify a custom crypto algorithm to use when encrypting data or computing digital signatures.</span></span> <span data-ttu-id="06188-104">A tale scopo, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="06188-104">This is done by the following steps:</span></span>  
  
1. <span data-ttu-id="06188-105">Derivare una classe da <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="06188-105">Derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite></span></span>  
  
2. <span data-ttu-id="06188-106">Registrare l'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="06188-106">Register the algorithm</span></span>  
  
3. <span data-ttu-id="06188-107">Configurare l'associazione con la classe derivata da <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="06188-107">Configure the binding with the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class.</span></span>  
  
## <a name="derive-a-class-from-securityalgorithmsuite"></a><span data-ttu-id="06188-108">Derivare una classe da SecurityAlgorithmSuite.</span><span class="sxs-lookup"><span data-stu-id="06188-108">Derive a class from SecurityAlgorithmSuite</span></span>  
 <span data-ttu-id="06188-109"><xref:System.ServiceModel.Security.SecurityAlgorithmSuite> è una classe di base astratta che consente di specificare l'algoritmo da usare per eseguire diverse operazioni relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="06188-109">The <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> is an abstract base class that allows you to specify the algorithm to use when performing various security related operations.</span></span> <span data-ttu-id="06188-110">Ad esempio, calcolare un hash per una firma digitale o crittografare un messaggio.</span><span class="sxs-lookup"><span data-stu-id="06188-110">For example, computing a hash for a digital signature or encrypting a message.</span></span> <span data-ttu-id="06188-111">Nel codice seguente viene illustrato come derivare una classe da <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="06188-111">The following code shows how to derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>:</span></span>  
  
```csharp  
public class MyCustomAlgorithmSuite : SecurityAlgorithmSuite  
    {  
        public override string DefaultAsymmetricKeyWrapAlgorithm  
        {  
            get { return SecurityAlgorithms.RsaOaepKeyWrap; }  
        }  
  
        public override string DefaultAsymmetricSignatureAlgorithm  
        {  
            get { return SecurityAlgorithms.RsaSha1Signature; }  
        }  
  
        public override string DefaultCanonicalizationAlgorithm  
        {  
            get { return SecurityAlgorithms.ExclusiveC14n; ; }  
        }  
  
        public override string DefaultDigestAlgorithm  
        {  
            get { return SecurityAlgorithms.MyCustomHashAlgorithm; }  
        }  
  
        public override string DefaultEncryptionAlgorithm  
        {  
            get { return SecurityAlgorithms.Aes128Encryption; }  
        }  
  
        public override int DefaultEncryptionKeyDerivationLength  
        {  
            get { return 128; }  
        }  
  
        public override int DefaultSignatureKeyDerivationLength  
        {  
            get { return 128; }  
        }  
  
        public override int DefaultSymmetricKeyLength  
        {  
            get { return 128; }  
        }  
  
        public override string DefaultSymmetricKeyWrapAlgorithm  
        {  
            get { return SecurityAlgorithms.Aes128Encryption; }  
        }  
  
        public override string DefaultSymmetricSignatureAlgorithm  
        {  
            get { return SecurityAlgorithms.HmacSha1Signature; }  
        }  
  
        public override bool IsAsymmetricKeyLengthSupported(int length)  
        {  
            return length >= 1024 && length <= 4096;  
        }  
  
        public override bool IsSymmetricKeyLengthSupported(int length)  
        {  
            return length >= 128 && length <= 256;  
        }  
    }  
```  
  
## <a name="register-the-custom-algorithm"></a><span data-ttu-id="06188-112">Registrare l'algoritmo personalizzato</span><span class="sxs-lookup"><span data-stu-id="06188-112">Register the Custom Algorithm</span></span>  
 <span data-ttu-id="06188-113">La registrazione può essere eseguita in un file di configurazione o nel codice imperativo.</span><span class="sxs-lookup"><span data-stu-id="06188-113">Registration can be done in a configuration file or in imperative code.</span></span> <span data-ttu-id="06188-114">La registrazione di un algoritmo personalizzato viene eseguita creando un mapping tra una classe che implementa un provider di servizi di crittografia e un alias.</span><span class="sxs-lookup"><span data-stu-id="06188-114">Registering a custom algorithm is done by creating a mapping between a class that implements a crypto service provider and an alias.</span></span> <span data-ttu-id="06188-115">L'alias viene quindi mappato a un URI che viene usato per specificare l'algoritmo nell'associazione del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="06188-115">The alias is then mapped to a URI which is used when specifying the algorithm in the WCF service’s binding.</span></span> <span data-ttu-id="06188-116">Nel frammento di configurazione seguente viene illustrato come registrare un algoritmo personalizzato in config:</span><span class="sxs-lookup"><span data-stu-id="06188-116">The following configuration snippet illustrates how to register a custom algorithm in config:</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
           <cryptoClasses>  
              <cryptoClass SHA256CSP="System.Security.Cryptography.SHA256CryptoServiceProvider, System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
           </cryptoClasses>  
           <nameEntry name="http://constoso.com/CustomAlgorithms/CustomHashAlgorithm"  
              class="SHA256CSP" />  
           </cryptoNameMapping>  
        </cryptographySettings>  
    </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="06188-117">La sezione sotto `cryptoClasses` l'elemento <> crea il mapping tra SHA256CryptoServiceProvider e l'alias "SHA256CSP".</span><span class="sxs-lookup"><span data-stu-id="06188-117">The section under the <`cryptoClasses`> element creates the mapping between the SHA256CryptoServiceProvider and the alias "SHA256CSP".</span></span> <span data-ttu-id="06188-118">L'elemento> <`nameEntry` crea il mapping tra l'alias "SHA256CSP" e l'URL `http://constoso.com/CustomAlgorithms/CustomHashAlgorithm`specificato.</span><span class="sxs-lookup"><span data-stu-id="06188-118">The <`nameEntry`> element creates the mapping between the "SHA256CSP" alias and the specified URL `http://constoso.com/CustomAlgorithms/CustomHashAlgorithm`.</span></span>  
  
 <span data-ttu-id="06188-119">Per registrare l'algoritmo personalizzato nel codice usare il metodo <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm(System.Type,System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="06188-119">To register the custom algorithm in code use the <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm(System.Type,System.String[])> method.</span></span> <span data-ttu-id="06188-120">Questo metodo crea entrambi i mapping.</span><span class="sxs-lookup"><span data-stu-id="06188-120">This method creates both mappings.</span></span> <span data-ttu-id="06188-121">Nell'esempio seguente viene illustrato come chiamare questo metodo:</span><span class="sxs-lookup"><span data-stu-id="06188-121">The following example shows how to call this method:</span></span>  
  
```csharp
// Register the custom URI string defined for the hashAlgorithm in MyCustomAlgorithmSuite class to create the
// SHA256CryptoServiceProvider hash algorithm object.  
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), "http://constoso.com/CustomAlgorithms/CustomHashAlgorithm");  
```  
  
## <a name="configure-the-binding"></a><span data-ttu-id="06188-122">Configurare l'associazione</span><span class="sxs-lookup"><span data-stu-id="06188-122">Configure the Binding</span></span>  
 <span data-ttu-id="06188-123">L'associazione si configura specificando la classe derivata da <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> nelle impostazioni di associazione, come indicato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="06188-123">You configure the binding by specifying the custom <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class in the binding settings as shown in the following code snippet:</span></span>  
  
```csharp  
WSHttpBinding binding = new WSHttpBinding();  
            binding.Security.Message.AlgorithmSuite = new MyCustomAlgorithmSuite();  
```  
  
 <span data-ttu-id="06188-124">Per un esempio di codice completo, vedere l'agilità [di crittografia nella sicurezza WCF](../samples/cryptographic-agility-in-wcf-security.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="06188-124">For a complete code example, see the [Cryptographic Agility in WCF Security](../samples/cryptographic-agility-in-wcf-security.md) sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06188-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06188-125">See also</span></span>

- [<span data-ttu-id="06188-126">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="06188-126">Securing Services and Clients</span></span>](../feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="06188-127">Protezione dei servizi</span><span class="sxs-lookup"><span data-stu-id="06188-127">Securing Services</span></span>](../securing-services.md)
- [<span data-ttu-id="06188-128">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="06188-128">Security Overview</span></span>](../feature-details/security-overview.md)
- [<span data-ttu-id="06188-129">Concetti relativi alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="06188-129">Security Concepts</span></span>](../feature-details/security-concepts.md)
