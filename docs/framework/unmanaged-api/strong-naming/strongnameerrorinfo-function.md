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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 021fa1668247bc59a4412d2b5f4bac3f5ee8cc6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799109"
---
# <a name="strongnameerrorinfo-function"></a>Funzione StrongNameErrorInfo
Ottiene l'ultimo codice di errore che è stato generato da una delle funzioni con nome sicuro.  
  
 Questa funzione è stata deprecata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>Valore restituito  
 Ultimo codice di errore COM impostato da una delle funzioni con nome sicuro.  
  
## <a name="remarks"></a>Note  
 La maggior parte dei metodi con nome sicuro restituisce `true` una `false` semplice o un'indicazione del completamento corretto. Utilizzare la `StrongNameErrorInfo` funzione per recuperare un valore HRESULT che specifica l'ultimo errore generato dalle funzioni con nome sicuro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
