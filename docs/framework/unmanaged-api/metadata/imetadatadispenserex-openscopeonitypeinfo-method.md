---
title: Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a0838895870370e3003aac4967a535b44c8e7943
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a>Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo
Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pITI`  
 [in] Puntatore a un [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) interfaccia che fornisce le informazioni sul tipo in cui aprire l'ambito.  
  
 `dwOpenFlags`  
 [in] I flag della modalità di apertura.  
  
 `riid`  
 [in] L'interfaccia desiderata.  
  
 `ppIUnk`  
 [out] Puntatore a un puntatore all'interfaccia restituita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataDispenserEx (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
