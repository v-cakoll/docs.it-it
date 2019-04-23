---
title: Metodo IMetaDataImport2::GetPEKind
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9dda1fb38546138d52b5fe61754d5497e676c37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113486"
---
# <a name="imetadataimport2getpekind-method"></a>Metodo IMetaDataImport2::GetPEKind
Ottiene un valore che identifica la natura del codice nel file eseguibile portabile (PE) di file, in genere un file DLL o EXE, definito nell'ambito dei metadati corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pdwPEKind`  
 [out] Un puntatore a un valore di [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumerazione che descrive il file PE.  
  
 `pdwMachine`  
 [out] Puntatore a un valore che identifica l'architettura del computer. Vedere la sezione successiva per i valori possibili.  
  
## <a name="remarks"></a>Note  
 Il valore a cui fanno riferimento le `pdwMachine` parametro può essere uno dei valori seguenti.  
  
|Value|Architettura del computer|  
|-----------|--------------------------|  
|IMAGE_FILE_MACHINE_I386<br /><br /> 0x014C|x86|  
|IMAGE_FILE_MACHINE_IA64<br /><br /> 0x0200|Intel IPF|  
|IMAGE_FILE_MACHINE_AMD64<br /><br /> 0x8664|X64|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Enumerazione CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
