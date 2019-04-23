---
title: Metodo IBindingDisplay::InitializeForProcess
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa1e85751f90c34d40e88207af5c7eed2dd1bb82
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197875"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a>Metodo IBindingDisplay::InitializeForProcess
Inizializza la [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pid`  
 [in] L'identificatore di processo.  
  
## <a name="remarks"></a>Note  
 Il debugger chiama il `InitializeForProcess` metodo in fase di creazione per inizializzare la visualizzazione delle associazioni. `InitializeForProcess` deve essere chiamato in fase di creazione della prima di qualsiasi altro metodo su `IBindingDisplay` viene chiamato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** BindingDisplay.h  
  
 **Libreria:** BindingDisplay.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
