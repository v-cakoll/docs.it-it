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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e4be840760782789aa91e5519f60374aca2e3941
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775255"
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
 [in] Il token di metadati che specifica il `ExportedType` modifica della struttura dei metadati.  
  
 `tkImplementation`  
 [in] Il token, di tipo `File`, `AssemblyRef`, o `ExportedType`, che specifica la modalità di implementazione di questo tipo.  
  
 `tkTypeDef`  
 [in] Il `TypeDef` token di cui viene fatto riferimento nel file di codice.  
  
 `dwExportedTypeFlags`  
 [in] Combinazione bit per bit dei valori che specificano gli attributi del tipo.  
  
## <a name="remarks"></a>Note  
 Per creare un `ExportedType` struttura dei metadati, usare il [DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
