---
title: Funzione StrongNameErrorInfo
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
ms.openlocfilehash: d5eedc34b75d3a0c02969c06454b0f7ec942ed17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176942"
---
# <a name="strongnameerrorinfo-function"></a>Funzione StrongNameErrorInfo
Ottiene l'ultimo codice di errore che è stato generato da una delle funzioni con nome sicuro.  
  
 Questa funzione è deprecata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StrongNameErrorInfo ();
```  
  
## <a name="return-value"></a>Valore restituito  
 L'ultimo codice di errore COM impostato da una delle funzioni con nome sicuro.  
  
## <a name="remarks"></a>Osservazioni  
 La maggior parte dei metodi `true` `false` con nome sicuro restituisce una semplice o un'indicazione di completamento corretto. Utilizzare `StrongNameErrorInfo` la funzione per recuperare un HRESULT che specifica l'ultimo errore generato dalle funzioni con nome sicuro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** NomeForte.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
