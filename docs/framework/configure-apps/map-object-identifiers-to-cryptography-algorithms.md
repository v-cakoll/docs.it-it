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
ms.openlocfilehash: a5aebac2d392d4540581dfe7c7afff0819968ac0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69912547"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="ad9e5-102">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="ad9e5-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="ad9e5-103">Le firme digitali garantiscono che i dati non vengano manomessi quando vengono inviati da un programma a un altro.</span><span class="sxs-lookup"><span data-stu-id="ad9e5-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="ad9e5-104">La firma digitale viene in genere calcolata applicando una funzione matematica all'hash dei dati da firmare.</span><span class="sxs-lookup"><span data-stu-id="ad9e5-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="ad9e5-105">Quando si formatta un valore hash per la firma, alcuni algoritmi di firma digitale aggiungono un identificatore di oggetto ASN. 1 (OID) come parte dell'operazione di formattazione.</span><span class="sxs-lookup"><span data-stu-id="ad9e5-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="ad9e5-106">L'OID identifica l'algoritmo utilizzato per calcolare l'hash.</span><span class="sxs-lookup"><span data-stu-id="ad9e5-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="ad9e5-107">È possibile eseguire il mapping degli algoritmi agli identificatori di oggetto per estendere il meccanismo di crittografia per l'uso di algoritmi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ad9e5-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="ad9e5-108">Nell'esempio seguente viene illustrato come eseguire il mapping di un identificatore di oggetto a un nuovo algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="ad9e5-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="ad9e5-109">L' [ \<oidEntry> elemento](./file-schema/cryptography/oidentry-element.md) contiene due attributi.</span><span class="sxs-lookup"><span data-stu-id="ad9e5-109">The [\<oidEntry> element](./file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="ad9e5-110">L'attributo **OID** è il numero di identificatore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ad9e5-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="ad9e5-111">L'attributo **Name** è il valore dell'attributo **Name** dell' [ \<nameEntry> elemento](./file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="ad9e5-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="ad9e5-112">Deve essere presente un mapping da un nome di algoritmo a una classe prima che sia possibile eseguire il mapping di un identificatore di oggetto a un nome semplice.</span><span class="sxs-lookup"><span data-stu-id="ad9e5-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad9e5-113">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ad9e5-113">See also</span></span>

- [<span data-ttu-id="ad9e5-114">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="ad9e5-114">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
- [<span data-ttu-id="ad9e5-115">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="ad9e5-115">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
