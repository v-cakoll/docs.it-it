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
ms.openlocfilehash: 88c2513229b6a4183cadbdc78e505910e01e152c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796480"
---
# <a name="ienumdefinitionidentity-interface"></a>Interfaccia IEnumDefinitionIdentity
Funge da enumeratore per una raccolta di `IDefinitionIdentity` oggetti.  
  
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
  
|Metodo|DESCRIZIONE|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|Ottiene un puntatore a interfaccia a un `IEnumDefinitionIdentity` nuovo oggetto che contiene gli stessi membri di `IEnumDefinitionIdentity`questo oggetto.|  
|`IEnumDefinitionIdentity::Next`|Ottiene il numero specificato di `IDefinitionIdentity` oggetti, a partire dalla posizione corrente.|  
|`IEnumDefinitionIdentity::Reset`|Sposta il puntatore all'istruzione all'inizio di questo `IEnumDefinitionIdentity`oggetto.|  
|`IEnumDefinitionIdentity::Skip`|Sposta il puntatore all'istruzione in poi in base al numero specificato di elementi, a partire dalla posizione corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Interfaccia IDefinitionIdentity](idefinitionidentity-interface.md)
