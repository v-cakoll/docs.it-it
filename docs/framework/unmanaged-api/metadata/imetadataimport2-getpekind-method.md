---
title: Metodo IMetaDataImport2::GetPEKind
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetPEKind
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9fc963f38a845db67bb5b5d377ecabf9a40c359f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getpekind-method"></a>Metodo IMetaDataImport2::GetPEKind
Ottiene un valore che identifica il tipo di codice nel file eseguibile portabile (PE) del file, in genere un file DLL o EXE, definito nell'ambito dei metadati corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pdwPEKind`  
 [out] Un puntatore a un valore di [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumerazione che descrive il file PE.  
  
 `pdwMachine`  
 [out] Puntatore a un valore che identifica l'architettura del computer. Vedere la sezione successiva per i valori possibili.  
  
## <a name="remarks"></a>Note  
 Il valore a cui fa riferimento il `pdwMachine` parametro può essere uno dei seguenti.  
  
|Valore|Architettura del computer|  
|-----------|--------------------------|  
|IMAGE_FILE_MACHINE_I386<br /><br /> 0x014C|x86|  
|IMAGE_FILE_MACHINE_IA64<br /><br /> 0x0200|Intel IPF|  
|IMAGE_FILE_MACHINE_AMD64<br /><br /> 0x8664|x64|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [CorPEKind (enumerazione)](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
