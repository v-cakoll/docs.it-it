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
ms.openlocfilehash: 204e5660e95434f8d0c44d54f4fdbb1c2acc1e5d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777778"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>Metodo IMetaDataDispenser::OpenScopeOnMemory
Apre un'area di memoria che contiene i metadati esistenti. Vale a dire, questo metodo consente di aprire un'area specificata di memoria in cui i dati esistenti viene considerati come metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pData`  
 [in] Un puntatore che specifica l'indirizzo iniziale dell'area di memoria.  
  
 `cbData`  
 [in] Le dimensioni dell'area di memoria, espressa in byte.  
  
 `dwOpenFlags`  
 [in] Valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione per specificare la modalità (lettura, scrittura e così via) per l'apertura.  
  
 `riid`  
 [in] IID dell'interfaccia di metadati desiderati da restituire. il chiamante Usa l'interfaccia per importare (lettura) o la creazione dei metadati (scrittura).  
  
 Il valore di `riid` deve specificare una delle interfacce "import" o "Crea". I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 IID_IMetaDataAssemblyEmit IID_IMetaDataImport2.  
  
 `ppIUnk`  
 [out] Il puntatore all'interfaccia restituita.  
  
## <a name="remarks"></a>Note  
 La copia in memoria dei metadati è possibile eseguire query utilizzando i metodi di una delle interfacce "import" o aggiunti utilizzando i metodi di una delle interfacce di "generazione".  
  
 Il `OpenScopeOnMemory` metodo è simile al [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) metodo, ad eccezione del fatto che i metadati di interesse esistono già in memoria, anziché in un file su disco.  
  
 Se l'area di destinazione di memoria non contiene metadati di common language runtime (CLR), il `OpenScopeOnMemory` metodo avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
