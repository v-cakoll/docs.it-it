---
title: Enumerazione CorMethodAttr
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f144426996583d5058f70daed99d8a37cfb6bfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="cormethodattr-enumeration"></a>Enumerazione CorMethodAttr
Contiene valori che descrivono le funzionalità di un metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`mdMemberAccessMask`|Specifica l'accesso ai membri.|  
|`mdPrivateScope`|Specifica che il membro non può far riferimento.|  
|`mdPrivate`|Specifica che il membro è accessibile solo dal tipo padre.|  
|`mdFamANDAssem`|Specifica che il membro è accessibile soltanto i sottotipi in questo assembly.|  
|`mdAssem`|Specifica che il membro è accessibile da qualsiasi utente nell'assembly.|  
|`mdFamily`|Specifica che il membro è accessibile solo dal tipo e sottotipi.|  
|`mdFamORAssem`|Specifica che il membro è accessibile dalle classi derivate e gli altri tipi nell'assembly.|  
|`mdPublic`|Specifica che il membro è accessibile da tutti i tipi con accesso all'ambito.|  
|`mdStatic`|Specifica che il membro è definito come parte del tipo anziché come un membro di un'istanza.|  
|`mdFinal`|Specifica che il metodo non può essere sottoposta a override.|  
|`mdVirtual`|Specifica che il metodo può essere sottoposta a override.|  
|`mdHideBySig`|Specifica che il metodo nasconde dal nome e firma, anziché solo per nome.|  
|`mdVtableLayoutMask`|Specifica il layout di tabella virtuale.|  
|`mdReuseSlot`|Specifica che è possibile riutilizzare lo slot utilizzato per questo metodo in una tabella virtuale. Questa è l'impostazione predefinita.|  
|`mdNewSlot`|Specifica che il metodo ottiene sempre un nuovo slot nella tabella virtuale.|  
|`mdCheckAccessOnOverride`|Specifica che il metodo può essere sostituito dagli stessi tipi a cui è visibile.|  
|`mdAbstract`|Specifica che il metodo non implementato.|  
|`mdSpecialName`|Specifica che il metodo è speciale e che il relativo nome viene descritto come.|  
|`mdPinvokeImpl`|Specifica che l'implementazione del metodo viene inoltrato tramite PInvoke.|  
|`mdUnmanagedExport`|Specifica che il metodo è un metodo gestito esportato in codice non gestito.|  
|`mdReservedMask`|Riservato per uso interno da common language runtime.|  
|`mdRTSpecialName`|Specifica che common language runtime deve verificare la codifica del nome del metodo.|  
|`mdHasSecurity`|Specifica che il metodo dispone di protezione associata.|  
|`mdRequireSecObject`|Specifica che il metodo chiama un altro metodo contenente codice di sicurezza.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
