---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: aaf0dd9d6918f2c248942cee3773eee8332adda9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552840"
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
 Tipo di dati: Matrice di BindingElement  
  
 Tipo di accesso: Sola lettura  
  
 Raccolta di elementi di associazione implementati dall'associazione.  
  
### <a name="closetimeout"></a>CloseTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Intervallo di tempo consentito per il completamento di un'operazione di chiusura.  
  
### <a name="name"></a>nome  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Nome dell'associazione.  
  
### <a name="namespace"></a>Spazio dei nomi  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Spazio dei nomi XML dell'associazione.  
  
### <a name="opentimeout"></a>OpenTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Intervallo di tempo consentito per il completamento di un'operazione di apertura.  
  
### <a name="receivetimeout"></a>ReceiveTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Intervallo di tempo consentito per il completamento di un'operazione di ricezione.  
  
### <a name="scheme"></a>Scheme  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Schema di trasporto URI utilizzato dalla channel factory e dalla listener factory generate dall'associazione.  
  
### <a name="sendtimeout"></a>SendTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Intervallo di tempo consentito per il completamento di un'operazione di invio.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Channels.Binding>
