---
title: Metodo IMetaDataDispenserEx::FindAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
ms.openlocfilehash: 50aebb09924b93a622e5b7d84e65e41ee91f6018
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006194"
---
# <a name="imetadatadispenserexfindassembly-method"></a>Metodo IMetaDataDispenserEx::FindAssembly
Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szAppBase`  
 [in] Non utilizzato.  
  
 `szPrivateBin`  
 [in] Non utilizzato.  
  
 `szGlobalBin`  
 [in] Non utilizzato.  
  
 `szAssemblyName`  
 in Assembly da trovare.  
  
 `szName`  
 out Nome semplice dell'assembly.  
  
 `cchName`  
 in Dimensione, in byte, di `szName` .  
  
 `pcName`  
 out Numero di caratteri effettivamente restituiti in `szName` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataDispenser](imetadatadispenser-interface.md)
