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
ms.openlocfilehash: b4e701c2f0d669a04be7f7235c8ab1edb8ce1612
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="c40ac-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="c40ac-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="c40ac-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="c40ac-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c40ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c40ac-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c40ac-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c40ac-105">Methods</span></span>  
 <span data-ttu-id="c40ac-106">La classe WSAT_TraceRecord non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="c40ac-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c40ac-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c40ac-107">Properties</span></span>  
 <span data-ttu-id="c40ac-108">La classe WSAT_TraceRecord dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c40ac-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="c40ac-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="c40ac-109">ActivityID</span></span>  
 <span data-ttu-id="c40ac-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="c40ac-110">Data type: object</span></span>  
<span data-ttu-id="c40ac-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c40ac-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c40ac-112">ID attività del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="c40ac-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="c40ac-113">EventID</span><span class="sxs-lookup"><span data-stu-id="c40ac-113">EventID</span></span>  
 <span data-ttu-id="c40ac-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="c40ac-114">Data type: sint32</span></span>  
<span data-ttu-id="c40ac-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c40ac-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c40ac-116">ID evento del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="c40ac-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="c40ac-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="c40ac-117">TraceRecord</span></span>  
 <span data-ttu-id="c40ac-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c40ac-118">Data type: string</span></span>  
<span data-ttu-id="c40ac-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c40ac-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c40ac-120">Record di traccia</span><span class="sxs-lookup"><span data-stu-id="c40ac-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c40ac-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c40ac-121">Requirements</span></span>  
  
|<span data-ttu-id="c40ac-122">MOF</span><span class="sxs-lookup"><span data-stu-id="c40ac-122">MOF</span></span>|<span data-ttu-id="c40ac-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c40ac-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c40ac-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c40ac-124">Namespace</span></span>|<span data-ttu-id="c40ac-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c40ac-125">Defined in root\ServiceModel</span></span>|
