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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f3db50a32fabc117c79eef5ac086a7798f86ed3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="32d3a-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="32d3a-102">ActivityTransfer</span></span>
<span data-ttu-id="32d3a-103">Evento trasferimento attività</span><span class="sxs-lookup"><span data-stu-id="32d3a-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32d3a-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="32d3a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="32d3a-105">Methods</span></span>  
 <span data-ttu-id="32d3a-106">La classe ActivityTransfer non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="32d3a-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="32d3a-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="32d3a-107">Properties</span></span>  
 <span data-ttu-id="32d3a-108">La classe ActivityTransfer dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="32d3a-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="32d3a-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="32d3a-109">ActivityID</span></span>  
  
-   <span data-ttu-id="32d3a-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="32d3a-110">Data type: object</span></span>  
    <span data-ttu-id="32d3a-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="32d3a-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="32d3a-112">ID attività</span><span class="sxs-lookup"><span data-stu-id="32d3a-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="32d3a-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="32d3a-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="32d3a-114">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="32d3a-114">Data type: object</span></span>  
    <span data-ttu-id="32d3a-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="32d3a-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="32d3a-116">ID attività correlata</span><span class="sxs-lookup"><span data-stu-id="32d3a-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32d3a-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32d3a-117">Requirements</span></span>  
  
|<span data-ttu-id="32d3a-118">MOF</span><span class="sxs-lookup"><span data-stu-id="32d3a-118">MOF</span></span>|<span data-ttu-id="32d3a-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="32d3a-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="32d3a-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="32d3a-120">Namespace</span></span>|<span data-ttu-id="32d3a-121">Definito in root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="32d3a-121">Defined in root\ServiceModel.</span></span>|
