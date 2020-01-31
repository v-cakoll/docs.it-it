---
title: Metodo ICLRDataTarget::GetPointerSize
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
ms.openlocfilehash: 7a274aaec4919b86f32f98e4d8278dc12748fb2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785484"
---
# <a name="iclrdatatargetgetpointersize-method"></a>Metodo ICLRDataTarget::GetPointerSize
Ottiene la dimensione, in byte, del tipo di puntatore utilizzato dal processo di destinazione. Questo metodo viene chiamato dal servizio di accesso ai dati Common Language Runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pointerSize`  
 out Puntatore a un valore integer che specifica la dimensione, in byte, di un puntatore nel processo di destinazione.  
  
## <a name="remarks"></a>Note  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget](iclrdatatarget-interface.md)
