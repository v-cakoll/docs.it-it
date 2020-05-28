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
ms.openlocfilehash: 7ef6dbc46806febc6fba89b39a8b894377225c23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003966"
---
# <a name="imetadataemittranslatesigwithscope-method"></a>Metodo IMetaDataEmit::TranslateSigWithScope
Importa un assembly nell'ambito corrente e ottiene una nuova firma dei metadati per l'ambito Unito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Interfaccia per l'assembly di importazione (in cui è definita la firma).  
  
 `pbHashValue`  
 in Blob hash per l'assembly.  
  
 `cbHashValue`  
 in Numero di byte in `pbHashValue` .  
  
 `import`  
 in Interfaccia per l'ambito dell'importazione dei metadati.  
  
 `pbSigBlob`  
 in Firma da importare.  
  
 `cbSigBlob`  
 in Dimensione, in byte, di `pbSigBlob` .  
  
 `pAssemEmit`  
 in Interfaccia per l'esportazione dell'assembly.  
  
 `emit`  
 in Interfaccia per l'ambito di esportazione dei metadati.  
  
 `pvTranslatedSig`  
 out Buffer in cui memorizzare il BLOB di firma tradotto.  
  
 `cbTranslatedSigMax`  
 in Capacità, in byte, di `pvTranslatedSig` .  
  
 `pcbTranslatedSig`  
 out Numero di byte effettivi nella firma tradotta.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
