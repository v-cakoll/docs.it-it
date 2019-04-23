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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac0e5db4a87b49d631bad4411f03fae8c1199aea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125632"
---
# <a name="imetadataemitsethandler-method"></a>Metodo IMetaDataEmit::SetHandler
Imposta il metodo specificato fa riferimento `IUnknown` puntatore come un callback di notifica per riassegnazioni di token.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pUnk`  
 [in] Il gestore da registrare.  
  
## <a name="remarks"></a>Note  
 Il motore di metadati invia notifica tramite il metodo che viene fornito da `SetHandler`, per i compilatori che non generano record in modo ottimizzato e che desiderano ottimizzare registra salvato.  
  
 Se il metodo di callback non viene fornito attraverso `SetHandler`, verrà eseguita alcuna ottimizzazione nel salvataggio tranne diversi in cui importare gli ambiti sono stati uniti usando `IMapToken` merge per ogni ambito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
