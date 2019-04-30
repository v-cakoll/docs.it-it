---
title: Interfaccia IMetaDataImport2
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6717c48fca14f2200f783a984594388ef3b29c15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042471"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="d9e9b-102">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d9e9b-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="d9e9b-103">Estende la [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia per fornire la funzionalità di uso dei tipi generici.</span><span class="sxs-lookup"><span data-stu-id="d9e9b-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9e9b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d9e9b-104">Methods</span></span>  
  
|<span data-ttu-id="d9e9b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d9e9b-105">Method</span></span>|<span data-ttu-id="d9e9b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9e9b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9e9b-107">Metodo EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="d9e9b-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="d9e9b-108">Ottiene un enumeratore per una matrice di vincoli del parametro generico associato al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="d9e9b-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="d9e9b-109">Metodo EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="d9e9b-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="d9e9b-110">Ottiene un enumeratore per una matrice di parametri generici token associato con il TypeDef o MethodDef specificato token.</span><span class="sxs-lookup"><span data-stu-id="d9e9b-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="d9e9b-111">Metodo EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="d9e9b-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="d9e9b-112">Ottiene un enumeratore per una matrice dei token MethodSpec Neobsahuje associati MethodDef specificato o MemberRef token.</span><span class="sxs-lookup"><span data-stu-id="d9e9b-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="d9e9b-113">Metodo GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="d9e9b-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="d9e9b-114">Ottiene i metadati associati al vincolo del parametro generico rappresentato dal token di vincolo specificato.</span><span class="sxs-lookup"><span data-stu-id="d9e9b-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="d9e9b-115">Metodo GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="d9e9b-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="d9e9b-116">Ottiene i metadati associati al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="d9e9b-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="d9e9b-117">Metodo GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="d9e9b-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="d9e9b-118">Ottiene il token di firma dei metadati del metodo fa riferimento il MethodSpec Neobsahuje specificato.</span><span class="sxs-lookup"><span data-stu-id="d9e9b-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="d9e9b-119">Metodo GetPEKind</span><span class="sxs-lookup"><span data-stu-id="d9e9b-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="d9e9b-120">Ottiene un valore che identifica la natura del codice in un file eseguibile portabile (PE) di file, in genere un file DLL o EXE, definito nell'ambito dei metadati correnti</span><span class="sxs-lookup"><span data-stu-id="d9e9b-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="d9e9b-121">Metodo GetVersionString</span><span class="sxs-lookup"><span data-stu-id="d9e9b-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="d9e9b-122">Ottiene il numero di versione del runtime che è stato usato per compilare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d9e9b-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9e9b-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9e9b-123">Requirements</span></span>  
 <span data-ttu-id="d9e9b-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9e9b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9e9b-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d9e9b-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9e9b-126">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d9e9b-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9e9b-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e9b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e9b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9e9b-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="d9e9b-129">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="d9e9b-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="d9e9b-130">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d9e9b-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
