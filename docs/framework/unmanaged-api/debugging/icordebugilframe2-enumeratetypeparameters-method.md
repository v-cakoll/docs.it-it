---
title: Metodo ICorDebugILFrame2::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a0c23c066a6f704c4dfcfbe254e91ab3bc5817e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416241"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="fb5c7-102">Metodo ICorDebugILFrame2::EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="fb5c7-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="fb5c7-103">Ottiene un oggetto ICorDebugTypeEnum che contiene il <xref:System.Type> parametri in questo frame.</span><span class="sxs-lookup"><span data-stu-id="fb5c7-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb5c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb5c7-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb5c7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fb5c7-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="fb5c7-106">Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugTypeEnum che consente l'enumerazione dei parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="fb5c7-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="fb5c7-107">L'elenco di parametri di tipo include i parametri di tipo classe (se presente) seguiti dai parametri di tipo metodo (se presente).</span><span class="sxs-lookup"><span data-stu-id="fb5c7-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb5c7-108">Note</span><span class="sxs-lookup"><span data-stu-id="fb5c7-108">Remarks</span></span>  
 <span data-ttu-id="fb5c7-109">Utilizzare il [Imetadataimport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) metodo per determinare il numero di parametri di tipo classe e metodo contiene l'elenco di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="fb5c7-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="fb5c7-110">I parametri di tipo non sono sempre disponibili.</span><span class="sxs-lookup"><span data-stu-id="fb5c7-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb5c7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fb5c7-111">Requirements</span></span>  
 <span data-ttu-id="fb5c7-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb5c7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb5c7-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="fb5c7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb5c7-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fb5c7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb5c7-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb5c7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
