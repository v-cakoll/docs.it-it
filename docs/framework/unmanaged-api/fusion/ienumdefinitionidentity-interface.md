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
ms.openlocfilehash: 09c6431ec885c8b797dc9bb5f5c3ffe21890ccc7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107949"
---
# <a name="ienumdefinitionidentity-interface"></a>Interfaccia IEnumDefinitionIdentity
Funge da enumeratore per una raccolta di oggetti `IDefinitionIdentity`.  
  
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
|`IEnumDefinitionIdentity::Clone`|Ottiene un puntatore a interfaccia a un nuovo oggetto `IEnumDefinitionIdentity` contenente gli stessi membri di questo `IEnumDefinitionIdentity`.|  
|`IEnumDefinitionIdentity::Next`|Ottiene il numero specificato di oggetti `IDefinitionIdentity`, a partire dalla posizione corrente.|  
|`IEnumDefinitionIdentity::Reset`|Sposta il puntatore all'istruzione all'inizio di questo `IEnumDefinitionIdentity`.|  
|`IEnumDefinitionIdentity::Skip`|Sposta il puntatore all'istruzione in poi in base al numero specificato di elementi, a partire dalla posizione corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Interfaccia IDefinitionIdentity](idefinitionidentity-interface.md)
