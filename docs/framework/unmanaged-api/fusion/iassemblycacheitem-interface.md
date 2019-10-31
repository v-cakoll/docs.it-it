---
title: Interfaccia IAssemblyCacheItem
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
ms.openlocfilehash: 2493b5338824e1eab3f82a9023bbcced59a98fc8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134458"
---
# <a name="iassemblycacheitem-interface"></a>Interfaccia IAssemblyCacheItem
Rappresenta un singolo assembly nel Global Assembly Cache.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AbortItem](iassemblycacheitem-abortitem-method.md)|Consente all'assembly nel Global Assembly Cache di eseguire operazioni di pulizia prima del rilascio.|  
|[Metodo Commit](iassemblycacheitem-commit-method.md)|Consente di eseguire il commit del riferimento all'assembly memorizzato nella cache nella memoria.|  
|[Metodo CreateStream](iassemblycacheitem-createstream-method.md)|Crea un flusso con il nome e il formato specificati.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Global Assembly Cache](../../app-domains/gac.md)
- [Interfaccia IAssemblyCache](iassemblycache-interface.md)
