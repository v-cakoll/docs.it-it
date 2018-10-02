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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d23fc48a53ee47aacfc290b52887b800ce37477f
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48036859"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Mapping di identificatori di oggetti ad algoritmi di crittografia
Le firme digitali garantiscono che i dati non venga manomesso quando viene inviato da un programma a un altro. In genere la firma digitale viene calcolata applicando una funzione matematica l'hash dei dati da firmare. Quando si formatta un valore hash deve essere firmato, alcuni algoritmi di firma digitale accodare un identificatore di oggetto ASN.1 (OID) come parte dell'operazione di formattazione. L'identificatore di oggetto identifica l'algoritmo utilizzato per calcolare l'hash. È possibile mappare gli algoritmi per gli identificatori di oggetto per estendere il meccanismo di crittografia per l'uso di algoritmi personalizzati. Nell'esempio seguente viene illustrato come eseguire il mapping di un identificatore di oggetto a un nuovo algoritmo di hash.  
  
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
  
 Il [ \<oidEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contiene due attributi. Il **OID** attributo è il numero dell'identificatore di oggetto. Il **name** attributo è il valore della **nome** dell'attributo dal [ \<nameEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md). Deve essere presente un mapping da nome di un algoritmo a una classe prima di un identificatore di oggetto può essere mappato a un nome semplice.  
  
## <a name="see-also"></a>Vedere anche  
 [Configurazione di classi di crittografia](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
