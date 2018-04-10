---
title: Metodo IAssemblyCacheItem::CreateStream
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 726efe69f67627c48108b6b1ece9fe52f34a91c1
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="iassemblycacheitemcreatestream-method"></a>Metodo IAssemblyCacheItem::CreateStream
Crea un flusso con il nome specificato e il formato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateStream (  
    [in]  DWORD dwFlags,  
    [in]  LPCWSTR pszStreamName,  
    [in]  DWORD dwFormat,  
    [in]  DWORD dwFormatFlags,  
    [out] IStream **ppIStream,  
    [in, optional] ULARGE_INTEGER *puliMaxSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwFlags`  
 [in] Flag definiti in Fusion.  
  
 `pszStreamName`  
 [in] Il nome del flusso da creare.  
  
 `dwFormat`  
 [in] Il formato del file da trasmettere.  
  
 `dwFormatFlags`  
 [in] Flag specifici del formato definito in Fusion.  
  
 `ppIStream`  
 [out] Un puntatore all'indirizzo dell'oggetto restituito [IStream](https://msdn.microsoft.com/library/aa380034.aspx) istanza.  
  
 `puliMaxSize`  
 [in, facoltativo] La dimensione massima del flusso a cui fa riferimento `ppIStream`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
