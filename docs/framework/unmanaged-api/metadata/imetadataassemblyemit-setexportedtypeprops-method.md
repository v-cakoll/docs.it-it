---
title: Metodo IMetaDataAssemblyEmit::SetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
ms.openlocfilehash: dd1d6f1da6e49837eebd9356500f403c199b011b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177858"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a>Metodo IMetaDataAssemblyEmit::SetExportedTypeProps
Modifica la struttura dei metadati `ExportedType` specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ct`  
 [in] Token di metadati `ExportedType` che specifica la struttura dei metadati da modificare.  
  
 `tkImplementation`  
 [in] Token, di `File`tipo `AssemblyRef`, `ExportedType`, o , che specifica la modalità di implementazione di questo tipo.  
  
 `tkTypeDef`  
 [in] Token `TypeDef` a cui viene fatto riferimento nel file di codice.  
  
 `dwExportedTypeFlags`  
 [in] Combinazione bit per bit di valori che specificano attributi del tipo.  
  
## <a name="remarks"></a>Osservazioni  
 Per creare `ExportedType` una struttura dei metadati, utilizzare il metodo [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
