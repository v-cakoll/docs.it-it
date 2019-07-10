---
title: Interfaccia IEnumDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bbd8476b7778de6d0023f3a8522a44be6626884
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751522"
---
# <a name="ienumdefinitionidentity-interface"></a>Interfaccia IEnumDefinitionIdentity
Serve come enumeratore per una raccolta di `IDefinitionIdentity` oggetti.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|Ottiene un puntatore a interfaccia a una nuova `IEnumDefinitionIdentity` oggetto che contiene gli stessi membri di questo `IEnumDefinitionIdentity`.|  
|`IEnumDefinitionIdentity::Next`|Ottiene il numero specificato di `IDefinitionIdentity` oggetti, a partire dalla posizione corrente.|  
|`IEnumDefinitionIdentity::Reset`|Sposta il puntatore all'istruzione all'inizio di questo `IEnumDefinitionIdentity`.|  
|`IEnumDefinitionIdentity::Skip`|Sposta in avanti il puntatore all'istruzione per il numero specificato di elementi, a partire dalla posizione corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [Interfaccia IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
