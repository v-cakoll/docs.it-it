---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d24f74d4086a5499d3bfd4ef6183d377528acc21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="bf932-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="bf932-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="bf932-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="bf932-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf932-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf932-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bf932-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="bf932-105">Methods</span></span>  
 <span data-ttu-id="bf932-106">La classe WSAT_TraceRecord non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="bf932-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bf932-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="bf932-107">Properties</span></span>  
 <span data-ttu-id="bf932-108">La classe WSAT_TraceRecord dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf932-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="bf932-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="bf932-109">ActivityID</span></span>  
 <span data-ttu-id="bf932-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="bf932-110">Data type: object</span></span>  
<span data-ttu-id="bf932-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="bf932-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf932-112">ID attività del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="bf932-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="bf932-113">ID evento</span><span class="sxs-lookup"><span data-stu-id="bf932-113">EventID</span></span>  
 <span data-ttu-id="bf932-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="bf932-114">Data type: sint32</span></span>  
<span data-ttu-id="bf932-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="bf932-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf932-116">ID evento del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="bf932-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="bf932-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="bf932-117">TraceRecord</span></span>  
 <span data-ttu-id="bf932-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="bf932-118">Data type: string</span></span>  
<span data-ttu-id="bf932-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="bf932-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf932-120">Record di traccia</span><span class="sxs-lookup"><span data-stu-id="bf932-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf932-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf932-121">Requirements</span></span>  
  
|<span data-ttu-id="bf932-122">MOF</span><span class="sxs-lookup"><span data-stu-id="bf932-122">MOF</span></span>|<span data-ttu-id="bf932-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bf932-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bf932-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="bf932-124">Namespace</span></span>|<span data-ttu-id="bf932-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bf932-125">Defined in root\ServiceModel</span></span>|
