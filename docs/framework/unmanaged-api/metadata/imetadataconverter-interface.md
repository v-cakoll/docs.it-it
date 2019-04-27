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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d3377617ddd6b82ad88d22f6ffda04b1d6ae837
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904748"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="b52db-102">Interfaccia IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="b52db-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="b52db-103">Fornisce metodi per eseguire il mapping delle librerie dei tipi alle relative firme di metadati e per eseguire la conversione da una all'altra.</span><span class="sxs-lookup"><span data-stu-id="b52db-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b52db-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b52db-104">Methods</span></span>  
  
|<span data-ttu-id="b52db-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b52db-105">Method</span></span>|<span data-ttu-id="b52db-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b52db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b52db-107">Metodo GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="b52db-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="b52db-108">Ottiene un puntatore a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) istanza che rappresenta la firma dei metadati per la libreria dei tipi specificato fa riferimento `ITypeInfo` istanza.</span><span class="sxs-lookup"><span data-stu-id="b52db-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="b52db-109">Metodo GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="b52db-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="b52db-110">Ottiene un puntatore a un `IMetaDataImport` istanza che rappresenta la firma dei metadati per la libreria dei tipi rappresentata dall'oggetto specificato `ITypeLib` istanza.</span><span class="sxs-lookup"><span data-stu-id="b52db-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="b52db-111">Metodo GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="b52db-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="b52db-112">Ottiene un puntatore a un `ITypeLib` istanza che rappresenta la libreria dei tipi con i nomi di modulo e di libreria specificati.</span><span class="sxs-lookup"><span data-stu-id="b52db-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b52db-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b52db-113">Requirements</span></span>  
 <span data-ttu-id="b52db-114">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b52db-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b52db-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b52db-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b52db-116">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b52db-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b52db-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b52db-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b52db-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b52db-118">See also</span></span>

- [<span data-ttu-id="b52db-119">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="b52db-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="b52db-120">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b52db-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
