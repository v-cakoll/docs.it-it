---
title: Configurazione di classi di crittografia
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 23bf831a4374add55258f5fb41c17a5d4a8f14c3
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832807"
---
# <a name="configuring-cryptography-classes"></a>Configurazione di classi di crittografia
Windows Software Development Kit (SDK) consente agli amministratori di computer configurare gli algoritmi di crittografia predefinito e implementazioni di algoritmi che usano .NET Framework e le applicazioni scritte in modo appropriato.  Ad esempio, un'azienda che ha la propria implementazione di un algoritmo di crittografia può utilizzare tale implementazione il valore predefinito anziché l'implementazione fornito nel SDK di Windows. Sebbene le applicazioni gestite che usano crittografia sempre possono scegliere di associare in modo esplicito a una particolare implementazione, è consigliabile che creano oggetti di crittografia utilizzando il sistema di configurazione della crittografia.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Mapping di nomi di algoritmi a classi di crittografia](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Viene descritto come eseguire il mapping di un nome di algoritmo a una classe di crittografia.  
  
 [Mapping di identificatori di oggetti ad algoritmi di crittografia](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Viene descritto come eseguire il mapping di un identificatore di oggetto a un algoritmo di crittografia.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Fornisce una panoramica di servizi di crittografia forniti da Windows SDK.  
  
 [Schema delle impostazioni di crittografia](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Vengono descritti gli elementi che eseguono il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.
