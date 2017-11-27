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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3966311bc10b5ad2ee401ef9e3e13c8f36e14505
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="e04fd-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="e04fd-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="e04fd-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="e04fd-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e04fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e04fd-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e04fd-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e04fd-105">Methods</span></span>  
 <span data-ttu-id="e04fd-106">La classe WSAT_TraceRecord non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="e04fd-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e04fd-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e04fd-107">Properties</span></span>  
 <span data-ttu-id="e04fd-108">La classe WSAT_TraceRecord dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="e04fd-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="e04fd-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="e04fd-109">ActivityID</span></span>  
 <span data-ttu-id="e04fd-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="e04fd-110">Data type: object</span></span>  
<span data-ttu-id="e04fd-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e04fd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e04fd-112">ID attività del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="e04fd-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="e04fd-113">EventID</span><span class="sxs-lookup"><span data-stu-id="e04fd-113">EventID</span></span>  
 <span data-ttu-id="e04fd-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e04fd-114">Data type: sint32</span></span>  
<span data-ttu-id="e04fd-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e04fd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e04fd-116">ID evento del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="e04fd-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="e04fd-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="e04fd-117">TraceRecord</span></span>  
 <span data-ttu-id="e04fd-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="e04fd-118">Data type: string</span></span>  
<span data-ttu-id="e04fd-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e04fd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e04fd-120">Record di traccia</span><span class="sxs-lookup"><span data-stu-id="e04fd-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e04fd-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e04fd-121">Requirements</span></span>  
  
|<span data-ttu-id="e04fd-122">MOF</span><span class="sxs-lookup"><span data-stu-id="e04fd-122">MOF</span></span>|<span data-ttu-id="e04fd-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e04fd-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e04fd-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="e04fd-124">Namespace</span></span>|<span data-ttu-id="e04fd-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e04fd-125">Defined in root\ServiceModel</span></span>|
