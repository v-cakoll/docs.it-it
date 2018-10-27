---
title: PeerCustomResolverBindingElement
ms.date: 03/30/2017
ms.assetid: 9ccc2770-a20e-4dff-9970-f56ad8aec2b5
ms.openlocfilehash: 62e52a1ebec8a55b51d3c918971c420fe45fdaa1
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50037863"
---
# <a name="peercustomresolverbindingelement"></a>PeerCustomResolverBindingElement
PeerCustomResolverBindingElement  
  
## <a name="syntax"></a>Sintassi  
```csharp
class PeerCustomResolverBindingElement : PeerResolverBindingElement
{  
    string Address;
    string Binding;
};
```  
  
## <a name="methods"></a>Metodi  
 La classe PeerCustomResolverBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe PeerCustomResolverBindingElement dispone delle proprietà seguenti:  
  
### <a name="address"></a>Indirizzo  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 L'indirizzo del resolver personalizzato del peer.  
  
### <a name="binding"></a>Binding  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome della configurazione dell'associazione.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement>
