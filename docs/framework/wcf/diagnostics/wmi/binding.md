---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: 84e304f3dedcbd785d6238e6cb5eb142c288b995
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50033833"
---
# <a name="binding"></a>Binding
Associazione wmi  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe Binding non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe Binding dispone delle proprietà seguenti:  
  
### <a name="bindingelements"></a>BindingElements  
 Tipo di dati: matrice di BindingElement  
  
 Tipo di accesso: sola lettura  
  
 Raccolta di elementi di associazione implementati dall'associazione.  
  
### <a name="closetimeout"></a>CloseTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Intervallo di tempo consentito per il completamento di un'operazione di chiusura.  
  
### <a name="name"></a>nome  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome dell'associazione.  
  
### <a name="namespace"></a>Spazio dei nomi  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Spazio dei nomi XML dell'associazione.  
  
### <a name="opentimeout"></a>OpenTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Intervallo di tempo consentito per il completamento di un'operazione di apertura.  
  
### <a name="receivetimeout"></a>ReceiveTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Intervallo di tempo consentito per il completamento di un'operazione di ricezione.  
  
### <a name="scheme"></a>Scheme  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Schema di trasporto URI utilizzato dalla channel factory e dalla listener factory generate dall'associazione.  
  
### <a name="sendtimeout"></a>SendTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Intervallo di tempo consentito per il completamento di un'operazione di invio.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.Binding>
