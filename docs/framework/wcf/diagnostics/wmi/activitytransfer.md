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
ms.openlocfilehash: 7c1caf0ae27efce858328e5db88434253be61d50
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="ab25b-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="ab25b-102">ActivityTransfer</span></span>
<span data-ttu-id="ab25b-103">Evento trasferimento attività</span><span class="sxs-lookup"><span data-stu-id="ab25b-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab25b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab25b-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ab25b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ab25b-105">Methods</span></span>  
 <span data-ttu-id="ab25b-106">La classe ActivityTransfer non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="ab25b-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ab25b-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ab25b-107">Properties</span></span>  
 <span data-ttu-id="ab25b-108">La classe ActivityTransfer dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab25b-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="ab25b-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="ab25b-109">ActivityID</span></span>  
  
-   <span data-ttu-id="ab25b-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="ab25b-110">Data type: object</span></span>  
    <span data-ttu-id="ab25b-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ab25b-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="ab25b-112">ID attività</span><span class="sxs-lookup"><span data-stu-id="ab25b-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="ab25b-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="ab25b-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="ab25b-114">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="ab25b-114">Data type: object</span></span>  
    <span data-ttu-id="ab25b-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ab25b-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="ab25b-116">ID attività correlata</span><span class="sxs-lookup"><span data-stu-id="ab25b-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab25b-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab25b-117">Requirements</span></span>  
  
|<span data-ttu-id="ab25b-118">MOF</span><span class="sxs-lookup"><span data-stu-id="ab25b-118">MOF</span></span>|<span data-ttu-id="ab25b-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ab25b-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ab25b-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ab25b-120">Namespace</span></span>|<span data-ttu-id="ab25b-121">Definito in root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="ab25b-121">Defined in root\ServiceModel.</span></span>|
