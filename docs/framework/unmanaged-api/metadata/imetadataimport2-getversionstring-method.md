---
title: Metodo IMetaDataImport2::GetVersionString
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ccf168473c1182e4b7d57d52930d90084eaa2dd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getversionstring-method"></a>Metodo IMetaDataImport2::GetVersionString
Ottiene il numero di versione del runtime che è stato utilizzato per compilare l'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pwzBuf`  
 [out] Una matrice per archiviare la stringa che specifica la versione.  
  
 `ccBufSize`  
 [in] Le dimensioni, in caratteri wide, del `pwzBuf` matrice.  
  
 `pccBufSize`  
 [out] Il numero di caratteri wide, incluso un terminatore null, restituite nel `pwzBuf` matrice.  
  
## <a name="remarks"></a>Note  
 Il `GetVersionString` metodo ottiene la versione compilata per di ambito dei metadati corrente. Se l'ambito non è mai stato salvato, non disporrà di una versione e verrà restituita una stringa vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
