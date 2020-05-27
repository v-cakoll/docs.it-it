---
title: Metodo IMetaDataEmit::SetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: 57f6de1f7edf7c75a3f96cb2bf9fb98fdbd6f65e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007858"
---
# <a name="imetadataemitsetmethodprops-method"></a>Metodo IMetaDataEmit::SetMethodProps
Imposta o aggiorna la funzionalità, archiviata in corrispondenza dell'indirizzo virtuale relativo specificato, di un metodo definito da una chiamata precedente a [IMetaDataEmit::D efinemethod](imetadataemit-definemethod-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a>Parametri  
 `md`  
 in Token per il metodo da modificare.  
  
 `dwMethodFlags`  
 in Attributi del membro.  
  
 `ulCodeRVA`  
 in Indirizzo del codice.  
  
 `dwImplFlags`  
 in Flag di implementazione per il metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
