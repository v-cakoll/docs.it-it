---
title: Enumerazione CorDeclSecurity
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
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30fd7ca2cf7962c6cadb43d4d8e3031b59292463
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordeclsecurity-enumeration"></a>Enumerazione CorDeclSecurity
Specifica le azioni relative alla sicurezza che possono essere eseguite con la sicurezza dichiarativa.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`dclActionMask`|Riservato.|  
|`dclActionNil`|Riservato.|  
|`dclRequest`|Riservato.|  
|`dclDemand`|A tutti i chiamanti nella parte superiore dello stack di chiamate deve essere concessa l'autorizzazione specificata dall'oggetto di autorizzazione corrente.|  
|`dclAssert`|Il codice chiamante può accedere alla risorsa identificata dall'oggetto autorizzazioni corrente, anche se i chiamanti nello stack non dispongono dell'autorizzazione per accedere alla risorsa|  
|`dclDeny`|La possibilità di accedere alla risorsa specificata dall'oggetto autorizzazioni corrente viene negata ai chiamanti, anche se essi dispongono dell'autorizzazione per accedervi.|  
|`dclPermitOnly`|È possibile accedere solo alle risorse specificate dall'oggetto di autorizzazione, anche se al codice è stata concessa l'autorizzazione per accedere ad altre risorse.|  
|`dclLinktimeCheck`|Il chiamante immediato è necessario concedere l'autorizzazione specificata per un periodo di tempo specifico.|  
|`dclInheritanceCheck`|La classe derivata eredita un'altra classe o si esegue l'override di un metodo è necessaria disporre dell'autorizzazione specificata.|  
|`dclRequestMinimum`|Il chiamante può richiedere per le autorizzazioni minime necessarie per l'esecuzione di codice. Questa azione può essere usata solo nell'ambito dell'assembly.|  
|`dclRequestOptional`|Il chiamante può richiedere le autorizzazioni aggiuntive facoltative (non necessarie per eseguire). Con questa richiesta viene implicitamente rifiutata ogni altra autorizzazione che non sia stata esplicitamente richiesta. Questa azione può essere usata solo nell'ambito dell'assembly.|  
|`dclRequestRefuse`|Non verrà concessa la richiesta del chiamante per le autorizzazioni utilizzabili in modo improprio. Questa azione può essere usata solo nell'ambito dell'assembly.|  
|`dclPrejitGrant`|Riservato.|  
|`dclPrejitDenied`|Riservato.|  
|`dclNonCasDemand`|Riservato.|  
|`dclNonCasLinkDemand`|È necessario concedere al chiamante diretto l'autorizzazione specificata.|  
|`dclNonCasInheritance`|Riservato.|  
|`dclLinkDemandChoice`|Riservato.|  
|`dclInheritanceDemandChoice`|Riservato.|  
|`dclDemandChoice`|Riservato.|  
|`dclMaximumValue`|Riservato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
