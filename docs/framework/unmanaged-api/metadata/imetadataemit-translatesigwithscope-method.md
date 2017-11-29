---
title: Metodo IMetaDataEmit::TranslateSigWithScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.TranslateSigWithScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5127defc97423283b52b7b5bd8c6b7a31104fbc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemittranslatesigwithscope-method"></a>Metodo IMetaDataEmit::TranslateSigWithScope
Importa un assembly nell'ambito corrente e ottiene una nuova firma dei metadati per l'ambito unito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pAssemImport`  
 [in] L'interfaccia per importare l'assembly (in cui è definita la firma).  
  
 `pbHashValue`  
 [in] Il blob hash per l'assembly.  
  
 `cbHashValue`  
 [in] Il numero di byte in `pbHashValue`.  
  
 `import`  
 [in] L'interfaccia per l'ambito di importazione dei metadati.  
  
 `pbSigBlob`  
 [in] Firma da importare.  
  
 `cbSigBlob`  
 [in] Le dimensioni, in byte, di `pbSigBlob`.  
  
 `pAssemEmit`  
 [in] L'interfaccia per esportare l'assembly.  
  
 `emit`  
 [in] L'interfaccia per l'ambito dei metadati di esportazione.  
  
 `pvTranslatedSig`  
 [out] Il buffer contenente il BLOB della firma convertita.  
  
 `cbTranslatedSigMax`  
 [in] La capacità, in byte, di `pvTranslatedSig`.  
  
 `pcbTranslatedSig`  
 [out] Il numero di byte effettivi nella firma convertita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [IMetaDataAssemblyImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
