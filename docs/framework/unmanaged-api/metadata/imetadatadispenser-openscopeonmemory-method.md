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
ms.openlocfilehash: 69e5e05012d2b44a76a986591ec990f66bf8ae20
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007325"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>Metodo IMetaDataDispenser::OpenScopeOnMemory
Apre un'area di memoria contenente i metadati esistenti. Questo metodo apre un'area di memoria specificata in cui i dati esistenti vengono considerati come metadati.  
  
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
 in Puntatore che specifica l'indirizzo iniziale dell'area di memoria.  
  
 `cbData`  
 in Dimensioni in byte dell'area di memoria.  
  
 `dwOpenFlags`  
 in Valore dell'enumerazione [CorOpenFlags](coropenflags-enumeration.md) per specificare la modalità (lettura, scrittura e così via) per l'apertura.  
  
 `riid`  
 in IID dell'interfaccia di metadati desiderata da restituire. il chiamante utilizzerà l'interfaccia per importare (leggere) o creare (scrivere) metadati.  
  
 Il valore di `riid` deve specificare una delle interfacce "Import" o "Emit". I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.  
  
 `ppIUnk`  
 out Puntatore all'interfaccia restituita.  
  
## <a name="remarks"></a>Commenti  
 La copia in memoria dei metadati può essere sottoposta a query usando i metodi di una delle interfacce di "importazione" oppure aggiunti a usando i metodi di una delle interfacce "Emit".  
  
 Il `OpenScopeOnMemory` metodo è simile al metodo [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) , ad eccezione del fatto che i metadati di interesse sono già presenti in memoria, anziché in un file su disco.  
  
 Se l'area di destinazione della memoria non contiene metadati di Common Language Runtime (CLR), il `OpenScopeOnMemory` metodo avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenser](imetadatadispenser-interface.md)
- [Interfaccia IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
