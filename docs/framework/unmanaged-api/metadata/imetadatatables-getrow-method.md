---
title: Metodo IMetaDataTables::GetRow
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetRow
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 281824ace7696ab0fc6b3a96e0cdf307a9419313
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetrow-method"></a>Metodo IMetaDataTables::GetRow
Ottiene la riga in corrispondenza dell'indice di riga specificata, nella tabella in corrispondenza dell'indice di tabella specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ixTbl`  
 [in] Indice della tabella da cui verrà recuperata la riga.  
  
 `rid`  
 [in] Indice della riga da ottenere.  
  
 `ppRow`  
 [out] Un puntatore a un puntatore alla riga.  
  
## <a name="remarks"></a>Note  
 Non è consigliabile l'utilizzo di questo metodo, perché non restituisce risultati coerenti. Per informazioni sulla tabella dei GUID, vedere la documentazione di Common Language Infrastructure (CLI), in particolare "partizione II: metadati definizione e la semantica". La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataTables (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [IMetaDataTables2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
