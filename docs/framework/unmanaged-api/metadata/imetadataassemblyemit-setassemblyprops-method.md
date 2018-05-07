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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f8132296035e9ddcdcad76d93ed05358beb0b81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>Metodo IMetaDataAssemblyEmit::SetAssemblyProps
Modifica la struttura dei metadati `Assembly` specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `pma`  
 [in] Il token di metadati che specifica il `Assembly` struttura dei metadati da modificare.  
  
 `pbPublicKey`  
 [in] Puntatore alla chiave pubblica del server di pubblicazione dell'assembly.  
  
 `cbPublicKey`  
 [in] Le dimensioni in byte di `pbPublicKey`.  
  
 `ulHashAlgId`  
 [in] Identificatore per l'algoritmo hash utilizzato per i file di assembly di hash.  
  
 `szName`  
 [in] Il nome di un testo leggibile dell'assembly.  
  
 `pMetaData`  
 [in] Puntatore a ASSEMBLYMETADATA che contiene informazioni sulla versione, piattaforma e delle impostazioni locali per l'assembly.  
  
 `dwAssemblyFlags`  
 [in] Combinazione bit per bit di [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) valori che specificano vari attributi dell'assembly.  
  
## <a name="remarks"></a>Note  
 Per creare un `Assembly` struttura dei metadati, usare il [IMetaDataAssemblyEmit:: DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
