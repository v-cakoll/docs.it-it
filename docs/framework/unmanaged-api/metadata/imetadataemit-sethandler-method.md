---
title: Metodo IMetaDataEmit::SetHandler
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 4fa227d18b8cb10936d93fda9bcaf413ce63ca3b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003942"
---
# <a name="imetadataemitsethandler-method"></a>Metodo IMetaDataEmit::SetHandler
Imposta il metodo a cui fa riferimento il `IUnknown` puntatore specificato come callback di notifica per i mapping del token.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pUnk`  
 in Gestore da registrare.  
  
## <a name="remarks"></a>Commenti  
 Il motore dei metadati invia una notifica tramite il metodo fornito da `SetHandler` , a compilatori che non generano record in modo ottimizzato e che desiderano ottimizzare i record salvati.  
  
 Se il metodo di callback non viene fornito tramite `SetHandler` , non verrà eseguita alcuna ottimizzazione al salvataggio, tranne nel caso in cui diversi ambiti di importazione siano Stati Uniti utilizzando `IMapToken` il merge per ogni ambito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
