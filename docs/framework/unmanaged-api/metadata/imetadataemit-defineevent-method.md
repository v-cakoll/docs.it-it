---
title: Metodo IMetaDataEmit::DefineEvent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ba35cd678d88389854ca2e866020ea3a9364c923
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777672"
---
# <a name="imetadataemitdefineevent-method"></a>Metodo IMetaDataEmit::DefineEvent
Crea una definizione per un evento con la firma dei metadati specificati e ottiene un token di definizione di tale evento.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 [in] Il token per la classe di destinazione o l'interfaccia. Questo è un `mdTypeDef` o `mdTypeDefNil` token.  
  
 `szEvent`  
 [in] Il nome dell'evento.  
  
 `dwEventFlags`  
 [in] Flag dell'evento.  
  
 `tkEventType`  
 [in] Il token per la classe di evento. Si tratta di un `mdTypeDef`, una `mdTypeRef`, o un `mdTokenNil` token.  
  
 `mdAddOn`  
 [in] Il metodo utilizzato per sottoscrivere l'evento, o null.  
  
 `mdRemoveOn`  
 [in] Il metodo utilizzato per annullare la sottoscrizione per l'evento, o null.  
  
 `mdFire`  
 [in] Il metodo utilizzato (da una classe derivata) per generare l'evento.  
  
 `rmdOtherMethods[]`  
 [in] Matrice dei token per gli altri metodi associati all'evento. La matrice viene terminata con un `mdMethodDefNil` token.  
  
 `pmdEvent`  
 [out] Il token di metadati assegnato all'evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
