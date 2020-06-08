---
title: Metodo IMetaDataImport::GetScopeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: 0916b6382bb9352616d85e21f423301dc6aa9fa9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490848"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="2c346-102">Metodo IMetaDataImport::GetScopeProps</span><span class="sxs-lookup"><span data-stu-id="2c346-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="2c346-103">Ottiene il nome ed eventualmente l'identificatore di versione dell'assembly o del modulo nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="2c346-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c346-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c346-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c346-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c346-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="2c346-106">out Buffer per il nome dell'assembly o del modulo.</span><span class="sxs-lookup"><span data-stu-id="2c346-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2c346-107">in Dimensioni in caratteri wide di `szName` .</span><span class="sxs-lookup"><span data-stu-id="2c346-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="2c346-108">out Numero di caratteri wide restituiti in `szName` .</span><span class="sxs-lookup"><span data-stu-id="2c346-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="2c346-109">[out, facoltativo] Puntatore a un GUID che identifica in modo univoco la versione dell'assembly o del modulo.</span><span class="sxs-lookup"><span data-stu-id="2c346-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c346-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2c346-110">Remarks</span></span>  
 <span data-ttu-id="2c346-111">Per impostare queste proprietà, viene usato il metodo [IMetaDataEmit:: SetModuleProps](imetadataemit-setmoduleprops-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2c346-111">The [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c346-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c346-112">Requirements</span></span>  
 <span data-ttu-id="2c346-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c346-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c346-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2c346-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c346-115">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2c346-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c346-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c346-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c346-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c346-117">See also</span></span>

- [<span data-ttu-id="2c346-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2c346-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2c346-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2c346-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
