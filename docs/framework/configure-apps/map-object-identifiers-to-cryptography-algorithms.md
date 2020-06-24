---
title: Mapping di identificatori di oggetti ad algoritmi di crittografia
description: Vedere come eseguire il mapping di un identificatore di oggetto (OID) a un algoritmo di crittografia in .NET usando gli elementi oidEntry e nameEntry in un file di configurazione XML.
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: e22510014071455b83ba28cd82690b5ecdce9bc9
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "85142004"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="871e5-103">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="871e5-103">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="871e5-104">Le firme digitali garantiscono che i dati non vengano manomessi quando vengono inviati da un programma a un altro.</span><span class="sxs-lookup"><span data-stu-id="871e5-104">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="871e5-105">La firma digitale viene in genere calcolata applicando una funzione matematica all'hash dei dati da firmare.</span><span class="sxs-lookup"><span data-stu-id="871e5-105">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="871e5-106">Quando si formatta un valore hash per la firma, alcuni algoritmi di firma digitale aggiungono un identificatore di oggetto ASN. 1 (OID) come parte dell'operazione di formattazione.</span><span class="sxs-lookup"><span data-stu-id="871e5-106">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="871e5-107">L'OID identifica l'algoritmo utilizzato per calcolare l'hash.</span><span class="sxs-lookup"><span data-stu-id="871e5-107">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="871e5-108">È possibile eseguire il mapping degli algoritmi agli identificatori di oggetto per estendere il meccanismo di crittografia per l'uso di algoritmi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="871e5-108">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="871e5-109">Nell'esempio seguente viene illustrato come eseguire il mapping di un identificatore di oggetto a un nuovo algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="871e5-109">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="871e5-110">L' [ \<oidEntry> elemento](./file-schema/cryptography/oidentry-element.md) contiene due attributi.</span><span class="sxs-lookup"><span data-stu-id="871e5-110">The [\<oidEntry> element](./file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="871e5-111">L'attributo **OID** è il numero di identificatore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="871e5-111">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="871e5-112">L'attributo **Name** è il valore dell'attributo **Name** dell' [ \<nameEntry> elemento](./file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="871e5-112">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="871e5-113">Deve essere presente un mapping da un nome di algoritmo a una classe prima che sia possibile eseguire il mapping di un identificatore di oggetto a un nome semplice.</span><span class="sxs-lookup"><span data-stu-id="871e5-113">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="871e5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="871e5-114">See also</span></span>

- [<span data-ttu-id="871e5-115">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="871e5-115">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
- [<span data-ttu-id="871e5-116">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="871e5-116">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
