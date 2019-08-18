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
ms.openlocfilehash: 77f26405792ac782f2a04e174e8165a09b7f22f6
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567342"
---
# <a name="configuring-cryptography-classes"></a>Configurazione di classi di crittografia
Il Windows SDK consente agli amministratori di computer di configurare gli algoritmi di crittografia e le implementazioni degli algoritmi predefiniti che vengono utilizzati dall'.NET Framework e dalle applicazioni scritte in modo appropriato.  Ad esempio, un'azienda che dispone di una propria implementazione di un algoritmo crittografico può rendere tale implementazione il valore predefinito anziché l'implementazione fornita nel Windows SDK. Sebbene le applicazioni gestite che usano la crittografia possano sempre scegliere di eseguire un'associazione esplicita a una particolare implementazione, è consigliabile creare oggetti crittografici usando il sistema di configurazione della crittografia.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Mapping di nomi di algoritmi a classi di crittografia](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Viene descritto come eseguire il mapping di un nome di algoritmo a una classe di crittografia.  
  
 [Mapping di identificatori di oggetti ad algoritmi di crittografia](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Viene descritto come eseguire il mapping di un identificatore di oggetto a un algoritmo di crittografia.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Viene fornita una panoramica dei servizi di crittografia forniti dal Windows SDK.  
  
 [Schema delle impostazioni di crittografia](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Vengono descritti gli elementi che eseguono il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.
