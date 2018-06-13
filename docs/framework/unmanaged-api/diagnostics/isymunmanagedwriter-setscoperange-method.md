---
title: Metodo ISymUnmanagedWriter::SetScopeRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 495089ca33df3b36656da149da45019c30b81d39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428726"
---
# <a name="isymunmanagedwritersetscoperange-method"></a>Metodo ISymUnmanagedWriter::SetScopeRange
Definisce l'intervallo di offset per l'ambito lessicale specificato. L'ambito diventa il nuovo ambito corrente e viene inserito nello stack di ambiti. Gli ambiti devono formare una gerarchia. Elementi di pari livello non è consentiti si sovrappongono.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a>Parametri  
 `scopeId`  
 [in] L'identificatore di ambito per l'ambito.  
  
 `startOffset`  
 [in] L'offset in byte, della prima istruzione nell'ambito lessicale dall'inizio del metodo.  
  
 `endOffset`  
 [in] L'offset in byte, dell'ultima istruzione nell'ambito lessicale dall'inizio del metodo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="remarks"></a>Note  
 [ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere utilizzato con `ISymUnmanagedWriter::SetScopeRange` per definire un ambito dell'offset iniziale e finale in un secondo momento. In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) vengono ignorati. Gli identificatori di ambito sono solo validi nel metodo corrente.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
