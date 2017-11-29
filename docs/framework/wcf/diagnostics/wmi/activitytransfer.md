---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acbc346da940caf933868a03295744132bda4733
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="97fa9-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="97fa9-102">ActivityTransfer</span></span>
<span data-ttu-id="97fa9-103">Evento trasferimento attività</span><span class="sxs-lookup"><span data-stu-id="97fa9-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97fa9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97fa9-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="97fa9-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="97fa9-105">Methods</span></span>  
 <span data-ttu-id="97fa9-106">La classe ActivityTransfer non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="97fa9-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="97fa9-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="97fa9-107">Properties</span></span>  
 <span data-ttu-id="97fa9-108">La classe ActivityTransfer dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="97fa9-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="97fa9-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="97fa9-109">ActivityID</span></span>  
  
-   <span data-ttu-id="97fa9-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="97fa9-110">Data type: object</span></span>  
    <span data-ttu-id="97fa9-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="97fa9-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="97fa9-112">ID attività</span><span class="sxs-lookup"><span data-stu-id="97fa9-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="97fa9-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="97fa9-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="97fa9-114">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="97fa9-114">Data type: object</span></span>  
    <span data-ttu-id="97fa9-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="97fa9-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="97fa9-116">ID attività correlata</span><span class="sxs-lookup"><span data-stu-id="97fa9-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97fa9-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97fa9-117">Requirements</span></span>  
  
|<span data-ttu-id="97fa9-118">MOF</span><span class="sxs-lookup"><span data-stu-id="97fa9-118">MOF</span></span>|<span data-ttu-id="97fa9-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="97fa9-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="97fa9-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="97fa9-120">Namespace</span></span>|<span data-ttu-id="97fa9-121">Definito in root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="97fa9-121">Defined in root\ServiceModel.</span></span>|
