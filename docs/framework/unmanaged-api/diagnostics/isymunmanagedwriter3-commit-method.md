---
title: Metodo ISymUnmanagedWriter3::Commit
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.Commit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type:
- apiref
ms.openlocfilehash: 4331728a4766d81b723c439747e5e1181815394f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614669"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="e7cbb-102">Metodo ISymUnmanagedWriter3::Commit</span><span class="sxs-lookup"><span data-stu-id="e7cbb-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="e7cbb-103">Consente di eseguire il commit delle modifiche scritte finora nel flusso.</span><span class="sxs-lookup"><span data-stu-id="e7cbb-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7cbb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7cbb-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e7cbb-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e7cbb-105">Return Value</span></span>  
 <span data-ttu-id="e7cbb-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e7cbb-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7cbb-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7cbb-107">Requirements</span></span>  
 <span data-ttu-id="e7cbb-108">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e7cbb-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7cbb-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7cbb-109">See also</span></span>

- [<span data-ttu-id="e7cbb-110">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="e7cbb-110">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
