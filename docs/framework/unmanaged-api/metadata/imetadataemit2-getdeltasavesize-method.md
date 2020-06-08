---
title: Metodo IMetaDataEmit2::GetDeltaSaveSize
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
ms.openlocfilehash: 24fe8fd65b36e133b767cd07c8602aa1ea7b9dfc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493110"
---
# <a name="imetadataemit2getdeltasavesize-method"></a>Metodo IMetaDataEmit2::GetDeltaSaveSize
Ottiene un valore che indica qualsiasi modifica alle dimensioni dei metadati risultante dalla sessione di modifica e continuazione corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fSave`  
 in Uno dei valori di [CorSaveSize](corsavesize-enumeration.md) , che indica il livello di precisione desiderato. Per la versione .NET Framework 2,0, questo parametro viene ignorato.  
  
 `pdwSaveSize`  
 out Modifica delle dimensioni dei metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
