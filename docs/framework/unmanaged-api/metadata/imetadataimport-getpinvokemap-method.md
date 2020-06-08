---
title: Metodo IMetaDataImport::GetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
ms.openlocfilehash: 8409e56b5ec4dbe47035a0555b6b7ce175b517ee
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490978"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="2c3f5-102">Metodo IMetaDataImport::GetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="2c3f5-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="2c3f5-103">Ottiene un token ModuleRef per rappresentare l'assembly di destinazione di una chiamata PInvoke.</span><span class="sxs-lookup"><span data-stu-id="2c3f5-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c3f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c3f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c3f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c3f5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="2c3f5-106">in Token FieldDef o MethodDef per il quale ottenere i metadati del mapping PInvoke.</span><span class="sxs-lookup"><span data-stu-id="2c3f5-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="2c3f5-107">out Puntatore ai flag utilizzati per il mapping.</span><span class="sxs-lookup"><span data-stu-id="2c3f5-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="2c3f5-108">Questo valore è una maschera di maschera dall'enumerazione [CorPinvokeMap](corpinvokemap-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="2c3f5-108">This value is a bitmask from the [CorPinvokeMap](corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="2c3f5-109">out Nome della DLL di destinazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="2c3f5-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="2c3f5-110">in Dimensioni in caratteri wide di `szImportName` .</span><span class="sxs-lookup"><span data-stu-id="2c3f5-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="2c3f5-111">out Numero di caratteri wide restituiti in `szImportName` .</span><span class="sxs-lookup"><span data-stu-id="2c3f5-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="2c3f5-112">out Puntatore a un token ModuleRef che rappresenta la libreria di oggetti di destinazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="2c3f5-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c3f5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c3f5-113">Requirements</span></span>  
 <span data-ttu-id="2c3f5-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c3f5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c3f5-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2c3f5-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c3f5-116">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2c3f5-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c3f5-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c3f5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c3f5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c3f5-118">See also</span></span>

- [<span data-ttu-id="2c3f5-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2c3f5-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2c3f5-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2c3f5-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
