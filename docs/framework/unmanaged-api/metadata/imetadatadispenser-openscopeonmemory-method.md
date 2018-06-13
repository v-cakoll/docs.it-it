---
title: Metodo IMetaDataDispenser::OpenScopeOnMemory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f184c04db384c2b9bdbce2d8ae6919c05a2ab425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448895"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>Metodo IMetaDataDispenser::OpenScopeOnMemory
Verrà visualizzata un'area di memoria che contiene i metadati esistenti. Vale a dire, questo metodo apre un'area specificata di memoria in cui i dati esistenti viene trattati come metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pData`  
 [in] Un puntatore che specifica l'indirizzo iniziale dell'area di memoria.  
  
 `cbData`  
 [in] Le dimensioni dell'area di memoria, in byte.  
  
 `dwOpenFlags`  
 [in] Il valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione per specificare la modalità (lettura, scrittura e così via) di apertura.  
  
 `riid`  
 [in] L'IID dell'interfaccia di metadati desiderati da restituire. il chiamante utilizzerà l'interfaccia per l'importazione (lettura) o la creazione dei metadati (scrittura).  
  
 Il valore di `riid` deve specificare una delle interfacce "import" o "generazione". I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 IID_IMetaDataAssemblyEmit IID_IMetaDataImport2.  
  
 `ppIUnk`  
 [out] Puntatore all'interfaccia restituita.  
  
## <a name="remarks"></a>Note  
 La copia in memoria dei metadati è possibile eseguire query utilizzando i metodi di una delle interfacce "import" o aggiunti utilizzando i metodi di una delle interfacce di "generazione".  
  
 Il `OpenScopeOnMemory` è simile al metodo di [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) (metodo), ad eccezione del fatto che i metadati di interesse esistono già in memoria, piuttosto che in un file su disco.  
  
 Se l'area di destinazione di memoria non contiene metadati di common language runtime (CLR), il `OpenScopeOnMemory` metodo avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
