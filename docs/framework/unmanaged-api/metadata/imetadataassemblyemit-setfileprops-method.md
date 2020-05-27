---
title: Metodo IMetaDataAssemblyEmit::SetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 9990daea1b097532de53684921d3f10c520a3b1a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008066"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a>Metodo IMetaDataAssemblyEmit::SetFileProps
Modifica la struttura dei metadati `File` specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `file`  
 in Token di metadati che specifica la `File` struttura dei metadati da modificare.  
  
 `pbHashValue`  
 in Puntatore ai dati hash associati al file.  
  
 `cbHashValue`  
 in Dimensioni in byte di `pbHashValue` .  
  
 `dwFileFlags`  
 in Combinazione bit per bit di valori [CorFileFlags](corfileflags-enumeration.md) che specificano diversi attributi del file.  
  
## <a name="remarks"></a>Commenti  
 Per creare una `File` struttura di metadati, usare il metodo [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
