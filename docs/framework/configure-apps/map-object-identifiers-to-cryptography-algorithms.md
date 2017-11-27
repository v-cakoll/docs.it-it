---
title: Mapping di identificatori di oggetti ad algoritmi di crittografia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: dbfe394193925e38dad774d39d79ac813abef22a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Mapping di identificatori di oggetti ad algoritmi di crittografia
Verificare che le firme digitali che dati non vengono alterati quando viene inviato da un programma a un altro. In genere la firma digitale viene calcolata applicando una funzione matematica per l'hash dei dati da firmare. Quando si formatta un valore hash deve essere firmata, alcuni algoritmi di firma digitale accodare un identificatore di oggetto ASN. 1 (OID) come parte dell'operazione di formattazione. L'OID identifica l'algoritmo utilizzato per calcolare il valore hash. È possibile eseguire il mapping di algoritmi agli identificatori di oggetto per estendere il meccanismo di crittografia per l'utilizzo di algoritmi personalizzati. Nell'esempio seguente viene illustrato come eseguire il mapping di un identificatore di oggetto a un nuovo algoritmo di hash.  
  
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
  
 Il [ \<oidEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contiene due attributi. Il **OID** attributo è il numero dell'identificatore di oggetto. Il **nome** attributo è il valore della **nome** dall'attributo di [ \<nameEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md). Deve essere presente un mapping da un nome di algoritmo a una classe prima di un identificatore di oggetto può essere mappato a un nome semplice.  
  
## <a name="see-also"></a>Vedere anche  
 [Configurazione di classi di crittografia](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
