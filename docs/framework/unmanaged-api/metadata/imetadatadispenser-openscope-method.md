---
title: Metodo IMetaDataDispenser::OpenScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5b94987631f7dbbe39e585a8ea2c2252b9427613
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050168"
---
# <a name="imetadatadispenseropenscope-method"></a>Metodo IMetaDataDispenser::OpenScope
Apre un file esistente su disco e viene eseguito il mapping dei metadati in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szScope`  
 [in] Il nome del file da aprire. Il file deve contenere metadati di common language runtime (CLR).  
  
 `dwOpenFlags`  
 [in] Valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione per specificare la modalità (lettura, scrittura e così via) per l'apertura.  
  
 `riid`  
 [in] IID dell'interfaccia di metadati desiderati da restituire. il chiamante Usa l'interfaccia per importare (lettura) o la creazione dei metadati (scrittura).  
  
 Il valore di `riid` deve specificare una delle interfacce "import" o "Crea". I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 IID_IMetaDataAssemblyEmit IID_IMetaDataImport2.  
  
 `ppIUnk`  
 [out] Il puntatore all'interfaccia restituita.  
  
## <a name="remarks"></a>Note  
 La copia in memoria dei metadati è possibile eseguire query utilizzando i metodi di una delle interfacce "import" o aggiunti utilizzando i metodi di una delle interfacce di "generazione".  
  
 Se il file di destinazione non contiene metadati CLR, il `OpenScope` metodo avrà esito negativo.  
  
 In .NET Framework versione 1.0 e 1.1, se un ambito viene aperto con `dwOpenFlags` impostata su ofRead, è idoneo per la condivisione. Vale a dire, se i successivi le chiamate a `OpenScope` passare il nome di un file che è stato precedentemente aperto, viene riutilizzato l'ambito esistente e non viene creato un nuovo set di strutture di dati. Tuttavia, possono verificarsi problemi a causa di questa condivisione.  
  
 In .NET Framework versione 2.0, gli ambiti di aperta con `dwOpenFlags` impostato su ofRead non sono più condivisi. Usare il valore di ofReadOnly per consentire l'ambito da condividere. Quando viene condiviso un ambito, le query che usano "lettura/scrittura" interfacce di metadati avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
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
