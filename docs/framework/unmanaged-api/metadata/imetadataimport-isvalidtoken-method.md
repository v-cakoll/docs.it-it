---
title: Metodo IMetaDataImport::IsValidToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: 9190d021b801be951d214406dde7e6d76da15608
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503438"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="5eb60-102">Metodo IMetaDataImport::IsValidToken</span><span class="sxs-lookup"><span data-stu-id="5eb60-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="5eb60-103">Ottiene un valore che indica se il token specificato contiene un riferimento valido a un oggetto codice.</span><span class="sxs-lookup"><span data-stu-id="5eb60-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5eb60-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5eb60-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5eb60-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5eb60-106">in Token per il quale verificare la validità del riferimento.</span><span class="sxs-lookup"><span data-stu-id="5eb60-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5eb60-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5eb60-107">Return Value</span></span>  
 <span data-ttu-id="5eb60-108">`true`Se `tk` è un token di metadati valido nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="5eb60-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="5eb60-109">In caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="5eb60-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eb60-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5eb60-110">Requirements</span></span>  
 <span data-ttu-id="5eb60-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5eb60-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eb60-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5eb60-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5eb60-113">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5eb60-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5eb60-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eb60-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb60-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5eb60-115">See also</span></span>

- [<span data-ttu-id="5eb60-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5eb60-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5eb60-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5eb60-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
