---
title: Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
ms.openlocfilehash: 91ef9eaa855ed841bc75bfaeead462f045eb1d8b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007455"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a>Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo
Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pITI`  
 in Puntatore a un'interfaccia [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) che fornisce le informazioni sul tipo su cui aprire l'ambito.  
  
 `dwOpenFlags`  
 in Flag della modalità di apertura.  
  
 `riid`  
 in Interfaccia desiderata.  
  
 `ppIUnk`  
 out Puntatore a un puntatore all'interfaccia restituita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataDispenser](imetadatadispenser-interface.md)
