---
title: Metodo IMetaDataEmit::TranslateSigWithScope
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71029d6ebfb3248da791d4371dfe3e39589af443
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207643"
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
  
## <a name="parameters"></a>Parametri  
 `pAssemImport`  
 [in] L'interfaccia per importare l'assembly (in cui è definita la firma).  
  
 `pbHashValue`  
 [in] Il blob di hash per l'assembly.  
  
 `cbHashValue`  
 [in] Il numero di byte in `pbHashValue`.  
  
 `import`  
 [in] L'interfaccia per l'ambito dei metadati di importazione.  
  
 `pbSigBlob`  
 [in] La firma da importare.  
  
 `cbSigBlob`  
 [in] Le dimensioni, in byte, di `pbSigBlob`.  
  
 `pAssemEmit`  
 [in] L'interfaccia per esportare l'assembly.  
  
 `emit`  
 [in] L'interfaccia per l'ambito dei metadati di esportazione.  
  
 `pvTranslatedSig`  
 [out] Il buffer per mantenere il blob della firma tradotti.  
  
 `cbTranslatedSigMax`  
 [in] La capacità, in byte, di `pvTranslatedSig`.  
  
 `pcbTranslatedSig`  
 [out] Il numero di byte effettivi nella firma tradotto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
