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
ms.openlocfilehash: 60c9266806ef6b5d7e2e1c3a219a4485bc22d7f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445520"
---
# <a name="imetadataemitsethandler-method"></a>Metodo IMetaDataEmit::SetHandler
Imposta il metodo a cui fa riferimento specificato `IUnknown` puntatore come un callback di notifica per i nuovi mapping token.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pUnk`  
 [in] Gestore da registrare.  
  
## <a name="remarks"></a>Note  
 Il motore dei metadati invia notifica tramite il metodo che viene fornito da `SetHandler`, per i compilatori che non generano record in modo ottimizzato e che si desidera ottimizzare i record salvati.  
  
 Se il metodo di callback non viene fornito tramite `SetHandler`, verrà eseguita alcuna ottimizzazione su Salva tranne diversi in cui importare gli ambiti vengono uniti utilizzando `IMapToken` merge per ogni ambito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
