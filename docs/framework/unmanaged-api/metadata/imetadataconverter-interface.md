---
title: Interfaccia IMetaDataConverter
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: b771b368c069a4577d266b47bfb4a5ee1935e48e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436266"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="d2958-102">Interfaccia IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="d2958-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="d2958-103">Fornisce metodi per eseguire il mapping delle librerie dei tipi alle relative firme di metadati e per eseguire la conversione da una all'altra.</span><span class="sxs-lookup"><span data-stu-id="d2958-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2958-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d2958-104">Methods</span></span>  
  
|<span data-ttu-id="d2958-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d2958-105">Method</span></span>|<span data-ttu-id="d2958-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2958-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2958-107">Metodo GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="d2958-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="d2958-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span><span class="sxs-lookup"><span data-stu-id="d2958-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="d2958-109">Metodo GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="d2958-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="d2958-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span><span class="sxs-lookup"><span data-stu-id="d2958-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="d2958-111">Metodo GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="d2958-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="d2958-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span><span class="sxs-lookup"><span data-stu-id="d2958-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2958-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2958-113">Requirements</span></span>  
 <span data-ttu-id="d2958-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2958-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2958-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d2958-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2958-116">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2958-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2958-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2958-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2958-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2958-118">See also</span></span>

- [<span data-ttu-id="d2958-119">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="d2958-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="d2958-120">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d2958-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
