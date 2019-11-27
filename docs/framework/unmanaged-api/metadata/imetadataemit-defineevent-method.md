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
ms.openlocfilehash: 6966d0ad2fefd8401b19d8e8dcf7776799a066b2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432559"
---
# <a name="imetadataemitdefineevent-method"></a>Metodo IMetaDataEmit::DefineEvent
Crea una definizione per un evento con la firma dei metadati specificata e ottiene un token per la definizione dell'evento.  
  
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
 in Token per la classe o l'interfaccia di destinazione. Si tratta di un token `mdTypeDef` o `mdTypeDefNil`.  
  
 `szEvent`  
 in Nome dell'evento.  
  
 `dwEventFlags`  
 in Flag evento.  
  
 `tkEventType`  
 in Token per la classe di evento. Si tratta di un `mdTypeDef`, un `mdTypeRef`o un token di `mdTokenNil`.  
  
 `mdAddOn`  
 in Metodo utilizzato per sottoscrivere l'evento o null.  
  
 `mdRemoveOn`  
 in Metodo utilizzato per annullare la sottoscrizione dell'evento o null.  
  
 `mdFire`  
 in Metodo usato (da una classe derivata) per generare l'evento.  
  
 `rmdOtherMethods[]`  
 in Matrice di token per altri metodi associati all'evento. La matrice viene terminata con un token di `mdMethodDefNil`.  
  
 `pmdEvent`  
 out Token di metadati assegnato all'evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
