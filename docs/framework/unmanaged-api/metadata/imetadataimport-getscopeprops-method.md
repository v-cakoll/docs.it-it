---
title: Metodo IMetaDataImport::GetScopeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: 0916b6382bb9352616d85e21f423301dc6aa9fa9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490848"
---
# <a name="imetadataimportgetscopeprops-method"></a>Metodo IMetaDataImport::GetScopeProps
Ottiene il nome ed eventualmente l'identificatore di versione dell'assembly o del modulo nell'ambito dei metadati corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szName`  
 out Buffer per il nome dell'assembly o del modulo.  
  
 `cchName`  
 in Dimensioni in caratteri wide di `szName` .  
  
 `pchName`  
 out Numero di caratteri wide restituiti in `szName` .  
  
 `pmvid`  
 [out, facoltativo] Puntatore a un GUID che identifica in modo univoco la versione dell'assembly o del modulo.  
  
## <a name="remarks"></a>Osservazioni  
 Per impostare queste proprietà, viene usato il metodo [IMetaDataEmit:: SetModuleProps](imetadataemit-setmoduleprops-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
