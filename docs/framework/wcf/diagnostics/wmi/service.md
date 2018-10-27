---
title: Service
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2018
ms.locfileid: "49633950"
---
# <a name="service"></a>Service
Service  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
