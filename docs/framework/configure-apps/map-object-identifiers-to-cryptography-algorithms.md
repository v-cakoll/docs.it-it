---
title: Mapping di identificatori di oggetti ad algoritmi di crittografia
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: e035ff04a70a441f7f64bbc230ba6d8036fb2ace
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130611"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="6b54e-102">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="6b54e-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="6b54e-103">Le firme digitali garantiscono che i dati non venga manomesso quando viene inviato da un programma a un altro.</span><span class="sxs-lookup"><span data-stu-id="6b54e-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="6b54e-104">In genere la firma digitale viene calcolata applicando una funzione matematica l'hash dei dati da firmare.</span><span class="sxs-lookup"><span data-stu-id="6b54e-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="6b54e-105">Quando si formatta un valore hash deve essere firmato, alcuni algoritmi di firma digitale accodare un identificatore di oggetto ASN.1 (OID) come parte dell'operazione di formattazione.</span><span class="sxs-lookup"><span data-stu-id="6b54e-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="6b54e-106">L'identificatore di oggetto identifica l'algoritmo utilizzato per calcolare l'hash.</span><span class="sxs-lookup"><span data-stu-id="6b54e-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="6b54e-107">È possibile mappare gli algoritmi per gli identificatori di oggetto per estendere il meccanismo di crittografia per l'uso di algoritmi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6b54e-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="6b54e-108">Nell'esempio seguente viene illustrato come eseguire il mapping di un identificatore di oggetto a un nuovo algoritmo di hash.</span><span class="sxs-lookup"><span data-stu-id="6b54e-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="6b54e-109">Il [ \<oidEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contiene due attributi.</span><span class="sxs-lookup"><span data-stu-id="6b54e-109">The [\<oidEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="6b54e-110">Il **OID** attributo è il numero dell'identificatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="6b54e-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="6b54e-111">Il **name** attributo è il valore della **nome** dell'attributo dal [ \<nameEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="6b54e-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="6b54e-112">Deve essere presente un mapping da nome di un algoritmo a una classe prima di un identificatore di oggetto può essere mappato a un nome semplice.</span><span class="sxs-lookup"><span data-stu-id="6b54e-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b54e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b54e-113">See also</span></span>

- [<span data-ttu-id="6b54e-114">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="6b54e-114">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="6b54e-115">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="6b54e-115">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
