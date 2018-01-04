---
title: Service
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7b631ede7bd011a92003dc5f6083c1c427d990e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="service"></a>Service
Service  
  
## <a name="syntax"></a>Sintassi  
  
```  
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe Service non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe Service presenta le proprietà seguenti:  
  
### <a name="baseaddresses"></a>BaseAddresses  
 Tipo di dati: matrice di stringhe  
  
 Tipo di accesso: sola lettura  
  
 Indirizzi di base utilizzati dal servizio.  
  
### <a name="behaviors"></a>comportamenti  
 Tipo di dati: matrice di Behavior  
  
 Tipo di accesso: sola lettura  
  
 Comportamenti associati al servizio.  
  
### <a name="configurationname"></a>ConfigurationName  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 ServiceElement_BehaviorConfiguration  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome dell'istanza del contatore delle prestazioni del servizio.  
  
### <a name="distinguishedname"></a>DistinguishedName  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome del servizio all'indirizzo.  
  
### <a name="extensions"></a>Estensioni  
 Tipo di dati: matrice di stringhe  
  
 Tipo di accesso: sola lettura  
  
 Contesti dell'istanza per le estensioni dell'istanza del servizio.  
  
### <a name="metadata"></a>Metadati  
 Tipo di dati: matrice di stringhe  
  
 Tipo di accesso: sola lettura  
  
 Impostazioni dei metadati del servizio.  
  
### <a name="name"></a>nome  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome univoco del servizio.  
  
### <a name="namespace"></a>Spazio dei nomi  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Spazio dei nomi del servizio.  
  
### <a name="opened"></a>Opened  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Ora in cui il servizio è stato aperto.  
  
### <a name="outgoingchannels"></a>OutgoingChannels  
 Tipo di dati: matrice di Channel  
  
 Tipo di accesso: sola lettura  
  
 Canali in uscita dall'istanza di servizio.  
  
### <a name="processid"></a>ProcessId  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Id del processo che ospita il servizio.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|
