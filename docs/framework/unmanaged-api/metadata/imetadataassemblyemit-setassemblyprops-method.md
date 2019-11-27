---
title: Metodo IMetaDataAssemblyEmit::SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: f79320d5b7d2ad4ad44a79fae063ce6718490a70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431958"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>Metodo IMetaDataAssemblyEmit::SetAssemblyProps
Modifica la struttura dei metadati `Assembly` specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pma`  
 in Token di metadati che specifica la struttura dei metadati `Assembly` da modificare.  
  
 `pbPublicKey`  
 in Puntatore alla chiave pubblica del server di pubblicazione dell'assembly.  
  
 `cbPublicKey`  
 in Dimensioni in byte del `pbPublicKey`.  
  
 `ulHashAlgId`  
 in Identificatore dell'algoritmo hash utilizzato per eseguire l'hashing dei file di assembly.  
  
 `szName`  
 in Nome di testo leggibile dell'assembly.  
  
 `pMetaData`  
 in Puntatore a ASSEMBLYMETADATA che contiene le informazioni sulla versione, sulla piattaforma e sulle impostazioni locali per l'assembly.  
  
 `dwAssemblyFlags`  
 in Combinazione bit per bit di valori [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) che specificano diversi attributi dell'assembly.  
  
## <a name="remarks"></a>Osservazioni  
 Per creare una struttura di metadati `Assembly`, usare il metodo [IMetaDataAssemblyEmit::D efineassembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
