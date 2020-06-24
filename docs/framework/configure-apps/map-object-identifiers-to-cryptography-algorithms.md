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
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Mapping di identificatori di oggetti ad algoritmi di crittografia
Le firme digitali garantiscono che i dati non vengano manomessi quando vengono inviati da un programma a un altro. La firma digitale viene in genere calcolata applicando una funzione matematica all'hash dei dati da firmare. Quando si formatta un valore hash per la firma, alcuni algoritmi di firma digitale aggiungono un identificatore di oggetto ASN. 1 (OID) come parte dell'operazione di formattazione. L'OID identifica l'algoritmo utilizzato per calcolare l'hash. È possibile eseguire il mapping degli algoritmi agli identificatori di oggetto per estendere il meccanismo di crittografia per l'uso di algoritmi personalizzati. Nell'esempio seguente viene illustrato come eseguire il mapping di un identificatore di oggetto a un nuovo algoritmo hash.  
  
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
  
 L' [ \<oidEntry> elemento](./file-schema/cryptography/oidentry-element.md) contiene due attributi. L'attributo **OID** è il numero di identificatore dell'oggetto. L'attributo **Name** è il valore dell'attributo **Name** dell' [ \<nameEntry> elemento](./file-schema/cryptography/nameentry-element.md). Deve essere presente un mapping da un nome di algoritmo a una classe prima che sia possibile eseguire il mapping di un identificatore di oggetto a un nome semplice.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione di classi di crittografia](configure-cryptography-classes.md)
- [Servizi di crittografia](../../standard/security/cryptographic-services.md)
