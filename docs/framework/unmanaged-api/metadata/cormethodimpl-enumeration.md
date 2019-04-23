---
title: Enumerazione CorMethodImpl
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2138dd32cf39db7b7c8989ba5827178d1a1e46c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117235"
---
# <a name="cormethodimpl-enumeration"></a>Enumerazione CorMethodImpl
Contiene valori che descrivono funzionalità di implementazione dei metodi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`miCodeTypeMask`|Flag che descrivono il tipo di codice.|  
|`miIL`|Specifica che l'implementazione del metodo è Microsoft intermediate language (MSIL).|  
|`miNative`|Specifica che l'implementazione del metodo è nativa.|  
|`miOPTIL`|Specifica che l'implementazione del metodo è implementato in OPTIL.|  
|`miRuntime`|Specifica che l'implementazione del metodo è fornito da common language runtime.|  
|`miManagedMask`|Flag che indicano se il codice sia gestito o meno.|  
|`miUnmanaged`|Specifica che l'implementazione del metodo non gestito.|  
|`miManaged`|Specifica che l'implementazione del metodo è gestita.|  
|`miForwardRef`|Specifica che il metodo è definito. Questo flag viene utilizzato principalmente in scenari di tipo merge.|  
|`miPreserveSig`|Specifica che la firma del metodo non può essere alterata per una conversione di HRESULT.|  
|`miInternalCall`|Riservato per uso interno da common language runtime.|  
|`miSynchronized`|Specifica che il metodo è a thread singolo attraverso il relativo corpo.|  
|`miNoInlining`|Specifica che il metodo non può essere impostato come inline.|  
|`miAggressiveInlining`|Specifica che il metodo deve essere impostato come inline se possibile.|  
|`miNoOptimization`|Specifica che il metodo non deve essere ottimizzato.|  
|`miMaxMethodImplVal`|Il valore massimo valido per un `CorMethodImpl`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
