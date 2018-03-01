---
title: Metodo ICeeGen::AddSectionReloc
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
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e4bb3b1e436f51726ce50f80e1fd88c10f20fd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iceegenaddsectionreloc-method"></a>Metodo ICeeGen::AddSectionReloc
Aggiunge un'istruzione. reloc alla base di codice.  
  
 Questo metodo è obsoleto e non deve essere utilizzato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `section`  
 [in] La sezione di codice in memoria a cui aggiungere un'istruzione. reloc.  
  
 `offset`  
 [in] L'offset della sezione.  
  
 `relativeTo`  
 [in] La sezione in cui `offset` fa riferimento.  
  
 `relocType`  
 [in] Uno del [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) valori, che indica il tipo di istruzione. reloc da aggiungere.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
