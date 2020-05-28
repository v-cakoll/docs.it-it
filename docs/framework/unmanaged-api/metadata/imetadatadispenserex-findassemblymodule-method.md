---
title: Metodo IMetaDataDispenserEx::FindAssemblyModule
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
ms.openlocfilehash: 64f1e2a8f05616c7ca84bc130428629b1176e985
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006181"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a>Metodo IMetaDataDispenserEx::FindAssemblyModule
Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
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
 in Nome del modulo.  
  
 `szModuleName`  
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
