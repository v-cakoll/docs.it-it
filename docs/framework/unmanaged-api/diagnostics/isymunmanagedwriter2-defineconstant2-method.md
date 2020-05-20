---
title: Metodo ISymUnmanagedWriter2::DefineConstant2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
ms.openlocfilehash: 70ee853ff657a75dcc4df1454c4354f9d3f8202f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614721"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="33cce-102">Metodo ISymUnmanagedWriter2::DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="33cce-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="33cce-103">Definisce un nome per un valore costante.</span><span class="sxs-lookup"><span data-stu-id="33cce-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33cce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33cce-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33cce-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="33cce-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="33cce-106">in Nome della costante.</span><span class="sxs-lookup"><span data-stu-id="33cce-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="33cce-107">in Valore della costante.</span><span class="sxs-lookup"><span data-stu-id="33cce-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="33cce-108">in Token di metadati della costante.</span><span class="sxs-lookup"><span data-stu-id="33cce-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33cce-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="33cce-109">Return Value</span></span>  
 <span data-ttu-id="33cce-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="33cce-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33cce-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33cce-111">Requirements</span></span>  
 <span data-ttu-id="33cce-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="33cce-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33cce-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33cce-113">See also</span></span>

- [<span data-ttu-id="33cce-114">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="33cce-114">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="33cce-115">Metodo DefineConstant</span><span class="sxs-lookup"><span data-stu-id="33cce-115">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)
