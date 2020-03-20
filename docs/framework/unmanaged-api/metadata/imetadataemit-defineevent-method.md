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
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175850"
---
# <a name="imetadataemitdefineevent-method"></a>Metodo IMetaDataEmit::DefineEvent
Crea una definizione per un evento con la firma dei metadati specificata e ottiene un token per tale definizione di evento.  
  
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
 [in] Token per la classe o l'interfaccia di destinazione. Si tratta `mdTypeDef` di `mdTypeDefNil` un o token.  
  
 `szEvent`  
 [in] Nome dell'evento.  
  
 `dwEventFlags`  
 [in] Flag di evento.  
  
 `tkEventType`  
 [in] Token per la classe di evento. Si tratta `mdTypeDef`di `mdTypeRef`un, `mdTokenNil` un oggetto o un token.  
  
 `mdAddOn`  
 [in] Metodo utilizzato per sottoscrivere l'evento o null.  
  
 `mdRemoveOn`  
 [in] Metodo utilizzato per annullare la sottoscrizione all'evento o null.  
  
 `mdFire`  
 [in] Metodo utilizzato (da una classe derivata) per generare l'evento.  
  
 `rmdOtherMethods[]`  
 [in] Matrice di token per altri metodi associati all'evento. La matrice viene terminata con un `mdMethodDefNil` token.  
  
 `pmdEvent`  
 [fuori] Token di metadati assegnato all'evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
