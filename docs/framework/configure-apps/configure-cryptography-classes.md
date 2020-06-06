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
ms.openlocfilehash: e53f4c5c9e24fb25b43b7f27b80ab984214eeac2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927777"
---
# <a name="configuring-cryptography-classes"></a>Configurazione di classi di crittografia
Il Windows SDK consente agli amministratori di computer di configurare gli algoritmi di crittografia e le implementazioni degli algoritmi predefiniti che vengono utilizzati dall'.NET Framework e dalle applicazioni scritte in modo appropriato.  Ad esempio, un'azienda che dispone di una propria implementazione di un algoritmo crittografico può rendere tale implementazione il valore predefinito anziché l'implementazione fornita nel Windows SDK. Sebbene le applicazioni gestite che usano la crittografia possano sempre scegliere di eseguire un'associazione esplicita a una particolare implementazione, è consigliabile creare oggetti crittografici usando il sistema di configurazione della crittografia.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Mapping di nomi di algoritmi a classi di crittografia](map-algorithm-names-to-cryptography-classes.md)  
 Viene descritto come eseguire il mapping di un nome di algoritmo a una classe di crittografia.  
  
 [Mapping di identificatori di oggetti ad algoritmi di crittografia](map-object-identifiers-to-cryptography-algorithms.md)  
 Viene descritto come eseguire il mapping di un identificatore di oggetto a un algoritmo di crittografia.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Servizi di crittografia](../../standard/security/cryptographic-services.md)  
 Viene fornita una panoramica dei servizi di crittografia forniti dal Windows SDK.  
  
 [Schema delle impostazioni di crittografia](./file-schema/cryptography/index.md)  
 Vengono descritti gli elementi che eseguono il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.
