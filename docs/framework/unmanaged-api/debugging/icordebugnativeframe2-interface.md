---
title: Interfaccia ICorDebugNativeFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
ms.openlocfilehash: 22a3f39bc1f9b4e6cad1db4fd0a6480b7c04e8fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792746"
---
# <a name="icordebugnativeframe2-interface"></a>Interfaccia ICorDebugNativeFrame2
Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo IsChild](icordebugnativeframe2-ischild-method.md)|Determina se il frame corrente è un frame figlio.|  
|[Metodo IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md)|Determina se il frame specificato è l'elemento padre del frame corrente.|  
|[Metodo GetStackParameterSize](icordebugnativeframe2-getstackparametersize-method.md)|Restituisce la dimensione cumulativa dei parametri nello stack nei sistemi operativi x86.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia estende logicamente l'interfaccia "ICorDebugNativeFrame".  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
