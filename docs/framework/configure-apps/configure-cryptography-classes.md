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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b12d5d95a17439308d79d094e8c22206778f3128
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="configuring-cryptography-classes"></a>Configurazione di classi di crittografia
Il [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] consente agli amministratori di configurare gli algoritmi di crittografia predefinito e le implementazioni di algoritmi che usano .NET Framework e le applicazioni scritte in modo appropriato.  Ad esempio, un'azienda che dispone di una propria implementazione di un algoritmo di crittografia può utilizzare tale implementazione il valore predefinito anziché l'implementazione fornito con il [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]. Sebbene le applicazioni gestite che utilizzano la crittografia è comunque sempre possibile associare in modo esplicito a una particolare implementazione, è consigliabile creare oggetti di crittografia utilizzando il sistema di configurazione di crittografia.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Mapping di nomi di algoritmi a classi di crittografia](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Viene descritto come eseguire il mapping di un nome di algoritmo a una classe di crittografia.  
  
 [Mapping di identificatori di oggetti ad algoritmi di crittografia](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Viene descritto come eseguire il mapping di un identificatore di oggetto a un algoritmo di crittografia.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Viene fornita una panoramica di servizi di crittografia forniti dal [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  
  
 [Schema delle impostazioni di crittografia](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Vengono descritti gli elementi che eseguono il mapping dei nomi descrittivi degli algoritmi alle classi che implementano gli algoritmi di crittografia.
